# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).
> Becomes the Strategy Canvas slide of the final pitch deck you assemble in Module 6.

## 1. Product Strategy, The Context

**Target user:** VP-level Strategists and Product Leaders at Fortune 500 companies who pay a premium for verified market intelligence.

**Key use case:** Rapidly extracting specific, verified insights (e.g., comparing competitor pricing models or summarizing G2 reviews) without manual data digging.

**Value proposition:** Personalized, instant answers based on verified data, dramatically reducing the time spent finding and synthesizing information for high-stakes decisions and strategic roadmaps.

## 2. Measurements, The Execution

**User promise.** For VP-level strategists, Ascend IQ promises competitive intelligence they can trust without fact-checking it, delivered in seconds, so they can make roadmap calls without digging through data themselves.

**Top 3 trust metrics:**
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Robustness**, Coherence on messy, adversarial, out-of-scope inputs.
- **UX Trust**, Subjective predictability and consistency over time.

**Why these three:** • Hallucination Rate: these VPs pay for verified intel, so one fabricated number in a board deck ends the relationship. This is the metric the whole product lives or dies on.
• Robustness: VPs ask vague, messy, half-formed questions, not clean ones. If quality falls apart on a sloppy prompt, the tool fails exactly when they need it.
• UX Trust: a VP has to get the same answer to the same question today and next week. Inconsistency reads as unreliability, and they quietly stop using it.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Robustness
We prioritize Hallucination Rate over Robustness because a confident wrong answer is worse than a weak answer on a messy question. A VP can work with "I'm not sure," but a made-up number in a board deck ends the contract.

### Trade-off 2 · Hallucination Rate ↔ UX Trust
We prioritize Hallucination Rate over UX Trust because being consistently reliable means nothing if the answer is wrong. I'd rather the tool be occasionally uneven than smoothly confident about something false.

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._
