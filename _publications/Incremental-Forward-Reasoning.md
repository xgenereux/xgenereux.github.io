---
title: "Incremental Forward Reasoning for White-Box Proof Search"
collection: publications
permalink: /publication/Incremental-Forward-Reasoning
excerpt: 'Joint work with Jannis Limperg'
date: 2025-03-01
venue: 'CADE 2025'
venuestring: 'Submitted to'
paperurl: 'https://github.com/JLimperg/paper-aesop-forward/releases/download/submission/paper.pdf'
citation: 'Jannis Limperg and Xavier Généreux,
Incremental Forward Reasoning for White-Box Proof Search,
2025,'
---
Several proof assistants provide automation tactics based on
tableau-style tree search, such as Isabelle’s and Rocq’s auto and Lean’s
Aesop. In this setting we consider forward rules, which apply a given
theorem, say, A → B → C, to any goal containing hypotheses A and
B, adding C as a new hypothesis. When treated naively, such rules are
tried on every goal encountered during the search, leading to repeated
unifications of premises A and B with the hypotheses of each goal. We
present an approach to forward rules that avoids some of this repeated
work by taking advantage of similarities between successive goals. For
each goal, we cache partial applications of forward rules in a custom data
structure that enables efficient updates. Our technique is compatible with
any search strategy and most logics. It has been implemented in Aesop.

[Download paper here](https://github.com/JLimperg/paper-aesop-forward/releases/download/submission/paper.pdf)
