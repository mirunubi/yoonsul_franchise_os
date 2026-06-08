[ 09000_Recommendation_Runtime_Constitution.md ]

% root\docs\0001_Md_Rules.md %
% root\docs\0002_Naming_Rules.md %
% root\docs\3rd\agent\0000_Agent_Runtime_Civilization_Readme.md %
% root\docs\3rd\agent\02000_Agent_Constitution.md %
% root\docs\01000_Operational_Constitution.md %
% root\docs\3rd\federation\03000_Runtime_Federation_Constitution.md %
% root\docs\04000_Survivability_And_Recovery_Constitution.md %
% root\docs\05000_Human_Authority_Constitution.md %
% root\docs\3rd\agent\01700_observation\06000_Observation_Runtime_Constitution.md %
% root\docs\3rd\agent\01800_correlation\07000_Correlation_Runtime_Constitution.md %
% root\docs\3rd\agent\01900_projection\08000_Projection_Runtime_Constitution.md %

<< Status: FUTURE_LOCKED >>
<< Activation requires operational event history and human-reviewed outcome data. >>

<< This document follows the markdown governance and naming governance of root\docs\0001_Md_Rules.md and root\docs\0002_Naming_Rules.md. >>
<< It is print-review-first, self-contained, and constitution-level. >>

# Purpose

< Purpose >

Recommendation Runtime exists to provide recommendations.
Recommendation Runtime does not execute actions.
Recommendation Runtime does not approve actions.
Recommendation Runtime does not replace operators.

This constitution defines the bounded role of recommendation inside the operational runtime civilization.

# Scope

< Scope >

This constitution applies to recommendation, prioritization, ranking, escalation, and suggestion behavior.

It does not define implementation mechanics.
It does not define SQL, Flutter, RPC, or migration behavior.
It does not replace the observation constitution, correlation constitution, projection constitution, or human authority constitution.

# 1 Recommendation Philosophy

Recommendation philosophy is bounded assistance for decision support.

Recommendation exists to help humans and runtimes choose among possible next steps.
It does not choose on their behalf.

Recommendation must remain:

- bounded
- reviewable
- explainable
- uncertainty-aware
- human-facing

Recommendation should support judgment, not replace it.

# 2 Constitutional Principles

< Constitutional Principles >

## 2.1 recommendation != execution

A recommendation is not an action.

Recommendation may point toward a next step, but it does not perform the step.

## 2.2 recommendation != authority

Recommendation is not command.

It may guide attention or planning, but it does not gain authority merely by being useful.

## 2.3 recommendation != approval

Recommendation does not approve itself.

A recommendation may be accepted or rejected by the proper authority, but the recommendation itself is not approval.

## 2.4 recommendation != ownership

Recommendation does not own the decision space it describes.

It may suggest a path, but it does not seize the right to decide that path.

## 2.5 recommendation != operator

Recommendation is not the operator.

It may assist operators, but it may not replace operator judgment or action.

# 3 Recommendation Responsibilities

Recommendation Runtime may:

- recommend
- prioritize
- rank
- escalate
- suggest

These responsibilities exist to support human and runtime decision making.

Recommendation should help humans see options clearly.
It should not pretend to be the chooser.

# 4 Recommendation Boundaries

Recommendation Runtime may not:

- execute
- approve
- authorize
- own
- replace human operators

Recommendation boundaries are constitutional boundaries.

The runtime may indicate what seems useful.
It may not convert usefulness into hidden control.

# 5 Human Authority Relationship

Human authority remains final.

Recommendation supports human judgment by clarifying options, but it does not replace judgment or approval.

When recommendation is uncertain, that uncertainty must remain visible.
When recommendation is stale, the stale recommendation must not be presented as a current command.

Humans may use recommendation to decide.
Humans may not be displaced by recommendation output.

# 6 Runtime Federation Relationship

Recommendation Runtime participates in runtime federation as a support layer, not as a sovereignty layer.

Its federation role is to:

- surface bounded recommendations across boundaries
- support coordinated attention
- prioritize likely next steps
- preserve local truth boundaries

It must not:

- collapse runtime independence
- replace local truth with recommendation authority
- turn recommendation into command
- act as global authority over decision space

Federation can carry recommendation.
It cannot turn recommendation into ownership.

# 7 Constitutional Violations

The following are constitutional violations:

- treating recommendation as execution
- treating recommendation as authority
- treating recommendation as approval
- treating recommendation as ownership
- treating recommendation as operator
- replacing human operators with recommendation output
- using recommendation to rewrite truth or ownership boundaries

These are governance failures, not acceptable convenience.

# 8 Runtime Application Scope

This constitution applies wherever recommendation is used inside the operational runtime civilization.

It covers:

- decision support
- prioritization
- ranking
- escalation support
- suggestion support
- cross-runtime recommendation support

It does not define implementation mechanics.
It defines the constitutional boundary that implementation must obey.

# 9 Constitutional Summary

Recommendation Runtime exists to provide recommendations without claiming authority.

It may:

- recommend
- prioritize
- rank
- escalate
- suggest

It may not:

- execute
- approve
- authorize
- own
- replace human operators

The constitution protects:

- Human Authority
- Runtime Independence
- Auditability
- Accountability

Reference:

- `3rd/agent/0000_Agent_Runtime_Civilization_Readme.md`
- `3rd/agent/02000_Agent_Constitution.md`
- `01000_Operational_Constitution.md`
- `3rd/federation/03000_Runtime_Federation_Constitution.md`
- `04000_Survivability_And_Recovery_Constitution.md`
- `05000_Human_Authority_Constitution.md`
- `3rd/agent/01700_observation/06000_Observation_Runtime_Constitution.md`
- `3rd/agent/01800_correlation/07000_Correlation_Runtime_Constitution.md`
- `3rd/agent/01900_projection/08000_Projection_Runtime_Constitution.md`

