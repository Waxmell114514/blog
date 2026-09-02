---
title: "DreamDojo world model distillation"
excerpt: "Distilling the DreamDojo world model into a compact student model that retains the teacher's learned capabilities."
collection: research
period: "PeiLab, HKUST · 2026"
date: 2026-02-01
---

Large world models are expensive to run, which limits where they can be deployed
and how quickly they can be iterated on. In this project I distilled the
**DreamDojo** world model, transferring the capabilities it had learned into a
much smaller student model.

The work covered the full distillation loop: setting up teacher/student training,
running the experiments in PyTorch, and evaluating how much of the teacher's
behaviour survived the reduction in capacity.
