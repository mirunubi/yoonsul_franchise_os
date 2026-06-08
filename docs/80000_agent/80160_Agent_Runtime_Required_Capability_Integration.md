[ 80160_Agent_Runtime_Required_Capability_Integration.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80000_Agent_Runtime_Readme.md %
% root\docs\80000_agent\80170_Agent_Data_Store_And_AI_Evolution_Principles.md %

<< docs-only · Agent Runtime required capability integration >>

# 1 Purpose

This document is not a patent filing document.
This document does not draft legal patent claims and is not written for patent-attorney submission.

This document records required development-design capabilities discovered during Agent / BM discussion and integrates them into franchise_os Agent Runtime design.
The focus is operational capability integration for development planning, domain alignment, and future design propagation.

Data-store and AI evolution staging is defined in `80170_Agent_Data_Store_And_AI_Evolution_Principles.md`.
That document preserves RDBMS as canonical truth and separates Logical AI learning, Physical AI task translation, Physical AI interface specification, and actual device integration into staged design rules.

# 2 Core Agent Architecture Flow

The franchise_os Agent architecture flow is:

```text
Store Runtime
POS · KDS · Kiosk · DID/CMS · Waiting · Delivery · Inventory · Workforce
=> Local / Lightweight Agent Runtime
Observation · Eventization · Exception · Audit · Recovery · Queue · Sync
=> Ledger Layer
Task / Event / Audit / Exception / Recovery / Decision Message
=> Logical AI Layer
Learning · Recommendation · Manager Push
=> Human Approval Layer
Owner / Manager / HQ
=> Physical AI Translation Layer
Device-specific Task Instruction
```

The flow preserves the core boundary:

- Agent != Operator.
- Recommendation != Execution.
- Evidence != Approval.
- Logical AI message != Physical AI device command.
- Human approval remains final authority.

# 3 Required Capabilities

## 3.1 Agent Server Master Architecture

Required capabilities:

- Agent is not a large AI server.
- Agent is a lightweight operational runtime.
- Agent observes store systems and translates activity into Task, Event, Audit, and Exception records.
- Agent supports recovery, queue, sync, and degraded operation.

## 3.2 Primary / Secondary Agent Structure

Required capabilities:

- POS and Kiosk can operate as a Primary / Secondary Agent pair.
- POS-only stores may use a backup tablet as Secondary Agent.
- Large stores may use a physical Agent Server PC.
- Promoted Primary writes append-only.
- no overwrite after recovery.
- split-brain must be marked.

## 3.3 Module-Level Failover

Required capabilities:

- partial failure = partial recovery.
- module restart before full failover.
- module-level failover before full Agent failover.
- full Agent failover only for runtime-level or multi-critical failure.
- supervisor actions must be audited.

## 3.4 Local Temporary Ledger

Required capabilities:

- Local Temporary Ledger preserves degraded-operation evidence.
- Local Temporary Ledger is not central truth.
- Local Event Queue, Local Audit Queue, Local Task Queue, Failed Sync Queue, and Manual Recovery Queue must be represented in design.
- replay only after duplicate, missing, sequence, reference, and conflict checks.
- no silent merge.

## 3.5 Decision Message Repository

Required capabilities:

- Logical AI manager-facing recommendation messages must be stored.
- situation snapshot, related events, manager response, execution result, and learning status must be preserved.
- manager approval, rejection, and modification are core learning data.

## 3.6 Physical AI Task Translation

Required capabilities:

- Logical AI message is not a device command.
- human approval is required before translation.
- approved decision may be translated into device-specific task instruction.
- device result must return as Event and Audit.
- Physical AI failure must create Recovery Event.
- human intervention path is required.

## 3.7 Backup Data Center / Cross-Cloud Failover

Required capabilities:

- Primary cloud / data center and Secondary cloud / data center boundary must be represented.
- AWS primary plus Azure secondary, Azure primary plus AWS secondary, or separate region / data center options may be considered as design patterns.
- snapshot backup, Event Ledger backup, Audit Ledger backup, and Projection backup must be represented.
- secondary operation may be limited.
- sensitive operations may be restricted.
- backup data center is not silent authority transfer.
- recovery requires replay and integrity check.

# 4 Capability To Current Document Map

| required capability | primary current document |
| --- | --- |
| Agent Server Master Architecture | `80010_Agent_Server_Master_Architecture.md` |
| Primary / Secondary Agent Structure | `80040_Primary_Secondary_Agent_Failover.md` |
| Module Supervisor | `80050_Agent_Module_Supervisor.md` |
| Module-level Failover | `80060_Agent_Module_Level_Failover.md` |
| Local Temporary Ledger | `80070_Local_Temporary_Ledger.md` |
| Sync and Replay | `80080_Agent_Sync_And_Event_Replay.md` |
| Degraded Mode | `80090_Agent_Degraded_Mode.md` |
| Decision Message Repository | `80100_Decision_Message_Repository.md` |
| Logical AI Learning | `80110_Logical_AI_Learning_Interface.md` |
| Physical AI Translation | `80120_Physical_AI_Task_Translation_Module.md` |
| Device Adapter | `80130_Physical_AI_Device_Adapter_Model.md` |
| Result Event Collector | `80135_Physical_AI_Result_Event_Collector.md` |
| BM discussion boundary / capability origin | `80140_Agent_BM_Patent_Claim_Boundary.md` |
| Backup Data Center / Cross-cloud Failover | `80150_Agent_Backup_Data_Center_And_Cross_Cloud_Failover.md` |
| Agent Data Store And AI Evolution Principles | `80170_Agent_Data_Store_And_AI_Evolution_Principles.md` |
| Runtime Federation Boundary | `02020_Agent_Runtime_Federation_Principles.md` |

# 5 Cross-Domain Propagation Checklist

The following domains must later align with Agent Runtime required capabilities:

- KDS Runtime.
- DID/CMS Runtime.
- POS Runtime.
- Kiosk Runtime.
- Waiting Runtime.
- Delivery Runtime.
- Inventory Runtime.
- Workforce Runtime.
- Store Runtime Operations.
- Runtime Federation.
- Audit / Recovery / Override domains.

Future design for each domain must clarify:

- what Agent observes.
- what Agent may recommend.
- what Agent may not execute.
- which events are recorded.
- what failure visibility is required.
- what human approval boundary applies.

# 6 Non-Implementation Boundary

This document does not define:

- actual DB schema.
- RPC.
- Flutter UI.
- Agent process.
- local storage engine.
- sync protocol.
- device protocol.
- cloud vendor configuration.
- production failover automation.

This document is development-design capability integration only.
