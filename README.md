# Business Analyst: Solution Exploration

Two agent skills for moving from an unclear problem to a defensible solution decision.

```text
Problem + Context + Constraints
            ↓
         /explore
   Grill → Ground → Diverge
            ↓
      Solution Options
            ↓
         /decide
Verify → Filter → Compare → Recommend
            ↓
      Solution Decision
```

## `/explore` — Understand, ground, diverge

Use when you have a problem, goal, opportunity, or requirement but have not committed to a solution.

`/explore`:
- grills only material ambiguities that could change the problem, constraints, solution space, or later decision criteria;
- separates **hard constraints**, **preferences**, **assumptions**, and **unknowns**;
- lets the user answer now or defer a question to someone else;
- grounds the exploration using user-provided sources, AI research, or a hybrid path;
- prefers reliable and applicable evidence over repeated web opinion;
- generates materially different solution archetypes with stable `SO-###` IDs; and
- deliberately stops before ranking or choosing a winner.

Primary output: **Solution Options**.

## `/decide` — Filter, compare, recommend

Use after `/explore`, or whenever credible solution options already exist.

`/decide`:
- verifies that the decision basis is comparable;
- treats hard constraints as **gates, not weighted scoring factors**;
- compares only viable options using decision-relevant criteria;
- defaults to qualitative comparison to avoid false precision;
- makes gains, sacrifices, and conditional trade-offs explicit;
- ranks viable `SO-###` options; and
- recommends one direction, a runner-up, confidence, and what could change the decision.

Primary output: **Solution Decision**.

## Core principles

1. **Do not solve the wrong problem.** Grill before ideating when material ambiguity exists.
2. **Do not invent constraints.** Separate must-haves from preferences and assumptions.
3. **Ground before claiming best practice.** Prefer governing, primary, peer-reviewed, official, and authoritative sources when applicable.
4. **Diverge before converging.** Generate materially different approaches, not cosmetic variants.
5. **Hard constraints are gates.** An option that fails a mandatory constraint cannot win on score.
6. **Trade-offs matter more than fake precision.** Do not invent weights or objective-looking scores without meaningful inputs.
7. **Make uncertainty resumable.** Preserve stable question and solution IDs when new information arrives.

## Repository structure

```text
skills/
  solution-explore/
    SKILL.md
  solution-decide/
    SKILL.md
CHANGELOG.md
LICENSE
plugin.json
```

## Installation

Clone the repository, then copy or symlink the folders under `skills/` into your agent's skills directory.

```bash
git clone https://github.com/yosefdc7/Business-Analyst-solution-exploration.git
```

The `SKILL.md` files are the source of truth for behavior.
