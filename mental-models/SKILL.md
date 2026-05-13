---
name: mental-models
description: Apply one or more mental models or analytical frameworks (Premortem, WICS, Cynefin, Double-Loop Learning) to a decision, plan, problem, strategy, or post-mortem. Use this skill whenever the user asks to "analyze," "pressure-test," "stress-test," "look at this through the lens of," "premortem," "do a premortem on," "apply X framework," "think through with multiple frameworks," "what could go wrong with," or names any of the included frameworks by name. Also use when the user describes a substantive decision, plan, or strategic question and would clearly benefit from structured analysis, even if they do not name a framework explicitly. Prefer this skill over ad-hoc analysis whenever the request is about evaluating a plan, decision, or system rather than just answering a factual question.
---

# Mental Models

A library of structured analytical frameworks. Use one framework when the user names one or when the problem clearly maps to a single framework. Use two or three frameworks together when the problem is large, ambiguous, or high-stakes and would benefit from multiple angles.

This is part of an evolving series. New frameworks are added as the companion articles are published. Current set: Premortem, WICS, Cynefin, Double-Loop Learning.

## How to use this skill

1. **Identify which framework(s) apply.** Either the user named them, or you pick based on the framework selector below.
2. **Read only the framework files you need** from `references/`. Do not load all of them.
3. **Apply each framework** following the steps in its file.
4. **If using more than one,** synthesize using the multi-lens guidance further down.
5. **Produce output** in the format specified by each framework file. If multi-lens, use the synthesis format.

## Framework selector

If the user names a framework, use it. Otherwise, match the problem to a framework using this table. Read the linked file before applying.

| Framework | File | Use when the problem is... |
|---|---|---|
| **Premortem** | `references/premortem.md` | A plan, launch, or decision that hasn't happened yet. You want to surface failure modes before committing. |
| **WICS** | `references/wics.md` | You need to break a fuzzy situation into Wisdom / Intelligence / Creativity / Synthesis to figure out what kind of thinking it needs. |
| **Cynefin** | `references/cynefin.md` | You don't know what kind of problem you're looking at - simple, complicated, complex, or chaotic. Decide the regime before picking a response. |
| **Double-Loop Learning** | `references/double-loop-learning.md` | Something failed or keeps failing, and you suspect the governing assumptions (not just the actions) are wrong. |

If the user describes a substantive problem without naming a framework, propose 1-3 candidates with a one-line reason for each, then ask which they want (or proceed with the strongest fit if they've said "you pick").

## Single-framework workflow

1. Read the framework file from `references/`.
2. Restate the problem in one sentence so the user can confirm framing.
3. Follow the steps in the framework file.
4. Use the output format from that file.
5. End with one explicit "so what" - the action, decision, or next question this analysis surfaces.

## Multi-framework workflow

When applying two or three frameworks together, pick the synthesis pattern based on the problem shape. Choose, don't ask:

- **Sequential (each lens fully, then synthesis)** - use when the frameworks answer different questions that don't overlap much. Example: Cynefin (what kind of problem?) + Premortem (how could it fail?). Apply Cynefin fully, then Premortem fully, then a short synthesis section.
- **Interleaved (compare lens-by-lens on the same dimensions)** - use when the frameworks examine the same object from different angles and the contrast is the point. Example: WICS and Double-Loop on a repeated strategic miss - WICS surfaces which kind of thinking was missing, Double-Loop surfaces which governing assumption was wrong, and the overlap is where the actual lesson sits.
- **Lens-then-counter-lens** - use when one framework generates a position and the other stress-tests it. Example: WICS produces a recommendation; Premortem then attacks it.

Pick the pattern in one sentence at the top of the response so the user sees the choice, then execute it.

**Synthesis section is required for multi-lens.** End with 3-5 lines that name what the frameworks agreed on, where they disagreed, and what the resulting recommendation is. No bullet padding.

## Output style

- Lead with the framework name(s) and the synthesis pattern if multi-lens.
- Use the headings the framework file specifies. Don't invent new ones.
- Skip preamble. No "Great question" or "Let's dive in."
- Each framework section ends with its own "so what" line.
- If the user asks for a specific deliverable (memo, slide outline, post draft), apply the framework internally and present in their requested format - don't show the scaffolding unless they want it.

## When NOT to use this skill

- Pure factual lookups ("what year did X happen").
- Code generation, debugging, or technical implementation - unless the user explicitly wants a framework applied to an architecture decision.
- Short emotional or conversational exchanges.
- Tasks where the user has already done the analysis and just wants drafting help.

## Adding a new framework

To extend this skill with a new framework:
1. Add a new file in `references/` following the structure of existing files (summary, when it shines, when to avoid, the steps, example, output template).
2. Add a row to the Framework selector table above.
3. Update the description in the YAML frontmatter to include the new framework name.
4. Keep each framework file under 200 lines so loading several at once stays cheap.
