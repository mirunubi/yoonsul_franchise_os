[ 3rd_01350_CMS_Operational_Projection_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Readme.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01050_Operational_Agent_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01200_POS_Transactional_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01250_Kiosk_Self_Service_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01100_KDS_Operational_Recovery_Runtime_Constitution.md %

<< 3rd frontline CMS operational projection constitution >>
<< operational projection governance runtime worldview only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines CMS as an Operational Projection Governance Runtime.
It governs projection without owning operational truth, recovery state, or runtime final judgment.

# 1 CMS Runtime

< CMS Runtime >

CMS Runtime is the projection governance lane for customer-facing and staff-facing surfaces.
It coordinates what is shown, how it is shown, and which operational surfaces receive projection guidance.

CMS exists to:

- govern projection across operational runtimes.
- keep customer/staff-facing surfaces coherent.
- support visibility without claiming operational truth.

# 2 Core Relationships

< Runtime Relations >

| system | CMS relationship |
| ------ | ---------------- |
| DID | customer-facing projection lane that may receive CMS-driven content, waiting, and event visibility guidance |
| Kiosk | self-service customer intake surface that may be shaped by CMS presentation rules |
| POS | transactional authority runtime that CMS may visualize but not override |
| Operational Agent | mediation and intelligence layer that may observe and recommend without owning CMS |
| HQ Operational Brain | governance lane that may shape CMS policy, rollout, and support boundaries |
| Commerce / CRM | customer-facing commercial experience lane that CMS may project into, but does not own |
| Store Operations | local execution lane that CMS may support through visible surfaces, but does not govern directly |
| Waiting | visible customer/staff-facing state that CMS may project, but does not own |
| Event | visible operational event projection that CMS may surface, but does not own |

Rules:

- CMS may project, but it does not own operational truth.
- CMS may coordinate visibility, but it does not override authoritative runtime state.
- CMS may support surfaces, but it does not become the source of truth for those surfaces.
- CMS does not own recovery/runtime state.

# 3 Projection Governance Philosophy

< Projection Governance >

CMS is the governance layer for projection, not the authority layer for reality.
It should ensure that surfaces stay coherent, timely, and readable while still remaining subordinate to the operational runtime behind them.

Principles:

- projection must not override operational truth.
- visibility is not authority.
- campaign is not truth.
- a projection can be helpful without being authoritative.
- a projection must not hide or rewrite operational uncertainty.
- human final authority remains explicit.

# 4 Semantic Split

< Semantic Split >

| concept | meaning |
| ------- | ------- |
| operational truth | the underlying runtime condition that the business must treat as real |
| projection | the presented or displayed representation of a runtime condition |
| campaign | a governed content/action pattern intended to influence visibility or behavior |
| visibility | what a surface reveals to humans at a given moment |

Rules:

- operational truth comes first.
- projection must reflect operational truth, not replace it.
- campaign shapes visibility, but does not change truth by itself.
- visibility may be curated, but it must not become fake certainty.

# 5 HQ CMS Vs Store CMS

< CMS Variants >

CMS may exist in at least two governance shapes:

- HQ CMS
- Store CMS

HQ CMS concepts:

- policy-led projection governance.
- cross-store consistency.
- centrally managed rollout and support posture.

Store CMS concepts:

- local surface adaptation.
- store-contextual visibility.
- local presentation within HQ governance boundaries.

Rules:

- Store CMS must not override HQ governance boundaries.
- HQ CMS may guide policy, but it must not erase store reality.
- both variants remain projection governance, not operational truth.

# 6 Capability Tier Philosophy

< Tiers >

CMS capability may be organized into tiers:

- Basic
- Premium
- HQ-linked
- intelligence-assisted

Tier meaning:

- Basic: simple projection governance for local surfaces.
- Premium: richer visibility and content control.
- HQ-linked: centrally governed surfaces and rollout alignment.
- intelligence-assisted: recommendation support for projection decisions, still not authority.

Rules:

- tiering changes capability, not ownership.
- intelligence-assisted does not mean authority.
- higher tier still does not override operational truth.

# 7 Authority Split

< Authority Split >

| authority | meaning |
| --------- | ------- |
| projection authority | control over what is displayed and how it is arranged |
| operational authority | control over real runtime decisions and state transitions |
| recovery authority | control over how anomalies, incidents, and restoration are handled |

Rules:

- CMS owns projection authority.
- CMS does not own operational authority.
- CMS does not own recovery authority.
- projection authority must never be treated as runtime truth.

# 8 Runtime Synchronization And Visibility

< Synchronization >

CMS must remain synchronized with the operational runtime without becoming the runtime.

Concepts:

- timely projection updates.
- visible uncertainty when truth is not settled.
- projection refresh after state changes.
- surface coherence across customer and staff-facing views.
- waiting state visibility when queue or delay exists.
- event visibility when operational events need surfacing.

CMS should help humans understand the runtime, not replace the runtime.

# 9 Emergency / Minimal Projection Mode

< Emergency Mode >

When runtime, network, or server instability occurs, CMS must degrade to text-first and data-first minimal projection.

Emergency mode principles:

- emergency alert surfaces must exist across relevant systems.
- rich media, animation, and decorative campaign layers may be suppressed.
- essential notices, sold-out state, payment availability, waiting delay, pickup guidance, and emergency messages must be prioritized.
- CMS failure must not stop POS, KDS, or workforce runtime.
- degraded, stale, or uncertain state must be shown visibly.
- stale projection must not be presented as authoritative truth.

Backup connectivity concept:

- CMS may project emergency messages through fallback connectivity paths.
- low-bandwidth survivability is more important than visual richness.
- backup dongle or local emergency communication ideas may be referenced as philosophy only, not implementation.

# 10 What Does Not Belong Here

< Out Of Scope >

CMS does not own:

- operational truth.
- recovery state.
- order state.
- payment authority.
- inventory truth.
- payroll or workforce truth.
- runtime final judgment.
- kiosk transaction authority.
- POS order/payment authority.
- KDS kitchen authority.
- deep constitutional governance language that belongs in `3rd_00018`.
- implementation details, SQL, Flutter, RPC, or contracts.

Explicit boundary:

- Local Agent emergency attendance/auth cache, primary-secondary sync, promoted primary mode, and workforce survivability are out of scope for this CMS document.
- Those topics belong to Operational Agent and Workforce Survivability documents, not CMS.

# 11 Future Subsystem Candidates

< Future Candidates >

Possible future subsystem directions from this lane include:

- projection policy summaries.
- HQ-linked rollout surfaces.
- local store content governance.
- visibility tier management.
- emergency/minimal projection governance summaries.
- projection/recovery coordination summaries.

These are future subsystem candidates, not implementation commitments.

# 12 No Implementation Details

< Non-Goals >

This document does not define:

- database tables or schemas.
- SQL, triggers, migrations, or RPC contracts.
- Flutter pages or route flows.
- device SDK behavior.
- detailed event catalogues.
- state machine code.

The job of this constitution is to define the CMS boundary, not the implementation.
