# Business Analyst: Solution Exploration

Two agent skills for moving from an unclear problem to a defensible solution decision.

```text
Problem + Context + Constraints
            |
         /explore
 Interrogate -> Ground -> Diverge
            |
      Solution Options
            |
         /decide
Verify -> Filter -> Compare -> Recommend
            |
      Solution Decision
```

## `/explore` - Interrogate, ground, diverge

Use when you have a problem, goal, opportunity, or requirement but have not committed to a solution.

`/explore`:
- asks exactly one highest-impact material question at a time, then tests the answer for evidence, precision, conflicts, and consequences;
- uses a detective analogy for the interrogation process and requires a bounded analogy for every solution option;
- records each material `EQ-###` item with its purpose, status, evidence, dependencies, owner, and impact if unanswered;
- separates **hard constraints**, **preferences**, **assumptions**, and **unknowns**;
- distinguishes **Blocking** unknowns from **Conditional** unknowns, continuing only with unaffected exploration;
- lets the user answer now or defer a question to someone else;
- grounds the exploration using user-provided sources, AI research, or a hybrid path;
- prefers reliable and applicable evidence over repeated web opinion;
- generates materially different solution archetypes with stable `SO-###` IDs; and
- deliberately stops before ranking or choosing a winner.

Primary output: **Solution Options**.

## `/decide` - Filter, compare, recommend

Use after `/explore`, or whenever credible solution options already exist.

`/decide`:
- asks one highest-impact decision question at a time, then re-ranks transparently when an answer changes the case;
- records material `DQ-###` items with purpose, evidence, affected ranking, and unresolved impact;
- treats hard constraints as **gates, not weighted scoring factors**;
- compares only viable options using decision-relevant criteria;
- requires a Pugh matrix whenever at least two viable options remain, with a defensible baseline, defined criteria, importance levels, evidence-backed `+` / `0` / `-` / `?` cells, and solution comparison cards;
- uses detailed pairwise comparisons for the strongest two or three contenders;
- makes gains, sacrifices, and conditional trade-offs explicit;
- ranks viable `SO-###` options; and
- recommends one direction, a runner-up, confidence, and what could change the decision.

Primary output: **Solution Decision**.

## Core principles

1. **Do not solve the wrong problem.** Interrogate material ambiguity before ideating.
2. **Do not invent constraints.** Separate must-haves from preferences and assumptions.
3. **Ground before claiming best practice.** Prefer governing, primary, peer-reviewed, official, and authoritative sources when applicable.
4. **Diverge before converging.** Generate materially different approaches, not cosmetic variants.
5. **Hard constraints are gates.** An option that fails a mandatory constraint cannot win on score.
6. **Trade-offs matter more than fake precision.** Do not invent weights or objective-looking scores without meaningful inputs.
7. **Make uncertainty resumable.** Preserve stable questions, solution IDs, evidence, dependencies, materiality, and ranking changes when new information arrives.
8. **Explain without misleading.** Use analogies to clarify solutions, state where they break, and never treat them as evidence.

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
