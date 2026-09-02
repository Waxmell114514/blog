---
title: "Mechanistic interpretability of large models"
excerpt: "Reverse-engineering the features and circuits inside trained models, using sparse autoencoders, causal tracing, and circuit discovery."
collection: research
period: "Current focus"
date: 2026-06-01
---

My current research direction. Rather than judging a model only by its outputs, I
am interested in reading its internals directly: which features it represents,
where they live, and which components are causally responsible for a given
behaviour.

The methods I work with
======
* **Sparse autoencoders and dictionary learning** — decomposing dense activations
  into a larger, sparser set of directions that are easier to interpret one at a
  time.
* **Activation patching and causal tracing** — swapping activations between runs
  to establish which components actually cause a behaviour, instead of merely
  correlating with it.
* **Logit lens and attribution analysis** — projecting intermediate states into
  output space and attributing predictions back to the components that produced
  them.
* **Circuit discovery** — piecing individual components together into the
  subgraph that implements a specific capability.
* **Linear probing of internal representations** — testing what information is
  linearly recoverable from a given layer.

Tooling
======
Mostly Python, with [PyTorch](https://pytorch.org) and
[TransformerLens](https://github.com/TransformerLensOrg/TransformerLens).
