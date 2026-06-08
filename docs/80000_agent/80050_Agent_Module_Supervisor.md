[ 80050_Agent_Module_Supervisor.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80010_Agent_Server_Master_Architecture.md %
% root\docs\80000_agent\80060_Agent_Module_Level_Failover.md %

<< docs-only Agent Module Supervisor doctrine >>
<< supervisor actions require audit evidence >>

# 1 Purpose

Agent Supervisor is the design-level control layer that monitors Agent modules, detects degraded operation, attempts bounded recovery, triggers failover paths, and records supervisor actions as audit evidence.

Agent Supervisor is not an autonomous business approver.
Agent Supervisor does not convert recommendations into execution authority.

# 2 Module Heartbeat Monitoring

Agent Supervisor monitors module heartbeat signals.

Heartbeat monitoring exists to detect:

- stopped modules.
- delayed modules.
- unstable modules.
- repeated crash or restart patterns.
- module-level isolation from local queues or sync paths.

# 3 Module Restart

Agent Supervisor may trigger module restart as a bounded recovery action.

Restart must be treated as an operational event.
Restart must not erase module evidence, queues, or unresolved exception context.

# 4 Resource Monitoring

Agent Supervisor monitors resource pressure that may affect Agent continuity.

Resource pressure candidates:

- CPU saturation.
- memory pressure.
- disk pressure.
- local queue growth.
- clock drift suspicion.
- device health degradation.
- network instability.

# 5 Queue Health Monitoring

Agent Supervisor monitors queue health for:

- Local Event Queue.
- Local Audit Queue.
- Local Task Queue.
- Failed Sync Queue.
- Manual Recovery Queue.

Queue health monitoring must surface backlog growth, failed retry patterns, blocked sync, and recovery risk.

# 6 Sync Failure Detection

Agent Supervisor detects sync failure between Agent Runtime and central systems.

Sync failure detection must distinguish:

- temporary network interruption.
- repeated upload failure.
- central rejection.
- conflict isolation.
- sequence mismatch.
- reference mismatch.

# 7 Degraded Mode Trigger

Agent Supervisor may trigger degraded mode when runtime conditions make normal operation unsafe or unverifiable.

Degraded mode may be triggered by:

- database failure.
- network failure.
- main server failure.
- Agent failure.
- module failure.
- audit path failure.
- sync failure.
- split-brain suspicion.

# 8 Module-Level Failover Trigger

Agent Supervisor may trigger module-level failover when a module fails but Agent Runtime remains usable.

Module-level failover is appropriate when:

- one module is failing.
- local event and audit recording can continue.
- sensitive operation restrictions can contain risk.
- full Agent failover is not required.

# 9 Full Agent Failover Trigger

Agent Supervisor may trigger full Agent failover when runtime-level failure prevents the active Agent from preserving operational continuity.

Full Agent failover is appropriate when:

- Primary Agent heartbeat is lost.
- local queues cannot be maintained.
- audit evidence cannot be preserved by the active Agent.
- critical runtime resources are unavailable.
- module-level recovery is insufficient.
- runtime-level failure or multi-critical failure is detected.

Full Agent failover conditions include:

- Agent Runtime failure.
- Supervisor failure.
- Local Event Queue unavailable.
- Local Audit Queue unavailable.
- Primary hardware failure.
- CPU, memory, or disk critical failure.
- multiple critical module failure.
- event or audit recording capability lost.
- primary data corruption suspected.

# 10 Audit Requirement For Supervisor Actions

Every supervisor action requires audit evidence.

Audit evidence should include:

- action type.
- triggering condition.
- affected module or runtime.
- timestamp.
- device identity.
- staff or system actor identity when applicable.
- previous state.
- next state.
- queue impact.
- sync impact.
- recovery status.

# 11 Supervisor Recovery Doctrine

Partial failure should trigger partial recovery first.

The supervisor should prefer:

1. module heartbeat detection.
2. module restart.
3. module-level failover.
4. degraded mode transition.
5. full Agent failover only when runtime-level or multi-critical failure makes partial recovery unsafe.

Every supervisor action must produce an audit record when audit recording is available.
If audit recording is degraded, Local Audit Queue fallback or sensitive operation restriction is required.

# 12 Implementation Boundary

This document defines supervisor doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
