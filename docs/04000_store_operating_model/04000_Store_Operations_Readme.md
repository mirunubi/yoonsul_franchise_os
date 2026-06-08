[ 3rd_02000_Store_Operations_Readme.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %

<< 3rd store operations lane anchor readme >>
<< purpose, boundary, and neighboring lane guidance only >>
<< no implementation; no SQL; no Flutter; no RPC >>

This lane covers store-level operational control, daily execution, and the practical coordination layer between frontline actions and HQ policy.

# 1 Purpose

< Purpose >

The store operations lane anchors the store as an executable operational unit.

This lane exists to:

- define day-to-day store execution ownership.
- keep local store control separate from HQ governance.
- provide the anchor for future store operations subsystem docs.

# 2 What Belongs Here

< In Scope >

- store opening and closing coordination.
- local operational checklists and store execution rhythm.
- staff-facing store operations guidance.
- store-level recovery coordination and handoff rules.
- store execution state that is broader than frontline capture but narrower than HQ policy.

# 3 What Does Not Belong Here

< Out Of Scope >

- HQ policy or rollout governance.
- customer relationship or membership lifecycle governance.
- supply chain, warehouse, or supplier orchestration.
- deep constitutional rules that belong in `3rd_00018`.
- implementation contracts, SQL, Flutter, RPC, or device SDK details.

# 4 Neighboring Lanes

< Neighbors >

- `docs/3rd/frontline/` owns capture and immediate operational projection.
- `docs/3rd/hq/` owns policy, support, and rollout governance.
- `docs/3rd/commerce/` owns customer and commerce continuity boundaries.
- `docs/3rd/3rd_00018_Governance_Constitution.md` owns the shared Phase 3 constitutional rules.
