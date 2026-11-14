---
name: effective-writer
description: "Audit and rewrite text or documents for answer-first clarity, logical structure, and decision-readiness. Use when a user asks to improve a message, memo, PR description, slide outline, or similar written communication."
---

# Effective Writer

Audit and rewrite written communications using the Effective Communication / Pyramid Principle. The result should be clear, answer-first, and ready for a reader to decide or act.

## Input

The user may paste text, reference text already in the conversation (including a prior assistant response), or provide a file path. Read a referenced file. If no target text is available, ask the user to paste it or supply a path.

## Audit

Before rewriting, assess the text against the applicable principles below. Make concrete findings tied to quoted sentences or sections; do not use generic labels such as “vague.”

1. **Purpose:** Identify the requested decision, feedback, approval, or action; distinguish present scope from prior or future work; surface trade-offs, disagreement, uncertainty, and feedback needs. Prefer purpose → reasoning → mechanics → evidence.
2. **Answer first:** Open with a governing thought and explicit requested action. Put the answer before supporting arguments and evidence. Explain why the recommended alternative wins; move history or analysis below the fold.
3. **Logical pyramid:** Ensure each level summarizes the one beneath it and answers the reader’s implied question: Why? → distinct reasons; How? → ordered steps; What supports this? → evidence. Peer points must be the same type, mutually exclusive, and logically ordered. Usually use about three main arguments (three to four for a presentation). Flag material that does not support the governing thought.
4. **Necessary context:** When context is needed, keep it brief and structure it as Situation → Complication → Question → Answer.
5. **Decisions:** For a decision, present two or three genuine options with distinct advantages and disadvantages. State the recommendation, explain rejected options, and disclose uncertainty or disagreement. Justify any middle option used for comparison with evidence.
6. **Audience:** Anticipate the reader’s questions, objections, and information needs. Make reasoning visible and support selective reading: conclusion, essential reasoning, optional depth.
7. **Evidence:** Support important claims with relevant facts, data, examples, or analysis. Put evidence under the argument it supports and state its implication. Retain only decision-relevant evidence. For charts, check the takeaway, labels, scale, and legibility.
8. **Slide outlines:** Open with the conclusion; use three to four distinct supporting arguments; give each slide one primary point with suitable evidence or visuals; ensure the sequence builds logically.
9. **Clarity:** Prefer direct conclusions over chronological narration. Use descriptive headings, short focused sections, precise language, and correct mechanics. Remove unnecessary history, repetition, jargon, filler, and mechanical transitions.

## Deliver the audit

Give a terse, bullet-point audit before the rewrite. Group findings under only the categories that have issues:

- **Structural issues:** Missing or buried governing thought, weak ordering or pyramid, or missing SCQA context.
- **Decision-presentation issues:** Missing real options, recommendation, trade-offs, or disclosed uncertainty.
- **Evidence issues:** Unsupported, irrelevant, or misplaced evidence.
- **Clarity issues:** Jargon, filler, chronological narration, or grammar problems.

Be direct: explicitly call out buried conclusions, absent recommendations, and unsupported claims.

## Rewrite

Fix every audit finding. Start with the governing thought or recommendation and explicit requested action. Use answer → roughly three supporting arguments → their evidence. Compress essential background into SCQA, give real decision options when relevant, move nonessential detail to **Additional detail** or **Appendix**, and tighten the prose for scanning.

For pasted or in-conversation text, return the rewritten version and a short **What changed** bullet list focused on structural changes. If the user asks only for a restatement or rewrite—especially of a prior assistant response—return only the rewrite unless they request the audit or change summary.

For a file, first ask whether to overwrite it or create a sibling rewritten file unless the user already gave that instruction. Make the selected edit, then report a short diff-style summary of the structural changes.
