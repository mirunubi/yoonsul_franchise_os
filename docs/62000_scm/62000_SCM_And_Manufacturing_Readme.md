[ 3rd_05000_SCM_And_Manufacturing_Readme.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %

<< 3rd SCM and manufacturing lane anchor readme >>
<< purpose, boundary, and neighboring lane guidance only >>
<< no implementation; no SQL; no Flutter; no RPC >>

This lane covers supply chain and manufacturing continuity that feeds store operations and product availability.

# 1 Purpose

< Purpose >

The SCM and manufacturing lane anchors replenishment, production, and supply continuity.

This lane exists to:

- define supply chain and manufacturing ownership.
- keep supply continuity separate from store execution and HQ policy.
- provide the anchor for future SCM subsystem docs.

# 2 What Belongs Here

< In Scope >

- supply chain coordination.
- manufacturing continuity.
- replenishment and vendor-facing operational support.
- supply availability and upstream production continuity.

# 3 What Does Not Belong Here

< Out Of Scope >

- store floor capture and immediate operational projection.
- HQ policy and rollout governance.
- customer CRM or membership lifecycle ownership.
- deep constitutional rules that belong in `3rd_00018`.
- implementation contracts, SQL, Flutter, RPC, or device SDK details.

# 4 Neighboring Lanes

< Neighbors >

- `docs/3rd/store_ops/` owns store execution.
- `docs/3rd/hq/` owns policy and rollout governance.
- `docs/3rd/future/` owns future expansion beyond current operational lanes.
- `docs/3rd/3rd_00018_Governance_Constitution.md` owns the shared Phase 3 constitutional rules.
