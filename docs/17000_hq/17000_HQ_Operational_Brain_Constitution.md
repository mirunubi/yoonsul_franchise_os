[ 3rd_03000_HQ_Operational_Brain_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\hq\3rd_03000_HQ_Operational_Brain_Readme.md %

<< 3rd HQ operational brain constitution >>
<< governance and orchestration worldview only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines the operational governance and orchestration worldview of the HQ lane.
It describes how HQ sees, supports, coordinates, and intervenes without collapsing every other lane into HQ authority.

# 1 What HQ Operational Brain Is

< HQ Operational Brain >

HQ Operational Brain is the centralized governance and orchestration lane that supports the business across stores.
It is the place where policy, planning, cross-store visibility, and intervention guidance come together.

HQ Operational Brain exists to:

- coordinate the business at a higher level than any single store.
- preserve visibility across the fleet without replacing local execution.
- provide support, escalation, and governance direction.

# 2 Core Relationships

< HQ Relations >

HQ Operational Brain relates to the following concerns:

| concern | HQ relationship |
| ------- | ---------------- |
| ERP | back-office alignment, financial coordination, and organizational record control |
| Franchise Governance | policy, standards, rollout discipline, and multi-store consistency |
| Policy | the rules and guardrails that shape operational behavior |
| Forecasting | demand, labor, and capacity planning support |
| Supply Coordination | visibility into replenishment and upstream operational needs |
| Operational Visibility | cross-store monitoring and support awareness |
| HQ Intervention | escalation handling, support action, and high-level correction guidance |

Rules:

- ERP supports organizational alignment, but it does not replace runtime ownership on the floor.
- Franchise Governance sets consistency expectations across stores.
- Policy guides behavior, but policy alone is not runtime truth.
- Forecasting is support for planning, not a guarantee of future state.
- Supply Coordination connects HQ to upstream continuity without making HQ the supply lane itself.
- Operational Visibility should help people act, not hide reality.
- HQ Intervention must remain visible, scoped, and auditable.

# 3 HQ Orchestration Philosophy

< Orchestration Philosophy >

HQ orchestrates the business by coordinating policy, visibility, and support across many local runtimes.
It is a governance and alignment function, not a replacement for store execution or customer experience.

Principles:

- central visibility does not mean centralized execution.
- HQ can coordinate across lanes, but it should not erase lane boundaries.
- intervention should assist recovery and consistency, not silently overwrite local reality.
- orchestration must keep store-level and frontline ownership intact.

# 4 Relationship To Neighbor Lanes

< Neighbor Relations >

HQ Operational Brain relates to other lanes as follows:

- Frontline Runtime handles immediate capture, projection, and store-edge continuity.
- Store Operations handles local execution and store-level governance.
- Commerce / CRM handles customer and commerce continuity.
- SCM handles supply chain and manufacturing continuity.

HQ may see across these lanes, but it must not own them all.

# 5 Centralized Visibility vs Decentralized Execution

< Visibility And Execution >

HQ should be able to see the state of the business across stores and lanes.
That visibility is for governance, support, and orchestration.

Execution remains decentralized:

- stores execute locally.
- frontline surfaces handle immediate action.
- customer/commerce continuity belongs in the commerce lane.
- supply continuity remains in supply lanes.

HQ sees broadly, but execution stays where the work happens.

# 6 Operational Authority Boundaries

< Authority >

HQ owns the governance boundary, not every runtime truth.

Owned boundary examples:

- policy setting and rollout governance.
- cross-store visibility and planning support.
- intervention guidance and escalation handling.
- franchise consistency and operational standards.
- forecasting support and supply coordination visibility.

Not owned here:

- frontline capture or immediate projection authority.
- store-level execution authority.
- customer commerce experience ownership.
- SCM execution authority.
- deep constitutional governance that belongs in `3rd_00018`.

# 7 Escalation And Intervention Principles

< Escalation >

HQ intervention should exist for situations that need higher-level support or consistency.
Intervention is not the same as silent replacement.

Principles:

- escalation should be clear and scoped.
- intervention should preserve evidence and rationale where practical.
- HQ should help restore order, not erase local accountability.
- urgent intervention should still leave a visible governance trace.

# 8 What Does Not Belong Here

< Out Of Scope >

HQ Operational Brain does not own:

- customer-facing commerce experience.
- frontline capture and immediate store-edge projection.
- store operations execution.
- supply chain execution.
- deep constitutional governance language that belongs in `3rd_00018`.
- implementation details, SQL, Flutter, RPC, or contracts.

# 9 Future Subsystem Candidates

< Future Candidates >

Possible future subsystem directions from this lane include:

- franchise governance dashboards.
- policy rollout orchestration.
- forecasting and capacity support lanes.
- HQ intervention and escalation workflows.
- cross-store visibility summaries.

These are future subsystem candidates, not implementation commitments.

# 10 No Implementation Details

< Non-Goals >

This document does not define:

- database tables or schemas.
- SQL, triggers, migrations, or RPC contracts.
- Flutter pages or route flows.
- device SDK behavior.
- detailed event catalogues.
- state machine code.

The job of this constitution is to define the HQ governance boundary, not the implementation.
