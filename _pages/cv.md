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

Profile
======
Year 2 Data Science and Technology undergraduate at HKUST with hands-on research
experience in reward model training, world model distillation, and VLA/LLM
training. Current focus on mechanistic interpretability of large models.

Education
======
* **BSc in Data Science and Technology**, The Hong Kong University of Science and
  Technology, Hong Kong — Year 2 (in progress)
  * Cumulative GPA: 3.92 / 4.30

Honours and awards
======
* **HKUST Continuing Scholarship** — awarded for sustained academic excellence
* **S. S. Chern Class** — member of HKUST's selective honours class

Research experience
======
* **Undergraduate Research Assistant (UGRA)**, PeiLab, HKUST — Jan 2026 – Aug 2026
  * Trained reward models and ran model-training experiments in PyTorch.
  * Distilled the DreamDojo world model, transferring learned capabilities into a
    compact student model.
  * Built and maintained end-to-end training pipelines for VLA and LLM-based models.

Skills
======
* **Programming**
  * Python
* **Frameworks**
  * PyTorch
  * TransformerLens
* **Machine learning**
  * Reward model training
  * World model distillation
  * VLA and LLM training
* **Mechanistic interpretability**
  * Sparse autoencoders and dictionary learning
  * Activation patching and causal tracing
  * Logit lens and attribution analysis
  * Circuit discovery
  * Linear probing of internal representations

Projects
======
  <ul>{% for post in site.research reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
