# Cynefin

## Summary
Dave Snowden's sense-making framework. Sorts a problem into one of five domains - Clear, Complicated, Complex, Chaotic, or Confused (Aporetic) - because each domain demands a different response. The mistake is treating one kind of problem as if it were another.

## When it shines
- You don't yet know what kind of problem you have.
- Smart people are disagreeing about whether to plan, experiment, or just act.
- Past playbooks aren't working and you suspect the domain has shifted.

## When to avoid
- The problem is already crisply scoped and the right response is obvious.
- Pure prioritization questions - Cynefin sorts, it doesn't rank.

## The five domains

- **Clear** (formerly Obvious/Simple) - cause and effect are known. Best practice exists. Approach: **Sense → Categorize → Respond.**
- **Complicated** - cause and effect are knowable with analysis or expertise. Good practice exists. Approach: **Sense → Analyze → Respond.**
- **Complex** - cause and effect only visible in hindsight. No right answer; emergent patterns. Approach: **Probe → Sense → Respond.** Run safe-to-fail experiments.
- **Chaotic** - no discernible cause and effect. Act first to establish stability. Approach: **Act → Sense → Respond.**
- **Confused / Aporetic** - you don't know which domain you're in. Break the problem into pieces and sort each piece.

## The steps

1. State the problem in one sentence.
2. Ask: do I know the cause-and-effect relationship?
   - Known and obvious → Clear.
   - Knowable with effort → Complicated.
   - Only visible afterwards → Complex.
   - Not visible at all and the situation is urgent → Chaotic.
   - Genuinely unsure → Confused; decompose.
3. Name the matching response approach.
4. Check for category errors: is anyone on the team treating this as a different domain than you just identified?
5. Recommend the next move appropriate to the domain.

## Example

**Problem:** Adoption of PRFRM's new GEO engine is uneven across customers.

- Cause and effect: probably visible in hindsight but not predictable up-front. Different customers have different content stacks.
- Domain: **Complex**.
- Approach: Probe → Sense → Respond. Run 3-4 small experiments with different customer segments, measure, then double down on what shows signal.
- Category error to watch: treating this as Complicated (running a big analysis project) when the right move is small experiments.

## Output template

```
## Cynefin Analysis: [Problem]

**Domain:** [Clear / Complicated / Complex / Chaotic / Confused]
**Why:** [one sentence on the cause-and-effect read]

**Response approach:** [Sense-Categorize-Respond / Sense-Analyze-Respond / Probe-Sense-Respond / Act-Sense-Respond]

**Category errors to watch:** [what wrong domain might people be treating this as]

**So what:** [the move]
```
