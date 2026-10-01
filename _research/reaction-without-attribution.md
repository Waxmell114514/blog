---
title: "Reaction Without Attribution: Hijacking a VLA's Actions Reveals No Linearly Readable Efference Copy"
excerpt: "Overriding a VLA policy's actions and probing its hidden states for any sign that it registers the movement was not its own. Accepted at the NeurIPS 2026 RoboPAD Workshop."
collection: research
period: "NeurIPS 2026 RoboPAD Workshop · accepted"
date: 2026-09-12
---

{% include base_path %}

**Accepted at the NeurIPS 2026 RoboPAD Workshop.** [PDF]({{ base_path }}/files/Reaction_Without_Attribution.pdf) · [OpenReview](https://openreview.net/forum?id=1OTHIshAFK)

If you override a robot policy's actions, does anything inside it register that
the movement wasn't its own? I ran
[OpenVLA-OFT](https://openvla-oft.github.io) on LIBERO-Goal, replaced a quarter of
its action chunks with plausible chunks from other episodes, and trained linear
probes on its hidden states to tell hijacked transitions from normal ones.

The probes found nothing, even though both halves of the comparison are available:
hand-built features comparing commanded against executed motion reach 0.69 (up
to 0.875 for the more disruptive overrides), and the policy's intended action is
linearly readable from its hidden state at R² = 0.64. The policy does become less
confident after some hijacks, but only when the override makes the scene look
unusual, so its reaction is explained by ordinary visual feedback rather than by
any attribution of the action to itself.

The full write-up, including limitations, is in the blog post
[Does a VLA policy notice when you hijack its actions?]({{ base_path }}/posts/2026/09/hijacking-vla-actions/).
