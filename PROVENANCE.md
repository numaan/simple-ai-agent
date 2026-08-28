# Provenance

This repository is a copy of [timlrx/simple-ai-agents](https://github.com/timlrx/simple-ai-agents)
at commit `d1896b2e32f4ba8150cd6bc937754f3d94f8adb3` (2024-10-06), MIT licensed, redistributed
under that licence with `LICENSE` intact. Copyright (c) 2023 Timothy Lin.

**The only addition is `citadel-agent.yaml`.** No source file has been modified — that is the
point of the exercise: an unmodified third-party agent, onboarded through Citadel-One's
least-privilege scanner, so the declared grant can be compared against what the code actually does.

`citadel-agent.yaml` declares a deliberately NARROW grant: one model (`gpt-4o-mini`) reached
through the in-cluster LiteLLM proxy. The code names roughly a dozen models across `examples/`
and, by default, calls providers directly. Every one of those gaps should surface in the scan as
`under_declared`. A clean scan here would mean the scanner is reading the declaration rather than
the code.
