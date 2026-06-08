[ 80090_Agent_Degraded_Mode.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80050_Agent_Module_Supervisor.md %
% root\docs\80000_agent\80060_Agent_Module_Level_Failover.md %
% root\docs\80000_agent\80070_Local_Temporary_Ledger.md %

<< docs-only Agent degraded mode doctrine >>
<< degraded operation preserves evidence but restricts sensitive authority >>

# 1 Purpose

Agent Degraded Mode defines how Agent Runtime preserves operational continuity and evidence when normal runtime conditions are unavailable or unsafe.

Degraded Mode is a bounded survivability mode.
It does not grant the Agent new approval authority.

# 2 Degraded Mode Causes

Degraded Mode may be caused by:

- database failure.
- network failure.
- main server failure.
- Agent failure.
- module failure.
- audit path failure.
- sync path failure.
- split-brain suspicion.
- local queue pressure.
- primary region failure.
- primary database unreachable.
- primary event write failure.
- backup data center or cross-cloud failover.

# 3 Database Failure

Database failure may prevent normal reads, writes, or projections.

During database failure:

- local queue storage should be used where possible.
- sensitive operation finalization must be restricted.
- recovery evidence must be preserved.
- central comparison is required after recovery.

# 4 Network Failure

Network failure may prevent central sync and external runtime communication.

During network failure:

- Local Event Queue may continue.
- Local Audit Queue may continue.
- Failed Sync Queue must preserve failed upload attempts.
- central truth must not be assumed from local-only state.

# 5 Main Server Failure

Main server failure may prevent normal central authority, projection, or sync.

During main server failure:

- store operation may continue within allowed degraded boundaries.
- local evidence must remain append-only.
- final sensitive decisions must wait for recovery and verification.

# 6 Agent Failure

Agent failure may require module recovery, full Agent failover, or manual fallback.

Agent failure must be evaluated by:

- active Agent heartbeat.
- local event evidence availability.
- local audit evidence availability.
- queue health.
- supervisor state.
- split-brain risk.

# 7 Module Failure

Module failure should trigger module restart or module-level failover before full Agent failover when safe.

Partial failure means partial recovery.
Full failover is reserved for runtime-level failure.

# 8 Read-Only Mode

Read-only mode may be used when writes are unsafe but current state can still be viewed.

Read-only mode supports visibility but must not be treated as proof that no new store activity occurred outside visible systems.

# 9 Limited Data Mode

Limited data mode may be used when only partial local or cached data is available.

Limited data mode must clearly preserve uncertainty.
Agent recommendations in limited data mode must remain bounded and reviewable.

# 10 Sensitive Operation Restriction

Sensitive operations must be restricted when evidence, approval, audit, or sync paths are degraded.

Evidence != Approval.
Recommendation != Execution.

# 11 Allowed Operations During Degraded Mode

Allowed operations during degraded mode may include:

- order intake if possible.
- cooking progress.
- packing.
- customer guidance.
- waiting time notice.
- basic Event recording.
- Audit recording.
- Recovery Queue storage.

Allowed operations remain subject to local runtime capability and audit availability.

# 12 Forbidden Or Restricted Operations During Degraded Mode

Restricted operations during degraded mode include:

- refund finalization.
- point settlement.
- payroll finalization.
- owner settlement finalization.
- legal responsibility judgment.
- large cancellation.
- customer compensation finalization.
- Physical AI task approval.

These operations require recovery, verification, and appropriate human or central approval before finalization.

# 13 Backup Data Center And Cross-Cloud Degraded Operation

Backup data center or cross-cloud failover may place the store or central runtime into secondary operation mode.

Secondary operation may preserve continuity through:

- snapshot backup.
- Event Ledger backup.
- Audit Ledger backup.
- Projection backup.
- limited write or read-only operation.

Secondary operation may be automatic or manager / HQ-approved depending on failure severity.
Secondary operation is not silent authority transfer.

Sensitive operations remain restricted during secondary operation when ledger integrity, approval context, or replay verification is incomplete.

Restricted operations during cross-cloud failover include:

- refund finalization.
- point settlement.
- payroll finalization.
- owner settlement finalization.
- large cancellation.
- customer compensation finalization.
- legal responsibility judgment.
- Physical AI task approval.

# 14 Implementation Boundary

This document defines degraded mode doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
