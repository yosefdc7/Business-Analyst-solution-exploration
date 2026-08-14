# Changelog

Notable changes to **Business Analyst: Solution Exploration** are recorded here.

## 0.3.0 - 2026-08-14

### Changed
- Strengthened `/decide` with a one-question-at-a-time decision interrogation loop, including the explicit rule: “Ask one highest-impact decision question at a time.”
- Added a resumable `DQ-###` decision-question register for ranking-sensitive evidence, priorities, and unresolved impacts.
- Added transparent partial re-ranking when a new answer, constraint, priority, evidence item, or option changes the decision model.
- Added optional Pugh-matrix comparison with a stated reference option, defined criteria, `+` / `0` / `-` scores, evidence for each score, and safeguards against false precision.
- Preserved hard constraints as pre-comparison gates and made Pugh totals non-decisive.

## 0.2.0 - 2026-08-13

### Changed
- Strengthened `/explore` with a one-question-at-a-time interrogation loop that tests answers for evidence, precision, conflicts, and consequences.
- Added the resumable `EQ-###` question register with status, materiality, evidence status, dependencies, suggested respondent, and unanswered impact.
- Added challenge rules for ownership versus contribution, evidence quality, shared or missing evidence, double counting, circular logic, proxy misuse, incentive problems, and observable success evidence.
- Replaced non-blocking handling with Blocking and Conditional continuation rules, and added explicit stop conditions before solution divergence.
- Clarified that `/explore` can express viability conditions without ranking or recommending an option.

## 0.1.0 - 2026-08-12

### Added
- `/explore` skill with **Grill -> Ground -> Diverge** workflow.
- Stable `EQ-###` question IDs and `SO-###` solution IDs.
- Deferred-question handling for inputs that must come from someone else.
- Explicit separation of hard constraints, preferences, assumptions, and unknowns.
- User-provided, AI-researched, and hybrid grounding paths.
- Reliable / Supporting / Weak source treatment for exploration.
- `/decide` skill with **Verify -> Filter -> Compare -> Recommend** workflow.
- Hard-constraint gating before comparison.
- Qualitative comparison by default to avoid false precision.
- Explicit gain/give-up and conditional trade-off analysis.
- Ranked recommendation, runner-up, confidence, decision conditions, and next validation.
- Resume behavior for both exploration and decision artifacts.
