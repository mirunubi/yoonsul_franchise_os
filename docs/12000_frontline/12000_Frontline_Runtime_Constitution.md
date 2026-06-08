[ 3rd_01000_Frontline_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Readme.md %

<< 3rd frontline runtime constitution >>
<< operational worldview and boundary only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines the operational worldview and ownership boundary of the Frontline Runtime lane.
It explains what the lane is responsible for and what it must not absorb from neighboring lanes.

# 1 What Frontline Runtime Is

< Frontline Runtime >

Frontline Runtime is the store-floor and customer-facing operational surface where immediate runtime action happens.
It is the lane where intent is captured, operational state is projected, and urgent continuity decisions must remain visible.

Frontline Runtime is not a full business brain.
It is the surface where the business is first experienced and where runtime continuity must stay honest.

# 2 Core System Relationships

< System Relations >

Frontline Runtime relates to the following systems as a coordinated runtime boundary:

| system | frontline relationship |
| ------ | ---------------------- |
| POS | captures order intent and initiates frontline action |
| Kiosk | presents guided customer-facing entry and ordering surface |
| KDS | coordinates kitchen work queue and prep progress |
| DID | projects customer-facing status, pickup, and communication |
| CMS | provides content and surface guidance that affects what Frontline may display |
| Waiting | represents wait state, queue visibility, and customer expectation management |
| Recovery | represents degraded continuity, uncertainty handling, and safe restore behavior |

Rules:

- POS and Kiosk may initiate intent, but they do not own downstream truth.
- KDS coordinates execution, but it does not own payment truth or customer finality.
- DID projects state, but it does not own order authority.
- CMS influences presentation and policy-driven content, but it does not directly own frontline truth.
- Waiting is a visible runtime condition, not a separate authority plane.
- Recovery is a core runtime behavior, not an afterthought.

# 3 Customer-Facing Runtime Philosophy

< Customer Facing Philosophy >

Frontline Runtime must remain honest, readable, and calm from the customer perspective.
It should tell the truth about what is happening without pretending certainty that does not exist.

Principles:

- projection is not authority.
- visible state must not be confused with final truth.
- uncertainty should be shown rather than hidden.
- customer-facing state should support trust, not manipulate it.
- the lane should preserve a clean handoff when the customer moves into another operational stage.

# 4 Runtime State Ownership

< State Ownership >

Frontline Runtime owns the immediate operational state visible at the store edge.
It may project, relay, and summarize state, but it does not own every authoritative plane.

Owned boundary examples:

- order intent visibility.
- kitchen progress projection.
- pickup visibility.
- waiting state visibility.
- degraded display behavior.
- customer-facing recovery messaging.

Not owned here:

- final payment truth.
- HQ policy authority.
- store-wide business approval.
- supply chain truth.
- customer relationship history as a master domain.

# 5 Relationship To Neighboring Lanes

< Neighbor Lanes >

Frontline Runtime sits between several neighboring lanes:

- Store Operations provides daily execution and local store management context.
- HQ provides policy, support, rollout, and governance guidance.
- Commerce provides customer, membership, and trust continuity beyond the immediate store edge.

Frontline Runtime must remain compatible with all three without absorbing their authority.

# 6 Recovery-First Runtime Concept

< Recovery First >

Frontline Runtime must assume that failure and delay are part of normal operation.
Its job is to remain usable, visible, and recoverable even when the environment degrades.

Recovery-first means:

- show uncertainty instead of hiding it.
- preserve evidence before trying to reconcile.
- degrade gracefully before collapse.
- keep the customer informed without making false guarantees.
- restore safely before restoring fully.

# 7 Human Override Principles

< Human Override >

Human override is a constitutional part of Frontline Runtime.
Where the system recommends a path, a human may still need to interrupt, confirm, or redirect the runtime.

Principles:

- recommendations are not final judgment.
- override must remain visible and auditable in the broader governance spine.
- override should not silently erase prior runtime history.
- high-risk situations should preserve evidence and handoff context.

# 8 What Does Not Belong Here

< Out Of Scope >

Frontline Runtime does not own:

- detailed store operations governance.
- HQ policy and rollout authority.
- customer CRM or membership lifecycle ownership.
- supply chain, warehouse, or supplier orchestration.
- deep constitutional governance language that belongs in `3rd_00018`.
- implementation details, SQL, Flutter, RPC, or contracts.

# 9 Future Subsystem Candidates

< Future Candidates >

Possible future subsystem directions from this lane include:

- POS intent handling.
- kiosk customer entry.
- kitchen display coordination.
- customer-facing wait and recovery messaging.
- edge relay and degraded continuity behavior.
- pickup guidance and trust projection.

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

The job of this constitution is to define the boundary, not the implementation.
