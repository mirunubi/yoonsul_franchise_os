[ 80120_Physical_AI_Task_Translation_Module.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80110_Logical_AI_Learning_Interface.md %
% root\docs\80000_agent\80130_Physical_AI_Device_Adapter_Model.md %
% root\docs\80000_agent\80135_Physical_AI_Result_Event_Collector.md %
% root\docs\80000_agent\80170_Agent_Data_Store_And_AI_Evolution_Principles.md %

<< docs-only Physical AI task translation doctrine >>
<< current phase defines translation boundary only >>

# 1 Purpose

Physical AI Task Translation Module defines the boundary between approved human decisions and future physical task instructions.

The current phase does not build Physical AI equipment.
The current phase defines translation boundary only.

# 2 Core Boundary

Logical AI message is not a device command.

Manager approval is required before physical task translation.
The translation module converts an approved manager decision into a device-specific task instruction.

Recommendation != Execution.
Evidence != Approval.

# 3 Translation Flow

The design-level flow is:

1. Logical AI generates a decision message.
2. Manager, owner, or HQ reviews the message.
3. Human approval is recorded.
4. Translation module creates an approved task instruction.
5. Device adapter maps the task instruction to a future device-specific command.
6. Device result returns as Event and Audit.
7. Physical AI failure creates Recovery Event.
8. Human intervention path remains available.

# 4 Task Instruction Fields

Task instruction fields include:

- `task_type`
- `target_order_id`
- `target_order_group`
- `device_id`
- `priority`
- `constraints`
- `approval_status`
- `failure_action`
- `human_intervention_required`
- `audit_required`
- `result_event_required`

These fields are design-level instruction concepts, not final protocols or final schemas.

The translation module converts approved decision messages into device-specific task instructions.
Human approval is required before translation.
Logical AI message is not a device command.

Physical AI interface specification is separated as Stage 5.5 in `80170_Agent_Data_Store_And_AI_Evolution_Principles.md`.
Stage 5.5 confirms the device-interface specification before actual Stage 6 device integration.

# 5 Example Task Instruction

Example:

```text
TASK_TYPE: PACKING_PRIORITY_CHANGE
TARGET_ORDER_GROUP: DELIVERY_ORDERS_PICKUP_WITHIN_10MIN
PRIORITY: HIGH
CONSTRAINTS:
- ALLERGY_ORDER_REQUIRES_HUMAN_CHECK
- SOLDOUT_CANDIDATE_INGREDIENT_FORBIDDEN
APPROVAL_STATUS: MANAGER_APPROVED
FAILURE_ACTION:
- REQUEST_HUMAN_INTERVENTION
- CREATE_RECOVERY_EVENT
AUDIT_REQUIRED: TRUE
RESULT_EVENT_REQUIRED: TRUE
```

# 6 Result And Failure Requirements

Device result must return as Event and Audit.

Physical AI failure must create Recovery Event.

Human intervention path is required whenever:

- device safety is uncertain.
- device result is missing.
- task failed.
- task conflicts with constraints.
- staff confirmation is required.
- customer safety or food safety may be affected.

# 7 Implementation Boundary

This document defines translation boundary only.
It does not implement Physical AI, define final device protocols, create implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
