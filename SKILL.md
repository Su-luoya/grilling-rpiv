---
name: grilling-rpiv
description: Stress-test a plan through structured question rounds, then confirm a shared decision brief.
disable-model-invocation: true
---

# Grilling RPIV

Interrogate a plan, decision, or idea until the user can confirm a bounded decision brief. Be relentless about consequential assumptions, not the number of questions. Facts are your job; goals, trade-offs, and consent belong to the user. Use `ask_user_question` for decisions with honest alternatives; its live declaration governs the dialog mechanics. Keep investigation read-only until the user confirms the brief.

## 1. Bound and investigate

Establish the goal, success criteria, and scope from the request and available materials; an already-clear scope needs no opening questionnaire. Read relevant local materials and verify factual prerequisites before asking about them. An inaccessible source stays unknown: name the gap and ask for the smallest missing input, or keep the affected decision blocked. A running investigation blocks only its dependent questions.

Stress-test the proposed approach: challenge its premises, trace consequences and dependencies, and examine material failure modes, trade-offs, and validation. Add branches only when they affect the agreed goal; a scope change belongs to the user.

## 2. Maintain the design tree

Track each material question under a stable short name, its prerequisites, and one status:

- **Open:** a user decision remains.
- **Blocked:** a prerequisite decision or necessary fact is unresolved.
- **Settled:** a user answer, an explicit delegation, a verified fact, or a strict consequence resolves it; retain the source.
- **Deferred:** the user accepts postponement; retain the impact and a reopening condition.

A **critical** question is required for correctness, safety, feasibility, or the next irreversible step: resolve it, pause, or have the user narrow scope; deferral cannot dismiss it.

**Prune** a question only when a verified fact or a prior user decision entails its answer; your own recommendation or a plausible inference settles nothing. Questions postponed to a later round stay open or blocked, never pruned. The **frontier** is the open questions whose prerequisites are all settled; work this set rather than a fixed questionnaire.

A **receipt** is a one-line report of a status change: the outcome, its source, and the reason for any prune or reopening.

## 3. Compose and deliver one round

Select frontier questions up to the dialog's limit, prioritizing critical blockers, upstream choices that unlock work, and high-impact uncertainty. Leftover questions are a backlog; retain them.

Ask one decision per question, with enough context to expose its consequence; separate observed facts from hypotheses and proposed choices. Each option is defensible on its own, carrying its reason or cost in its description — an honest binary may have two, and a fabricated third only fills the dialog. Recommend a complete stance, not a topic; when evidence is insufficient, expose the uncertainty rather than manufacture a preferred answer.

Open the round with new receipts and one compact line naming what remains on the frontier. When an essential question has no honest candidate set, ask it as a concise prose round, kept separate from dialog rounds. If no question is ready, investigate or report the blocker.

## 4. Interpret answers and rebuild

Unambiguous user wording can qualify or override a selection; a conditional answer stays conditional, and any unresolved condition, ambiguity, or contradiction keeps the affected question open or blocked. A skipped or unanswered item stays unresolved; an explicit skip follows the deferral rules. Cancellation pauses the interview without implying rejection, agreement, or deferral: acknowledge it and wait; resume by rebuilding the frontier, not by replaying the same dialog.

After every answer, expand the tree: inspect the decision's consequences for newly exposed prerequisites, downstream choices, failure modes, and contradictions, and add the material ones with their dependencies; questions on an unresolved branch wait for a later round. When an answer or new evidence changes a premise, recheck its descendants and reopen decisions whose justification no longer holds, preserving unaffected ones. Report a receipt for every change — when opening the next round, or in the final brief — then recompute the frontier.

## 5. Confirm the decision brief

Finish only when all of these hold within the agreed scope:

- The goal, success criteria, and scope trace to the user's words, not assumption.
- The tree was re-expanded after the latest answers, not merely exhausted.
- Every critical question and its factual prerequisites are settled.
- Every other material question is settled or deferred with its impact and reopening condition.
- No contradiction, unresolved condition, unaccepted recommendation, or unsupported inference is being counted as settled.

An empty frontier is insufficient: blocked questions can leave it empty. When completion is blocked, report what is missing and continue the interview or stay paused; call it unfinished.

Present a compact brief: goal and scope, settled decisions and their rationale, material evidence and residual risks, approved deferrals, and the validation or next action. Ask for confirmation in one plain-text sentence, then wait. A revision reopens the affected questions and asks for confirmation again after resolving them.

Confirmation establishes shared understanding. Execute only work the user's request authorizes, under the host's normal permission rules; otherwise hand off the brief.
