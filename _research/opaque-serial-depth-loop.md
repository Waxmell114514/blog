---
title: "How Much Opaque Serial Depth Does a Loop Buy? A Preregistered Study of No-CoT Reasoning in Small Looped Transformers"
excerpt: "Measuring how much serial computation one extra loop buys a looped transformer without chain of thought, compared with one extra unshared layer. Preprint, October 2026."
collection: research
period: "Preprint · October 2026"
date: 2026-10-12
---

{% include base_path %}

**Preprint, October 2026.** [PDF]({{ base_path }}/files/Opaque_Serial_Depth_Loop.pdf)

Looped transformers apply the same layers several times per token, which gives
them serial computation that never shows up in the chain of thought (CoT). How
much of that depth does a trained model actually use? I trained ∼2.2M-parameter
looped transformers from scratch on in-context pointer chasing, a task whose
serial difficulty can be set directly, with every prediction, verdict rule and
analysis preregistered.

With bidirectional attention among edge tokens, each loop adds 0.74 hops of
no-CoT pointer chasing (95% CI [0.70, 0.76]), from 3.5 hops at one loop to 8.8 at
eight; under a causal mask no law holds. At matched effective depth, plain models
with unshared layers beat looped ones by 0.45–0.68 hops, and letting later
positions read the final loop's KV cache gives no gain from filler tokens. Hop
counts track how far the training curriculum progressed, so these numbers measure
trained reach rather than architectural capacity. On the data side, the ability
to answer without CoT is learned from a fixed number of no-CoT examples (between
32,768 and 65,536), not a fixed fraction of the training set. Of the 10
preregistered predictions, 7 held; the 3 that failed all concern the functional
form of the loop law.
