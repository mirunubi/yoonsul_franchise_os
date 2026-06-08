[ 80040_Primary_Secondary_Agent_Failover.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80010_Agent_Server_Master_Architecture.md %
% root\docs\80000_agent\80070_Local_Temporary_Ledger.md %
% root\docs\80000_agent\80080_Agent_Sync_And_Event_Replay.md %

<< docs-only Primary / Secondary Agent failover doctrine >>
<< failover does not mean overwrite >>

# 1 Purpose

This document defines the design-level failover model for Primary Agent Server, Secondary Agent Server, Promoted Primary, split-brain suspicion, recovery pending state, and central verification before merge.

# 2 Primary Agent Server Role

The Primary Agent Server is the active store-side Agent Runtime instance.

It is responsible for:

- observing store runtime signals.
- assigning local sequence order.
- writing local operational evidence.
- managing local queues.
- detecting exceptions.
- syncing with central systems when available.
- exposing health state to the supervisor and central systems.

Primary Agent Server activity remains bounded.
Primary Agent Server does not own central truth and does not approve sensitive operations by itself.

# 3 Secondary Agent Server Role

The Secondary Agent Server is the standby or backup Agent Runtime instance.

It is responsible for:

- monitoring Primary Agent heartbeat.
- keeping standby readiness.
- preserving minimum observation continuity when configured.
- preparing for promotion when Primary heartbeat is lost.
- recording promotion evidence if promoted.

Secondary Agent Server standby status does not make it a central source of truth.

# 4 Promoted Primary Role

Promoted Primary is a Secondary Agent that temporarily becomes active after Primary heartbeat loss.

Promoted Primary may:

- continue local observation where possible.
- create local event, task, audit, exception, and recovery records.
- preserve local sequence continuity from its own promotion point.
- store records in local queues when central sync is unavailable.
- write new events append-only.
- avoid overwriting previous Primary data.

Promoted Primary is not Verified Primary.
Promotion allows operational continuity, not automatic authority transfer into central truth.

# 5 POS / Kiosk Model

In a normal store, POS and Kiosk may form a Primary / Secondary Agent pair.

Common patterns:

- POS as Primary Agent, Kiosk as Secondary Agent.
- Kiosk as Primary Agent, POS as Secondary Agent when kiosk stability is higher.

Selection must be explicit, based on operational stability, and visible to store management or central systems.

# 6 POS-Only And Backup Tablet Model

In a POS-only store:

- POS may act as Primary Agent.
- backup tablet may act as Secondary Agent.

The backup tablet exists for continuity during POS instability.
If promoted, it must mark records as promoted-primary local evidence until central verification completes.

# 7 Large Store Physical Agent Server Model

In a large store, a separate Physical Agent Server PC may act as Primary Agent.

POS, kiosk, or tablet devices may act as Secondary or emergency continuity agents.
The physical server model is appropriate when event volume, device count, queue size, or recovery complexity exceeds practical POS or tablet capacity.

# 8 Split-Brain Risk

Split-brain occurs when more than one Agent believes it is active Primary for the same store and time window.

Split-brain risk must be treated as a recovery and audit condition, not as a normal merge case.

When split-brain is suspected:

- the split-brain condition must be marked, not hidden.
- conflicting timelines must be isolated.
- local queues must not be blindly merged.
- sensitive operations must remain restricted.
- central, HQ, or manager verification is required.

# 9 Recovery Pending State

When the original Primary recovers after a Secondary has been promoted, the recovered Primary enters recovery pending state.

Recovery pending means:

- the recovered Primary must not overwrite Promoted Primary records.
- the recovered Primary must not automatically reclaim verified authority.
- Primary recovery requires resync.
- divergent event windows must be compared.
- conflict isolation must occur before replay.
- central, HQ, or manager verification must happen before merge.

# 10 No Automatic Overwrite After Recovery

Failover does not mean overwrite.

Recovered Primary records, Promoted Primary records, and central records must be compared before any merge or replay.
No device may erase or replace another device timeline simply because it has returned online.

# 11 Central / HQ / Manager Verification Before Merge

Central, HQ, or manager verification is required before:

- resolving split-brain.
- merging divergent local ledgers.
- rebuilding projections.
- finalizing sensitive operation outcomes.
- marking a Promoted Primary as verified for the affected window.

# 12 State Candidates

State candidates:

- `PRIMARY_AGENT_ACTIVE`
- `SECONDARY_AGENT_STANDBY`
- `PRIMARY_HEARTBEAT_LOST`
- `SECONDARY_PROMOTED_PRIMARY`
- `PRIMARY_RECOVERY_PENDING`
- `AGENT_SPLIT_BRAIN_SUSPECTED`
- `AGENT_RESYNC_REQUIRED`
- `CENTRAL_VERIFICATION_REQUIRED`

# 13 Implementation Boundary

This document defines failover doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
