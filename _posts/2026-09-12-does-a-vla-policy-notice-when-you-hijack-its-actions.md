---
title: "Does a VLA policy notice when you hijack its actions?"
date: 2026-09-12
permalink: /posts/2026/09/hijacking-vla-actions/
tags:
  - mechanistic interpretability
  - VLA
  - probing
  - robotics
excerpt: "I overrode a robot policy's actions and probed its hidden states for any sign that it noticed. Linear probes found nothing — even though both halves of the comparison are sitting right there."
---

{% include base_path %}

I spent about 20 hours on a small question: if you override a robot policy's
actions, does anything inside it register that the movement wasn't its own?

The setup
======
[OpenVLA-OFT](https://openvla-oft.github.io) running LIBERO-Goal. It is
memoryless — on each call it sees one camera image and the instruction, then
emits an action chunk. So it has no way to remember what it asked for last time.

Randomly, a quarter of the time, I threw away the chunk it produced and executed
a different one instead. Usually I substituted a chunk from another episode of
the same task, so the robot still moved in a plausible way and my probes could
not cheat by noticing weird motion.

Then I trained linear probes on the hidden states to see whether a hijacked
transition looked any different from a normal one.

They found nothing. I tried handing the probe more and more help — the commanded
chunk, the state from before the action as well as after — and it stayed at the
floor.

Why I believe the null
======
The null is credible, because while the linear probes found nothing, the
information is clearly available:

* If I hand-build features that compare what was commanded against what actually
  happened, a probe gets to **0.69**, and up to **0.875** for the more disruptive
  overrides.
* The policy's intended action is also sitting right there in its hidden state,
  readable at **R² = 0.64**.

So both halves of the comparison exist. Nothing in the model appears to have done
the comparison.

The behaviour is the interesting part
======
After a hijack the policy does get less confident on its next call, and that is a
real effect. But it only shows up for the overrides that make the scene look
unusual. The one where I zero out the motion entirely — the most blatant
violation of what it asked for — produces no reaction at all.

So it is reacting to what it sees, not to having been overridden. Ordinary visual
feedback control is enough to explain everything here.

Limitations
======
The most obvious limitation should be stressed: I only use linear probes, so the
attribution information could be undetectable simply by hiding in the
nonlinearity. A two-layer MLP on the same features would be the cheap way to show
I am wrong, and I would like someone to try it.

I would also like to run this on an RL-trained version of the same model, since
RL actually trains on the consequences of the policy's own actions.

If you try either, I would like to hear about it —
[zliuhs@connect.ust.hk](mailto:zliuhs@connect.ust.hk).
