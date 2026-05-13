# Double-Loop Learning

## Summary
Chris Argyris's framework. Single-loop learning asks "are we doing the thing right?" Double-loop learning asks "are we doing the right thing, and are the governing assumptions still true?" Most teams stay in the single loop because the double loop is uncomfortable.

## When it shines
- A pattern of failures, not a single failure.
- Fixes keep working briefly and then the problem returns.
- A team is iterating fast but on the wrong target.
- Post-mortems where the surface causes feel insufficient.

## When to avoid
- A one-off failure with an obvious cause.
- Real-time tactical fires - single-loop is correct here.

## The two loops

- **Single loop:** Governing variables → Actions → Consequences. When consequences disappoint, change the actions. The governing variables (goals, assumptions, rules of the game) stay fixed.
- **Double loop:** When consequences disappoint, *also* examine the governing variables. Maybe the goal itself is wrong. Maybe the assumption that drove the action was wrong.

## The steps

1. **Name the disappointing consequence.** What outcome are you not getting?
2. **List the actions that produced it.** What did the team actually do?
3. **Surface the governing variables.** What goals, assumptions, or rules drove those actions? These are usually unstated. Ask: "We did X because we believed Y." Fill in Y.
4. **Test the governing variables.** For each one, ask: is this still true? Was it ever true? What evidence would change it?
5. **Decide which loop to operate in.**
   - If the governing variables hold, fix the actions (single-loop).
   - If a governing variable is wrong, change it before changing actions (double-loop).
6. **Name what gets discarded.** Double-loop learning has a cost - usually a strategy, identity, or commitment that has to be let go.

## Example

**Disappointing consequence:** Outcomes from AI rollouts at clients keep underperforming expectations even though the team is shipping faster.

- **Actions:** More features, more integrations, more pilot programs.
- **Governing variable:** "More AI capability = more value delivered." Unstated but it's driving every action.
- **Test it:** Look at outcomes by capability count. If clients with fewer, deeper integrations are outperforming clients with broader rollouts, the governing variable is wrong.
- **Loop:** Double. Discard "broad capability surface" as the goal. Replace with "depth of integration per use case."

## Output template

```
## Double-Loop Learning: [Pattern]

**Disappointing consequence:** [the outcome you keep not getting]

**Single-loop view (actions taken):**
- [action]
- [action]

**Governing variables (unstated assumptions driving those actions):**
- We did X because we believed [assumption].
- ...

**Test each:**
| Assumption | Still true? | Evidence |
|---|---|---|
| ... | Yes / No / Unclear | ... |

**Verdict:** Single-loop or Double-loop.
**If double-loop:** What gets discarded → [the commitment, strategy, or belief being given up].

**So what:** [the change in direction, not just the change in tactics]
```
