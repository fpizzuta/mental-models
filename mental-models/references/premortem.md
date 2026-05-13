# Premortem

## Summary
Imagine the plan has already failed. Work backwards from that failure to surface the causes now, while you can still act on them. Developed by Gary Klein; popularized by Daniel Kahneman.

## When it shines
- A plan, launch, decision, or commitment that hasn't happened yet.
- High-stakes or hard-to-reverse moves.
- Teams that have rallied around a plan and stopped questioning it.
- Anytime "what could go wrong" needs to feel safe to say out loud.

## When to avoid
- Already-completed work - use a post-mortem or Double-Loop Learning instead.
- Trivially reversible decisions where the analysis costs more than the failure would.
- Pure exploration where there is no plan yet to attack.

## The steps

1. **Set the scene.** Name the plan, decision, or initiative in one sentence. State the time horizon (e.g., "six months from launch").
2. **Declare the failure.** Write: "It is [date]. The [plan] has failed. It is now obvious in hindsight that..." Be specific about what failure looks like - not just "it didn't work" but what the visible signs are (revenue, adoption, churn, missed deadline, reputational hit).
3. **Generate causes.** List the reasons the failure happened. Push for at least 8-12 before filtering. Cover at minimum:
   - **Assumption failures** - things we believed that turned out wrong.
   - **Execution failures** - things we tried to do but couldn't.
   - **External shocks** - things that happened to us.
   - **Adoption failures** - users, customers, or stakeholders didn't behave as expected.
   - **Internal failures** - team, politics, dependencies, attention.
4. **Rank by likelihood and severity.** For each cause, mark High / Medium / Low on both. The High/High causes are the ones to act on first.
5. **Convert to actions.** For each top-ranked cause, produce one of: a mitigation, a detection signal (what would tell us early this is happening), or a kill criterion (the condition under which we stop).

## Example

**Plan:** Launch PRFRM's LinkedIn Ads integration as the third paid channel.
**Failure declaration:** "It is November 2026. The LinkedIn Ads integration launched but adoption stalled at <10% of active accounts. It is now obvious in hindsight that..."

**Causes (compressed):**
- The `adAnalytics` API rate limits made the data freshness story weaker than Google/Meta. [Assumption, H/H]
- B2B clients we expected to convert were already locked into HubSpot/Salesforce attribution. [Adoption, H/M]
- The four-layer intelligence stack didn't extend cleanly to LinkedIn's data model. [Execution, M/H]
- LinkedIn changed API terms mid-build. [External, L/H]

**Top action:** Validate the freshness story against rate limits before committing build resources. Detection signal: if API testing in week 2 shows >4hr lag, escalate before week 4.

## Output template

```
## Premortem: [Plan]

**Time horizon:** [when failure is being imagined from]

**Failure declaration:**
It is [date]. [Plan] has failed. The visible signs: [specifics].

**Causes**

| Cause | Category | Likelihood | Severity |
|---|---|---|---|
| ... | Assumption / Execution / External / Adoption / Internal | H/M/L | H/M/L |

**Top three to act on now**
1. [Cause] → [mitigation, detection signal, or kill criterion]
2. ...
3. ...

**So what:** [the one thing that changes about the plan because of this analysis]
```
