---
name: solution-explore
description: Interrogate an unclear problem one material question at a time, ground its logic and evidence, and generate distinct solution options without prematurely ranking them.
license: MIT
metadata:
  version: "0.2.0"
---

# Solution Explore

**Mission**: Turn an unclear problem into a well-grounded set of genuinely different solution options. Interrogate first, research second, diverge third. Do not rank or select a winner; that belongs to `solution-decide`.

Use when the user has a problem, goal, opportunity, or requirement but has not yet committed to a solution.

**Triggers**:
- `/explore <problem or context>`
- `/explore <existing Solution Options>` to resume

## Core Flow

`GRILL -> GROUND -> DIVERGE`

Ask only questions that could materially change the problem definition, constraints, solution space, or later decision criteria.

## Step 1 - GRILL the Problem

Reconstruct:
- **Problem** - what is happening now and why it matters
- **Desired outcome** - what should be different
- **Scope / exclusions**
- **Users / stakeholders**
- **Hard constraints** - a viable solution must satisfy them
- **Preferences** - important but negotiable
- **Assumptions** - believed true but not established
- **Unknowns** - missing information that could change the solution space
- **Decision criteria** - factors likely to matter later when choosing

Do not treat a preference as a hard constraint without evidence.

### Interrogation loop

Persist until the problem model is coherent enough to diverge. Do not substitute a large upfront questionnaire for this loop:

1. Reconstruct the current problem model from known facts, evidence, preferences, assumptions, unknowns, and contradictions.
2. Identify the highest-impact unresolved claim, ambiguity, dependency, owner, metric, boundary, or exception.
3. Create or select one stable `EQ-###` question and state its **Purpose**: the problem definition, hard constraint, scope boundary, evidence source, decision criterion, or solution-family assumption that its answer could change.
4. Ask exactly that one material question.
5. Test the answer for evidence, precision, conflicts, and downstream implications.
6. Ask a targeted follow-up when the answer remains materially ambiguous. Otherwise update the model and repeat with the next highest-impact question.

Do not ask a question merely for coverage. Do not move to an unrelated question while an answer leaves a material logical gap.

### Challenge answers when applicable

- Distinguish an observed fact, measured evidence, stakeholder preference, assumption, and inference. Do not present one as another.
- Ask for the authoritative owner, source, time period, coverage, approval authority, and exceptions when they affect credibility or applicability.
- Separate ownership from contribution, outcome, cost, responsibility, and causation; do not assume one proves another.
- Test how a proposed rule handles shared, baseline, unmappable, missing, or contradictory evidence.
- Surface double counting, circular logic, proxy misuse, and incentive problems before treating a rule as viable.
- Convert vague success language into observable outcomes and acceptance evidence.

### Question register

Maintain a concise register for every material `EQ-###` item:

- **Question** and **Purpose**
- **Status** - Open, Answered, Deferred, or Superseded
- **Materiality** - Blocking or Conditional
- **Evidence status** - established, partial, unverified, conflicting, or unavailable
- **Dependencies** - the facts, questions, or options affected
- **Suggested respondent** - when another owner can answer it
- **Impact if unanswered** - what cannot be established, compared, or described credibly

When genuine interpretations or paths exist, use:
- **A. Recommended interpretation** - when evidence supports one
- **B. Alternative**
- **C. Another materially different interpretation** - only when real
- **D. Ask someone else / save this question**

The user may always provide a custom answer.

If the user chooses D or does not know:
1. Mark the question **Deferred**.
2. Record the suggested respondent when reasonably inferable.
3. Classify it as **Blocking** or **Conditional**.
4. State the impact if unanswered.

For a **Blocking** item, do not produce a credible option set until it is answered; return **Needs More Input** with the single next question. For a **Conditional** item, continue only with unaffected work and label every affected option with the condition and its impact.

### Stop conditions before DIVERGE

Proceed to solution options only when all of the following are true:
- the problem model and desired outcome are coherent;
- scope boundaries and hard constraints are explicit and non-conflicting;
- material evidence gaps and their status are visible;
- no unanswered Blocking question prevents a credible option set; and
- enough information exists to describe distinct, credible solution archetypes.

Otherwise, return **Needs More Input** and ask only the single highest-impact open Blocking question.

## Step 2 - GROUND the Exploration

Ask how the user wants to ground the solution space:

- **A. Provide sources** - upload/share internal playbooks, approved PPMs, policies, studies, standards, reference architectures, product requirements, or other trusted material.
- **B. Search for reliable sources** - research authoritative sources and existing solution patterns.
- **C. Hybrid** - use supplied sources first, then research gaps.

When researching:
1. Prefer governing requirements, official standards, primary institutional sources, peer-reviewed research, systematic reviews, authoritative first-party documentation, and credible existing implementations.
2. Prefer primary sources over summaries.
3. Check applicability to the actual context.
4. Distinguish **Reliable**, **Supporting**, and **Weak** sources.
5. Do not present repeated web opinion as a best practice.
6. Never fabricate a source or pretend it was retrieved.

If search/retrieval tools are unavailable, ask the user to provide sources or clearly label the exploration as **Reasoning-only / Not externally grounded**.

User approval is not required for every source before exploration can continue. However, make the material sources that influenced the solution options visible so the user can challenge them.

## Step 3 - DIVERGE into Solution Options

Generate **materially different solution archetypes**, not minor variants of the same idea.

Good divergence might include:
- adopt an existing solution;
- customize an open-source solution;
- build a thin internal solution;
- extend an existing internal platform;
- change the process rather than add technology;
- use a managed/commercial solution; or
- combine approaches when the hybrid is materially distinct.

Do not force a fixed number of options. Prefer a small set of credible, distinct approaches over a long brainstorm.

Every viable option receives a stable `SO-###` ID.

For each option capture:
- **Approach**
- **How it solves the problem**
- **Best fit / when it works well**
- **Main advantages**
- **Main trade-offs**
- **Hard-constraint fit** - Meets / Unclear / Fails
- **Key dependencies**
- **Evidence / source basis**
- **Important unknowns and conditions**

If an option clearly violates a hard constraint, either exclude it or keep it only as **Non-viable under current constraints** when showing it teaches something useful.

### Boundary

`solution-explore` must **not rank the options, choose a winner, or force convergence**.

It may state what evidence or conditions make an option viable, non-viable, or unclear. It may say which options are viable enough to pass to `solution-decide`. It must not turn that assessment into a ranking or recommendation.

## Resume

When given an existing Solution Options artifact:
1. Preserve existing `EQ-###`, `SO-###`, question-register entries, and answers.
2. Incorporate new answers, constraints, sources, or context.
3. Update dependencies, evidence status, and materiality only for affected items.
4. Supersede rather than overwrite a question when its premise is no longer valid.
5. Re-open only affected parts of the exploration.
6. Add new options only when new information materially expands the solution space.
7. Do not restart completed work unnecessarily.

## Output - Solution Options

Produce a concise artifact containing:

### 1. Problem
- Problem
- Desired outcome
- Scope / exclusions

### 2. Constraints
- Hard constraints
- Preferences
- Assumptions
- Unknowns

### 3. Decision Criteria
Factors likely to matter when selecting later.

### 4. Question Register
Material `EQ-###` items with purpose, status, materiality, evidence status, dependencies, suggested respondent, and impact if unanswered.

### 5. Grounding
Material reliable/supporting sources and important limitations.

### 6. Solution Options
For each `SO-###`: approach, fit, advantages, trade-offs, dependencies, evidence, and unknowns.

### 7. Questions for Others
Deferred `EQ-###` items only.

### 8. Exploration Status
Use:
- **Ready for Decision** - enough viable, distinct options and decision criteria exist for comparison.
- **Ready for Decision with Conditions** - comparison can proceed if listed assumptions/unknowns remain explicit.
- **Needs More Input** - missing information materially prevents a credible solution set.

## Completion Criterion

Exploration is complete when:
- the problem and desired outcome are clear enough to generate solutions responsibly;
- hard constraints are separated from preferences and assumptions;
- material unknowns are explicit or deferred;
- the question register makes materiality, evidence, dependencies, and unanswered impacts visible;
- no unanswered Blocking question has been bypassed;
- the exploration is grounded in visible evidence when reliable sources are available;
- the solution set contains credible, materially different approaches; and
- the skill stops before ranking or recommending a winner.

The goal is not to produce many ideas. The goal is to produce the **right solution space** for a high-quality decision.
