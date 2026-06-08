[ 80130_Physical_AI_Device_Adapter_Model.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80120_Physical_AI_Task_Translation_Module.md %
% root\docs\80000_agent\80135_Physical_AI_Result_Event_Collector.md %

<< docs-only Physical AI device adapter model >>
<< adapter is future extension boundary; device protocols are not final >>

# 1 Purpose

Physical AI Device Adapter Model defines a future extension boundary for mapping approved translated task instructions to device-specific commands.

Device protocols are not final in this document.
This document does not implement device control.

# 2 Adapter Boundary

Each device type requires a mapping from translated task instruction to a device-specific command.

The adapter boundary must preserve:

- manager approval requirement.
- task instruction constraints.
- approved decision message reference.
- human safety.
- human override.
- result event return.
- audit event return.
- exception and recovery event return on failure.

# 3 Adapter Candidates

Adapter candidates include:

- Packing Assembly Adapter.
- Auto Cooking Device Adapter.
- Smart Sensor Adapter.
- Robot Arm Adapter.
- Smart Steamer Adapter.
- Smart Fryer Adapter.
- Future Device Adapter.

Adapters are future extension boundaries.
They do not finalize device protocols in this phase.
Each device type requires mapping from translated task instruction to device-specific command.

# 4 Packing Equipment Examples

Packing equipment mapping may involve:

- packing order.
- label.
- pickup zone movement.
- missing item detection.

Packing adapter output must return as Event and Audit.
Missing item detection must return as Exception or Recovery Event when appropriate.

# 5 Auto Cooking Equipment Examples

Auto cooking equipment mapping may involve:

- cooking start.
- temperature.
- time.
- ingredient input.
- completion condition.

Cooking equipment output must preserve food safety, staff override, and auditable completion state.

# 6 Sensor Examples

Sensor mapping may involve:

- target condition.
- threshold.
- anomaly event.

Sensor anomaly output must return as Event, Exception, Audit, or Recovery evidence depending on severity and operational impact.

# 7 Robot Equipment Examples

Robot equipment mapping may involve:

- target object.
- workspace or coordinate.
- speed or safety constraint.
- stop condition.
- human intervention condition.

Robot equipment must preserve human safety and human override at all times.

# 8 Failure Return

Device failure must return as Exception or Recovery Event.

Failed physical execution must not be hidden inside adapter state.
Device output must return to Agent Runtime so it can be represented as Task, Event, Audit, Exception, or Recovery evidence.

# 9 Implementation Boundary

This document defines a future adapter boundary only.
It does not define final device protocols, implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
