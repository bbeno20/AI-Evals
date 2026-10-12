# First LLM-as-a-Judge Eval, Module 1

## Version A, Concise, system prompt used

You are an executive briefing assistant.
Summarize in exactly 3 bullet points under 60 words. No preamble, no extra text.

## Version B, Narrative, system prompt used

You are a PR communications assistant.
Write a 100-word narrative summary highlighting wins first, then risks and next steps. Keep a positive tone. No bullets.

## Eval setup, dataset name + judge model/family

Dataset: Module1Output (Output A, Output B, plus the cold-start starter rows). Evaluator: Conciseness LLM-as-a-Judge, binary (1 = concise and faithful, 0 = not). Generator: Claude (Anthropic). Judge: ChatGPT (OpenAI), a different model family to avoid self-preference bias. Result: A = 1 (concise, faithful, all key facts and deadlines kept). B = 0 (padded, added unsupported claims like "real momentum" and "strong signal that the refreshed strategy is landing").

## Cold-start, the prompt you used to seed a starter dataset

Generate 20 example rows for evaluating email-summary quality.
Each row: an input email + a candidate summary + a first-pass label ("good" or "bad") + a one-line reason.
Make roughly half concise/faithful ("good") and half verbose or inaccurate ("bad").
Include a few tricky cases: summaries that are short but drop a key deadline,
and summaries that are accurate but bury the most important item.
Return it as a markdown table.

## Your definition of good vs bad (golden-set criteria), the graded part, write your own

Good: every number, date, and owner matches the email exactly. Nothing added, no spin. All action items and deadlines survive. Risks and blockers are stated plainly, not buried behind wins. Readable in under 15 seconds.

Bad: fails any of the first three (hard fails), or is padded enough that the reader has to hunt for the point.

Edge cases: short but drops a deadline = bad. Accurate but buries the blocker = bad for a CEO. Rounded numbers only OK if the source is also approximate.

Changes to the LLM's labels: flipped row 8 to bad (dropped the "confirm address, then ship" action item). Dropped row 20 (duplicate of row 6). Added 3 rows for subtle failures the generated set missed: a summary that softens churn going 3% to 5% into "ticked up slightly," a clean version of the same summary, and one that rounds 23.6% to "roughly 25%."

## Screenshots, links or repo paths (optional if you followed the demo)
