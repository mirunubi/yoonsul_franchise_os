[ 80060_Agent_Module_Level_Failover.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80050_Agent_Module_Supervisor.md %
% root\docs\80000_agent\80090_Agent_Degraded_Mode.md %

<< docs-only module-level failover doctrine >>
<< partial failure means partial recovery >>

# 1 Purpose

This document defines how Agent Runtime should reason about module failure, module restart, module-level failover, full Agent failover, and sensitive operation restrictions during degraded mode.

# 2 Partial Failure Means Partial Recovery

Partial failure should lead to partial recovery whenever possible.

The system must not jump to full Agent failover when a bounded module restart or module-level failover can preserve operational continuity safely.

# 3 Full Failover Only For Runtime-Level Failure

Full Agent failover is reserved for runtime-level failure.
It may also be required for multi-critical failure when several modules or queues fail together and Agent Runtime can no longer preserve event and audit continuity.

Runtime-level failure includes:

- active Agent heartbeat loss.
- inability to preserve local event evidence.
- inability to preserve audit evidence.
- severe local queue failure.
- unrecoverable resource failure.
- split-brain risk requiring promotion isolation.
- Supervisor failure.
- Primary hardware failure.
- CPU, memory, or disk critical failure.
- multiple critical module failure.
- primary data corruption suspected.

# 4 Module Restart

Module restart is the first bounded recovery path for a failed module.

Module restart must:

- preserve local records.
- preserve unresolved exception context.
- produce supervisor audit evidence.
- avoid blind replay or mutation.

# 5 Module-Level Failover

Module-level failover is appropriate when a module cannot recover but the Agent Runtime remains otherwise usable.

Module-level failover may route work to:

- a standby module instance.
- a reduced local mode.
- a manual queue.
- a human fallback path.
- a delayed sync path.

# 6 Full Agent Failover

Full Agent failover is appropriate only when the active Agent Runtime cannot safely continue.

Full Agent failover must preserve:

- local queue evidence.
- audit continuity.
- promotion evidence.
- recovery pending status.
- central verification requirements.

# 7 Sensitive Operation Restriction During Degraded Mode

Sensitive operations must be restricted when the relevant module, audit path, sync path, or verification path is degraded.

Restricted operations include:

- refund finalization.
- point settlement.
- payroll finalization.
- owner settlement finalization.
- legal responsibility judgment.
- large cancellation.
- customer compensation finalization.
- Physical AI task approval.

# 8 Agent Module Candidates

Agent module candidates:

- Observation Module.
- Task Classification Module.
- Event Correlation Module.
- Exception Detection Module.
- Recommendation Module.
- SOP Handoff Module.
- Recovery Module.
- Audit Module.
- Sync Module.
- Physical AI Interface Module.

# 9 Failure Examples

Recommendation Module failure:

- recommendations stop.
- Event recording continues.
- Audit recording continues.
- manager uses manual judgment.

Sync Module failure:

- central sync stops.
- Local Queue continues.
- conflict and retry status must be preserved.
- replay happens after recovery.

Audit Module failure:

- Local Audit Queue fallback is required where possible.
- sensitive operations are restricted if audit cannot be preserved.
- supervisor action must be preserved as soon as audit fallback is available.

Recovery Module failure:

- Manual Recovery Queue is used.
- automated recovery recommendations stop.
- unresolved recovery work remains visible.
- HQ or manager verification is required.

Physical AI Interface Module failure:

- device instruction stops.
- human operation fallback remains available.
- Physical AI task approval is restricted.

# 10 Implementation Boundary

This document defines module-level failover doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
