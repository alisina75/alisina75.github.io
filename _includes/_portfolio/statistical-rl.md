---
title: "Statistical Reinforcement Learning: Adaptive Control of LQ Systems"
collection: portfolio
category: course
order: 1
summary: "Reproduced and analyzed regret bounds for the adaptive control of linear quadratic systems with unknown model parameters."
badge: "Course Project"
badge_class: "badge--course"
links:
  - label: "Paper (PMLR)"
    url: "https://proceedings.mlr.press/v19/abbasi-yadkori11a/abbasi-yadkori11a.pdf"
  - label: "Report (PDF)"
    url: "/files/misc_notes/CS542_project.pdf"
---

*Instructor: Nan Jiang*

Reproduced and analyzed the core results of *"Regret Bounds for the Adaptive
Control of Linear Quadratic Systems"* by Abbasi-Yadkori and Szepesvári. The work
presents key theorems, lemmas, and an algorithm for solving Linear Quadratic (LQ)
control problems with unknown model parameters — commonly referred to as adaptive
control — aiming to minimize regret. The proposed algorithm estimates parameters
using high-probability confidence sets and achieves a regret bound of
$\tilde{O}(\sqrt{T})$.
