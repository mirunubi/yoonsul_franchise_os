[ 80010_Agent_Server_Master_Architecture.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80000_Agent_Runtime_Readme.md %
% root\docs\80000_agent\80001_Agent_Constitution.md %
% root\docs\02000_runtime_federation\02000_Runtime_Federation_Constitution.md %

<< docs-only Agent Server master architecture >>
<< Agent Server is lightweight operational runtime, not large AI server >>

# 1 Agent Server Definition

Agent Server is a lightweight operational runtime that observes store systems, translates store activity into operational records, detects exceptions, manages local queues, supports recovery, records audit trails, and syncs with central systems.

Agent Server is not a large AI server.
Agent Server is not an autonomous operator.
Agent Server is not the final source of central truth.

# 2 Lightweight Operational Runtime

Agent Server exists close to store activity.
Its value comes from operational proximity, continuity, queue survivability, and audit discipline.

Agent Server should remain small enough to operate on practical store devices when store size requires it.
It may run on a POS, kiosk, tablet, or dedicated physical PC depending on store topology.

# 3 Runtime Flow

The conceptual flow is:

1. Store Runtime
2. Agent Runtime
3. Ledger Layer
4. Logical AI
5. Human Approval
6. Physical AI Translation

Meaning:

- Store Runtime produces operational activity.
- Agent Runtime observes, translates, queues, detects, and records.
- Ledger Layer preserves Task, Event, Audit, Exception, Recovery, and Sync evidence.
- Logical AI may recommend, classify, summarize, or prioritize.
- Human Approval remains final for sensitive or authority-bearing decisions.
- Physical AI Translation may convert approved work into physical execution instructions only after approval boundaries are satisfied.

## 3.1 Full Franchise OS Agent Architecture Flow

The franchise_os Agent architecture flow is:

```text
Store Runtime
POS / KDS / Kiosk / DID-CMS / Waiting / Delivery / Inventory / Workforce
=> Local / Lightweight Agent Runtime
Observation / Eventization / Exception / Audit / Recovery / Queue / Sync
=> Ledger Layer
Task / Event / Audit / Exception / Recovery / Decision Message
=> Logical AI Layer
Learning / Recommendation / Manager Push
=> Human Approval Layer
Owner / Manager / HQ
=> Physical AI Translation Layer
Device-specific Task Instruction
```

Agent is the Store Runtime survivability and translation layer.
Agent observes store activity, converts it into operational evidence, feeds the Ledger Layer, and allows Logical AI to learn from verified operational records.

Logical AI pushes decision messages.
Owner, Manager, or HQ approval remains required before sensitive action or Physical AI translation.
Physical AI Translation comes only after human approval.

# 4 Agent Responsibilities

Agent Server is responsible for:

- observing POS, KDS, Kiosk, DID/CMS, Waiting, Delivery, Inventory, and Workforce signals.
- translating store activity into Task, Event, Audit, and Exception records.
- detecting operational exceptions.
- maintaining local queues during degraded operation.
- preserving audit trails.
- supporting recovery after failure or partition.
- syncing with central systems.
- isolating conflicts before replay.
- surfacing recommendations for human review.
- triggering degraded mode and failover procedures when required.
- feeding the Ledger Layer with Task, Event, Audit, Exception, Recovery, and Decision Message evidence.
- supporting Degraded Mode, Recovery, Queue, and Sync as survivability functions.

# 5 Agent Non-Responsibilities

Agent Server is not responsible for:

- owning POS authority.
- owning KDS authority.
- owning Kiosk authority.
- owning DID/CMS authority.
- owning Waiting authority.
- owning Delivery authority.
- owning Inventory authority.
- owning Workforce authority.
- final approval of sensitive business operations.
- final legal responsibility judgment.
- final settlement, payroll, point, refund, or compensation decisions.
- blind overwrite of central truth.
- autonomous physical execution without approved translation.

# 6 Core Principles

- Agent != Operator.
- Recommendation != Execution.
- Evidence != Approval.
- Dismissed != Resolved.
- Replay != Mutation.
- Failover != Overwrite.
- Local queue != Central truth.
- Promoted Primary != Verified Primary.
- Logical AI message != Physical AI device command.
- Human approval remains final authority.
- Backup data center != silent authority transfer.

# 7 Store-Size Deployment Model

## 7.1 One-Person Or Small Store

The POS or an Android tablet may act as a Lightweight Agent.

The design goal is practical survivability without forcing a separate server footprint.
The Lightweight Agent observes, records, queues, and syncs within the limits of small-store hardware.

## 7.2 Normal Store

The POS may operate as Primary Agent and the Kiosk as Secondary Agent.
The Kiosk may operate as Primary Agent and the POS as Secondary Agent if kiosk stability is higher in that store.

Primary selection is based on practical runtime stability, uptime, network position, and operational fit.
The model must remain explicit and reviewable.

## 7.3 POS-Only Store

The POS may operate as Primary Agent and a backup tablet may operate as Secondary Agent.

The backup tablet preserves continuity when the POS is unstable or unavailable, but promotion does not create verified central truth by itself.

## 7.4 Large Store

A separate Physical Agent Server PC may operate as the primary Agent Server.

Large stores may require dedicated physical runtime capacity because of device count, event volume, local queue size, supervisor needs, and recovery complexity.

## 7.5 Future Large-Scale Store

A future large-scale store may use a local Agent Server plus backup data center or cross-cloud sync.

Backup data center sync may preserve snapshot, Event Ledger, Audit Ledger, and projection continuity.
It does not silently transfer business authority.
After primary recovery, verification, replay, and integrity checks are required before normal authority is restored.

# 8 Architecture Boundary

Agent Server architecture is design-only in this document.
This document does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
