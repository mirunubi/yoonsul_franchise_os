[ 3rd_01000_Frontline_Runtime_Readme.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %

<< 3rd frontline lane anchor readme >>
<< purpose, boundary, and neighboring lane guidance only >>
<< no implementation; no SQL; no Flutter; no RPC >>

This lane covers the frontline runtime surface where orders are captured, work is coordinated, and immediate customer-facing or kitchen-facing runtime actions occur.

# 1 Purpose

< Purpose >

The frontline lane anchors the runtime surfaces closest to the store floor and immediate operational action.

This lane exists to:

- define the boundary for frontline runtime ownership.
- keep intent capture, projection, and immediate operational coordination in one lane.
- provide the entry point for detailed frontline subsystem docs later.

# 2 What Belongs Here

< In Scope >

- POS / kiosk intent capture.
- KDS work coordination.
- DID customer-facing projection.
- edge relay and degraded continuity behavior at the store boundary.
- immediate operational surface guidance for the store floor.

# 3 What Does Not Belong Here

< Out Of Scope >

- HQ policy ownership.
- CRM / customer lifecycle governance.
- SCM / manufacturing / supplier coordination.
- deep constitutional governance that belongs in `3rd_00018`.
- implementation contracts, SQL, Flutter, RPC, or device SDK details.

# 4 Neighboring Lanes

< Neighbors >

- `docs/3rd/store_ops/` owns store-level operational control and day-to-day store execution.
- `docs/3rd/hq/` owns policy, rollout, support, and operational governance.
- `docs/3rd/commerce/` owns customer and commerce continuity boundaries.
- `docs/3rd/3rd_00018_Governance_Constitution.md` owns the shared Phase 3 constitutional rules.
