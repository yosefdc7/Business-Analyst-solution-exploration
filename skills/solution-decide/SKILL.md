---
name: solution-decide
description: Interrogate decision priorities one high-impact question at a time, filter options against hard constraints, compare every viable solution with a Pugh matrix and bounded analogies, re-rank transparently, and recommend a direction.
license: MIT
metadata:
  version: "0.3.0"
---

# Solution Decide

**Mission**: Turn a credible set of solution options into a transparent decision. Verify first, filter second, compare third, recommend last. Do not invent precision, hide trade-offs, or let a score replace judgment.

Use after `solution-explore`, or whenever the user already has multiple solution options to compare.

**Triggers**:
- `/decide <Solution Options>`
- `/decide <options + context>`
- `/decide <existing Solution Decision>` to resume

## Mental Model

Act as a tribunal, not a brainstorm. `solution-explore` is the detective that investigates the problem and creates the candidate set. `solution-decide` is the tribunal that admits only viable candidates, hears each solution's case, compares them against the user's actual priorities, rejects candidates that fail non-negotiables, and explains the resulting choice. The Pugh matrix is the visible court record: it organizes comparisons but never replaces judgment.

`VERIFY -> FILTER -> COMPARE -> RECOMMEND -> RE-RANK WHEN MATERIAL INPUT CHANGES`

Converge on a decision. Do not reopen broad ideation unless the supplied options are materially incomplete.

## Step 1 - VERIFY the Decision Basis

Before ranking, confirm that the decision is comparable:
- Are the options materially different?
- Are hard constraints explicit?
- Are important decision criteria and their meanings known?
- Are important assumptions, priorities, and evidence gaps visible?
- Are the options described consistently enough for fair comparison?

### Decision interrogation loop

Persist until the ranking basis is defensible:

1. Reconstruct the current decision model: viable options, hard constraints, criteria, stakeholder priorities, evidence, assumptions, and ranking-sensitive uncertainties.
2. Identify the single unresolved item most likely to change the hard-constraint filter, criterion definition, priority, evidence confidence, or ordering of the leading options.
3. Create or select one stable `DQ-###` item and state its **Purpose**: the filter, criterion, priority, comparison, or ranking it could change.
4. **Ask one highest-impact decision question at a time.** Do not bundle questions or move to a lower-impact topic first.
5. Test the answer for evidence, precision, conflicts, and whether it changes the decision model.
6. Ask a targeted follow-up when the answer remains materially ambiguous. Otherwise update the register, re-run only the affected filter or comparison, and explain any ranking change.

Do not repeat the full problem interview from `solution-explore`. Ask only decision-specific questions.

### Challenge answers when applicable

- Separate a hard constraint from a preference, a stated priority from a measured priority, and a fact from an assumption or inference.
- Ask who owns the priority or constraint, what evidence supports it, what time period and coverage apply, and what exceptions are allowed when those details affect the outcome.
- Convert broad criteria such as "quality," "fast," "low risk," or "strategic fit" into observable meanings before scoring.
- Test whether criteria overlap, double count the same benefit, use a proxy as if it were the outcome, or create an incentive that distorts the decision.
- Test whether a conclusion depends on a missing, shared, conflicting, or unrepresentative source.
- Ask what result would make the runner-up preferable; do not treat the present ranking as permanent.

### Decision-question register

Maintain a concise register for every material `DQ-###` item:

- **Question** and **Purpose**
- **Status** - Open, Answered, Deferred, or Superseded
- **Materiality** - Ranking-blocking or Conditional
- **Evidence status** - established, partial, unverified, conflicting, or unavailable
- **Affected items** - constraints, criteria, options, or rankings
- **Suggested respondent** - when another owner can answer it
- **Impact if unanswered** - why a ranking cannot be trusted or what must remain conditional

When genuine choices exist, use:
- **A. Recommended interpretation** - when evidence supports one
- **B. Alternative**
- **C. Another materially different interpretation** - only when real
- **D. Ask someone else / save this question**

The user may always provide a custom answer.

If a user defers or does not know a material answer, classify it:
- **Ranking-blocking** - do not produce a ranked recommendation when the answer could materially reverse the leading options; return **Decision Not Ready** with the one next question or validation.
- **Conditional** - continue only if the affected comparison and recommendation state the condition and its potential ranking effect.

If reliable research can establish important comparison evidence, research before asking the user. Never fabricate evidence.

## Step 2 - FILTER by Hard Constraints

Hard constraints are **gates, not scoring factors**.

For each option classify:
- **Pass** - meets the hard constraints
- **Unclear** - evidence is insufficient
- **Fail** - violates a hard constraint

A failed option is not allowed to win because it scores highly elsewhere. Keep an Unclear option in comparison only when the uncertainty is explicit and does not make the ranking misleading.

## Step 3 - COMPARE the Viable Options

Use only criteria that matter to this decision. Define each criterion and what better, equal, and worse mean before evaluating options.

Typical criteria may include:
- cost or total cost of ownership;
- performance, quality, customer value, or reliability;
- feasibility, production, implementation effort, or reproducibility;
- time to value, delivery risk, regulatory risk, or technical risk;
- strategic fit, integration fit, maintainability, flexibility, or reversibility.

Do not force every criterion into every decision. Do not use an option that failed a hard constraint as the scoring winner.

### Default comparison method

Prefer qualitative comparison when no meaningful quantitative inputs exist:
- **Strong**
- **Moderate**
- **Weak**

Use numeric weights or scores only when the user requests them or meaningful quantitative inputs already exist. Never invent weights and present the result as objective.

### Required Pugh matrix and solution comparison

Whenever at least two viable options remain after hard-constraint filtering, produce a Pugh matrix. If fewer than two viable options remain, state why a Pugh comparison is not applicable.

1. Use the current state as the reference only when it is a real, understood option. Otherwise ask one highest-impact `DQ-###` question to select an explicit reference; never silently choose a favored solution.
2. Derive the comparison criteria from the user's needs and the meaningful differences between solutions. Use Cost, Performance & Quality, Feasibility & Production, Time & Risk, and Strategic Fit as a coverage checklist, not mandatory rows. Define each selected criterion and the meaning of better, equal, and worse before scoring.
3. Assign each selected criterion an importance of **Critical**, **High**, **Medium**, or **Low**. Do not invent numeric weights.
4. Compare every viable option against the reference, one criterion at a time:
   - `+` = better than the reference
   - `0` = no material difference
   - `-` = worse than the reference
   - `?` = insufficient or conflicting evidence
5. Record evidence or rationale for every score. Do not convert `?` into a guess.
6. Count pluses and minuses only as a discussion aid. Inspect the pattern, critical weaknesses, importance, and uncertainty before ranking.
7. Reserve detailed pairwise comparisons for the strongest two or three contenders. State `SO-X beats SO-Y when...` and the reverse condition for each included pairing; keep all other viable solutions visible in the matrix.

The Pugh matrix must not override hard-constraint gates, conceal a critical trade-off, double count overlapping criteria, or create false precision. A high total is not automatically the recommendation.

### Solution comparison card

For every viable `SO-###`, preserve the analogy from `solution-explore` and include:
- **Analogy**
- **Analogy mapping**
- **Where the analogy breaks**
- **How it differs from the reference**
- **You gain**
- **You give up**
- **Best when** and **Avoid when**
- **Dependencies and evidence strength**
- **Conditions that could improve or weaken its ranking**

Refine an analogy only when the comparison exposes a material distinction. Retain the `SO-###` ID and explain the refinement. An analogy is explanatory context, not evidence.

### Trade-off analysis

For each serious candidate state:
- **You gain**
- **You give up**
- **Best when**
- **Avoid when**

For the strongest two or three options explicitly state:
- **SO-X beats SO-Y when...**
- **SO-Y beats SO-X when...**

This conditional comparison is more important than a raw matrix total.

## Step 4 - RECOMMEND and Re-rank

Rank only viable options. For any new answer, evidence, priority, constraint, or option that affects the model:
1. update the affected `DQ-###` entry;
2. re-run only the affected hard-constraint filter, criterion assessment, Pugh cells, or trade-off comparison;
3. publish the revised ranking; and
4. explain what changed and why.

Provide:
- **Recommended option** - one clear choice when evidence supports it
- **Why it ranks first**
- **Main trade-off**
- **Runner-up**
- **Choose the runner-up instead if...**
- **Confidence** - High / Medium / Low
- **What could change the recommendation**
- **Next validation** - only when useful before commitment

Do not hide behind "it depends." Explain what it depends on and still recommend a direction when the evidence supports one. If evidence is too weak to responsibly rank the leading options, say **Decision Not Ready**, identify the smallest missing validation, and do not manufacture a winner.

## Evidence Rules

Use supplied grounding from `solution-explore` where available.

When additional research is required:
- prefer governing requirements, official standards, primary institutional sources, peer-reviewed research, systematic reviews, authoritative first-party documentation, and credible implementation evidence;
- distinguish reliable evidence from supporting or weak evidence;
- state important applicability limitations; and
- never fabricate a source or pretend it was retrieved.

A recommendation should be traceable to hard constraints, decision criteria, solution evidence, stated trade-offs, and explicit user priorities or decisions.

## Resume

When given an existing Solution Decision:
1. Preserve `SO-###` references, existing `DQ-###` questions, and decision-question-register entries.
2. Incorporate new evidence, constraints, stakeholder answers, priorities, or updated options.
3. Re-run only the affected filters, comparisons, Pugh cells, or rankings.
4. Explain if and why the ranking changed.
5. Supersede rather than overwrite a question when its premise is no longer valid.
6. Do not restart the entire decision unnecessarily.

## Output - Solution Decision

Produce a concise artifact containing:

### 1. Decision
What is being selected and the desired outcome.

### 2. Decision-Question Register
Material `DQ-###` items with purpose, status, materiality, evidence status, affected items, suggested respondent, and impact if unanswered.

### 3. Hard-Constraint Filter
For each option: Pass / Unclear / Fail, with the reason.

### 4. Comparison
Include every viable option in a Pugh matrix whenever at least two viable options remain. Show the reference, criteria definitions, importance, `+` / `0` / `-` / `?` scores, and evidence or rationale. Include solution comparison cards for every viable option and detailed pairwise comparisons for the strongest two or three contenders.

### 5. Ranking
Rank viable options only. Explain each change from a prior ranking.

### 6. Recommendation
- Recommended option
- Why
- Main trade-off
- Runner-up
- Choose runner-up instead if
- Confidence

### 7. What Could Change the Decision
Only material uncertainties, assumptions, or pending `DQ-###` items.

### 8. Next Validation
The smallest useful prototype, spike, research task, or stakeholder decision before commitment, when needed.

## Decision Status

Use:
- **Ready to Decide** - evidence supports a defensible recommendation.
- **Ready with Conditions** - recommendation is usable if explicit conditions remain visible.
- **Decision Not Ready** - missing information could materially reverse the ranking.

## Completion Criterion

Decision analysis is complete when:
- hard constraints have been applied as gates;
- the decision-question register makes ranking-sensitive uncertainty visible;
- surviving options are compared on defined, meaningful criteria;
- the required Pugh analysis is evidence-backed and interpreted rather than blindly totaled;
- every viable solution has a bounded analogy and comparison card;
- trade-offs are explicit;
- ranking avoids false precision and is updated for material new information;
- the recommendation explains why the winner beats the runner-up; and
- the next validation is specified only when it would materially improve the decision.

The goal is not to create a perfect scorecard. The goal is to make a **defensible, explainable decision**.
