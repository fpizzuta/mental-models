# WICS

## Summary
Wisdom, Intelligence, Creativity, Synthesis. A framework from Robert Sternberg for asking what kind of thinking a situation actually needs, instead of defaulting to the kind you're best at. Each lens asks a different question of the same problem.

## When it shines
- Fuzzy situations where you're not sure what kind of problem you have.
- Decisions where smart people on the same team are talking past each other - usually because they're operating in different quadrants.
- AI-era problems where the "obvious" intelligence move (more data, more analysis) is the wrong response.
- Strategy reviews where the plan is technically sound but feels off.

## When to avoid
- Pure execution tasks where the question is already crisp.
- Time-pressured tactical decisions - this is a structuring tool, not a fast tool.

## The four lenses

- **Wisdom** asks: *Should we do this at all?* What are the second-order effects, the people affected, the values at stake, the long-term consequences? Wisdom is the one most often skipped.
- **Intelligence** asks: *What do we know and what can we figure out?* Data, analysis, pattern recognition, expertise. This is the default mode most teams operate in.
- **Creativity** asks: *What else could this be?* What's the non-obvious framing, the option no one has put on the table, the analogy from a different domain?
- **Synthesis** asks: *How do these fit together?* Pulls Wisdom, Intelligence, and Creativity into a coherent recommendation. Without Synthesis, the other three are just parallel monologues.

## The steps

1. **State the problem in one sentence.**
2. **Apply each lens in order: W → I → C → S.** Resist jumping to Intelligence first even though it's tempting.
3. **For each of W, I, C, write 3-5 specific observations.** Not generic statements - things that are true about *this* problem.
4. **In Synthesis, name the dominant tension.** WICS analyses almost always surface a tension - usually Wisdom vs. Intelligence, or Creativity vs. Intelligence. Name it.
5. **Resolve to a recommendation.** Synthesis isn't a summary, it's a decision.

## Example

**Problem:** Should Inveniam build a lease review agent for commercial real estate documents as the next agentic capability?

- **Wisdom:** Lease review touches legal liability. If the agent miscategorizes a clause, who is accountable? Does shipping this before the verification layer is mature put trust at risk? The customers most likely to adopt are also the ones least forgiving of errors.
- **Intelligence:** The document set is bounded and structured. Existing extraction benchmarks suggest 85-90% accuracy is achievable on standard clauses. We have the platform pieces. RIA market is asking for it.
- **Creativity:** What if this isn't an agent at all but a verification layer that sits on top of human review? Or a "second reader" that only flags disagreements with the human? Reframing from "replace" to "double-check" changes the failure profile entirely.
- **Synthesis:** Tension is Wisdom (liability) vs. Intelligence (it's technically doable). Creativity dissolves it - reframe as second-reader. Recommendation: build as a flagging layer, not a replacement, and measure agreement rate with human reviewers as the leading indicator.

## Output template

```
## WICS Analysis: [Problem]

**Wisdom** - *Should we?*
- [observation]
- [observation]

**Intelligence** - *What do we know?*
- [observation]
- [observation]

**Creativity** - *What else could this be?*
- [observation]
- [observation]

**Synthesis**
Dominant tension: [name it].
Recommendation: [the decision].

**So what:** [the action that follows]
```
