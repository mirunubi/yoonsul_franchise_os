[ 80000_Agent_Runtime_Readme.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80001_Agent_Constitution.md %
% root\docs\02000_runtime_federation\02000_Runtime_Federation_Constitution.md %

<< docs-only Agent Runtime foundation readme >>
<< no implementation code, no SQL, no migrations, no Flutter >>

# 1 Agent Domain Purpose

Agent Runtime is the lightweight operational runtime layer that observes store systems and converts operational activity into reviewable Task, Event, Audit, Exception, Recovery, and Sync records.

The Agent domain exists to help store operations remain visible, auditable, and recoverable during normal operation, degraded operation, offline operation, failover, and recovery.

Agent Runtime is not a large AI server.
Agent Runtime is not the store operator.
Agent Runtime does not own final business truth.

# 2 Relationship To Runtime Federation

Agent Runtime participates in Runtime Federation as an observation, translation, audit, recovery, and synchronization layer.

Runtime Federation keeps each runtime domain bounded.
Agent Runtime must not absorb authority from POS, KDS, Kiosk, DID/CMS, Waiting, Delivery, Inventory, or Workforce.

Agent Runtime may:

- observe runtime signals.
- translate activity into records.
- detect exceptions.
- manage local queues.
- preserve evidence during degraded operation.
- recommend recovery or escalation.
- sync with central systems.

Agent Runtime may not:

- approve sensitive operations.
- execute business decisions as an autonomous operator.
- overwrite central truth.
- blindly merge local degraded records.
- replace human approval.

# 3 Relationship To Store Runtime Domains

Agent Runtime supports Store Operations by preserving visibility, exception awareness, and recovery continuity.

Agent Runtime observes and translates signals from:

- POS: orders, payments, cancellations, refunds, settlements, staff actions, and local device stability.
- KDS: cooking state, preparation delay, completion, handoff, and kitchen-side exceptions.
- Kiosk: self-order flow, payment state, customer-side exception, and device availability.
- DID/CMS: display state, menu exposure, customer guidance, and content delivery continuity.
- Waiting: queue status, estimated wait time, call progress, and customer guidance events.
- Delivery: external order intake, rider handoff, delay, cancellation, and channel mismatch events.
- Inventory: stock movement, shortage signals, waste, replenishment, and count discrepancy events.
- Workforce: staff presence, role handoff, shift state, payroll-sensitive events, and supervisor actions.

The owning runtime remains authoritative for its domain.
Agent Runtime records evidence and supports recovery; it does not become the owner of those runtimes.

# 4 Key Documents In This Folder

Core foundation documents:

- `80000_Agent_Runtime_Readme.md` - Agent Runtime folder purpose and navigation.
- `80010_Agent_Server_Master_Architecture.md` - Agent Server definition, responsibilities, non-responsibilities, and deployment model.
- `80040_Primary_Secondary_Agent_Failover.md` - Primary, Secondary, Promoted Primary, split-brain, and recovery verification rules.
- `80050_Agent_Module_Supervisor.md` - supervisor monitoring, restart, failover trigger, queue health, and audit rules.
- `80060_Agent_Module_Level_Failover.md` - partial failure, module recovery, degraded mode, and full failover boundaries.
- `80070_Local_Temporary_Ledger.md` - local ledger and queue principles during degraded operation.
- `80080_Agent_Sync_And_Event_Replay.md` - safe sync, conflict isolation, replay, projection rebuild, verification, and audit lock.
- `80090_Agent_Degraded_Mode.md` - degraded operation modes, allowed actions, and restricted sensitive operations.
- `80100_Decision_Message_Repository.md` - Logical AI decision messages, manager responses, operational outcomes, and learning status.
- `80110_Logical_AI_Learning_Interface.md` - Logical AI learning inputs, recommendation boundaries, human decision recording, and feedback loop.
- `80120_Physical_AI_Task_Translation_Module.md` - boundary between approved manager decisions and future Physical AI task instructions.
- `80130_Physical_AI_Device_Adapter_Model.md` - future adapter boundary for device-specific command mapping and result return.
- `80135_Physical_AI_Result_Event_Collector.md` - Physical AI result, failure, human intervention, recovery, and audit event collection.
- `80140_Agent_BM_Patent_Claim_Boundary.md` - BM patent-oriented claim boundary and implementation-layer separation.
- `80150_Agent_Backup_Data_Center_And_Cross_Cloud_Failover.md` - backup data center, cross-cloud failover, secondary operation, and integrity verification boundary.
- `80160_Agent_Runtime_Required_Capability_Integration.md` - required Agent Runtime capability integration for development design and cross-domain propagation.
- `80170_Agent_Data_Store_And_AI_Evolution_Principles.md` - staged data-store and AI evolution principles from RDBMS canonical ledgers to Logical AI, Physical AI interface specification, and future device integration.
- `80180_Agent_Hygiene_Routine_And_CCP_Prompt_Integration.md` - hygiene routine prompt, CCP/HACCP-lite preparation support, KDS/DID/staff device/future speaker prompt boundary, overdue escalation, Event, and Audit design.
- `80190_Agent_Prepared_Inventory_And_Reorder_Integration.md` - Agent integration with SCM/Inventory for prepared inventory, reorder recommendation, inventory gap visibility, KDS/DID prompt boundary, manager approval, Event, and Audit design.

Existing constitutional context:

- `80001_Agent_Constitution.md` - bounded Agent authority and human approval boundary.
- `0000_Agent_Runtime_Civilization_Readme.md` - legacy namespace philosophy / bridge for old nested Agent references and namespace-growth rationale.

# 5 Current Status

This folder is design-only.

The documents in this folder define architecture, authority, recovery behavior, operational constraints, and audit principles.
They do not define implementation mechanics.

# 6 Explicit Implementation Prohibition

This folder must not contain:

- implementation code.
- SQL.
- Supabase migrations.
- Flutter implementation.
- RPC definitions.
- final local database schemas.
- executable Agent process code.

Agent Runtime documents may describe records, queues, states, flows, and responsibilities only as design-level operational concepts until a separate implementation authority explicitly permits implementation work.
