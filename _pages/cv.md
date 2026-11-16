---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download this CV as a PDF]({{ base_path }}/files/Ziwei_Liu_CV.pdf)

Data science undergraduate · machine learning research · Hong Kong ·
[zliuhs@connect.ust.hk](mailto:zliuhs@connect.ust.hk) ·
[github.com/Waxmell114514](https://github.com/Waxmell114514)

Education
======
* **BSc in Data Science and Technology**, The Hong Kong University of Science and
  Technology (HKUST), Hong Kong — Sep 2025 – Jun 2029 (expected)
  * Cumulative GPA: 3.92 / 4.30
  * S. S. Chern Class, HKUST's selective honours class in mathematics and science

Research interests
======
I study what happens inside large models and use it to make them cheaper to run.
My current focus is mechanistic interpretability applied to efficient LLM
inference on consumer hardware: what quantization destroys inside a model, and
which components decide expert routing in mixture-of-experts models. I also work
on memory and context management for LLM agents.

Publications and preprints
======
* Ziwei Liu. **Reaction Without Attribution: Hijacking a VLA's Actions Reveals No
  Linearly Readable Efference Copy.** *NeurIPS 2026 Workshop (RoboPAD)*, 2026.
  Accepted.
  [PDF]({{ base_path }}/files/Reaction_Without_Attribution.pdf) ·
  [OpenReview](https://openreview.net/forum?id=1OTHIshAFK) ·
  [project page]({{ base_path }}/research/reaction-without-attribution/) ·
  [blog post]({{ base_path }}/posts/2026/09/hijacking-vla-actions/)

* Ziwei Liu, et al. **A Count, Not a Fraction: Hundreds of Examples to Build a
  Cache, Dozens to Trust It.** Under review at ICLR 2027.

* Ziwei Liu. **Predictive but Not Faithfully Recovering: An Oracle-Bounded Audit
  of Model-Diffing Methods.** Under review at AAAI 2027.

Research projects
======
* **Who writes the routing decision? Expert prediction and prefetching in
  mixture-of-experts LLMs** — 2026
  * Decomposed cross-layer expert-prediction failures exactly into per-head and
    per-expert contributions on three MoE models (OLMoE-1B-7B, Qwen3.6-35B-A3B,
    Qwen3-30B-A3B). The top 10% of components carry 49–71% of routing flips, and
    causal ablation on two of the models confirms the attribution.
  * Built a lookup-table predictor that matches a rank-8 to rank-16 linear adapter
    with 4–8× fewer operations, then implemented prefetching in two llama.cpp
    offloading paths on an 8 GB laptop GPU. Prefetching did not speed up decoding
    (15–28% slower when streaming to VRAM, no change with a RAM cache), and I
    identified four conditions it needs in order to pay off.
* **What post-training quantization damages inside LLMs** (ongoing) — 2026
  * Testing a low-frequency-erasure hypothesis against a margin-to-noise
    hypothesis for quantization damage, with the aim of cheaper and
    better-targeted quantization.
* **jev-compaction: context compaction for coding agents** (open source) — 2026
  * A small judgment model scores transcript segments and never rewrites text.
    Kept lines stay verbatim, low-scoring segments move to a store the agent can
    expand on demand, and the prompt cache stays valid.
  * Evaluated on SWE-bench tasks and on long-session revisit-chain tests.
* **Quantitative trading research** (independent) — 2026
  * Found persistent premiums and funding rates on US and Hong Kong stock
    perpetual futures listed on crypto exchanges and traded them as a
    delta-neutral arbitrage. Documented how these venues mishandle stock splits
    and dividends.

Experience
======
* **Undergraduate Research Assistant**, HKUST, Hong Kong — Jan 2026 – Aug 2026
  * Trained reward models and ran training experiments in PyTorch.
  * Distilled the DreamDojo world model into a compact student model.
  * Built and maintained end-to-end training pipelines for VLA and LLM-based models.
* **Undergraduate Teaching Assistant, COMP1021 Introduction to Computer Science**,
  HKUST, Hong Kong — Sep 2026 – Jan 2027

Honours and activities
======
* S. S. Chern Class and S. S. Chern Scholarship, HKUST
* HKUST Continuing Scholarship, awarded for sustained academic excellence
* YC Startup School Taipei, selected attendee, 2026

Skills
======
* **Programming:** Python, C++ (llama.cpp patches)
* **Frameworks and tools:** PyTorch, TransformerLens, llama.cpp and GGUF
  quantization, Nsight Systems profiling
* **Interpretability:** sparse autoencoders and crosscoders, activation patching
  and causal tracing, linear probing, logit lens, circuit discovery
* **Machine learning:** training small transformers from scratch, reward-model
  training, world-model distillation, VLA and LLM training pipelines
* **Languages:** Mandarin, English

Project pages
======
  <ul>{% for post in site.research reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
