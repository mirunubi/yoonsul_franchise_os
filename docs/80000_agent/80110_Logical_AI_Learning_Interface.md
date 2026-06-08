[ 80110_Logical_AI_Learning_Interface.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80000_Agent_Runtime_Readme.md %
% root\docs\80000_agent\80100_Decision_Message_Repository.md %
% root\docs\80000_agent\80120_Physical_AI_Task_Translation_Module.md %
% root\docs\80000_agent\80170_Agent_Data_Store_And_AI_Evolution_Principles.md %

<< docs-only Logical AI learning interface doctrine >>
<< Logical AI recommends, explains, prioritizes, and requests approval >>

# 1 Purpose

Logical AI Learning Interface defines how Logical AI learns from Agent-generated operational evidence and returns bounded recommendations to manager, owner, or HQ reviewers.

Logical AI is a learning and recommendation layer above Agent Runtime.
It does not directly execute store operations.

# 2 Learning Source

Logical AI may learn from Agent-generated:

- Task data.
- Event data.
- Audit data.
- Exception data.
- Recovery data.
- manager decision messages.
- approval, rejection, and modification history.
- operational outcomes.

Agent evidence is a learning input.
Evidence is not approval.

# 3 Decision Message Flow

Logical AI pushes decision messages to manager, owner, or HQ.

The flow is:

1. Agent Runtime preserves operational evidence.
2. Logical AI analyzes patterns and generates a decision message.
3. Manager, owner, or HQ reviews the message.
4. Human decision is recorded.
5. Operational result is recorded.
6. Result is fed back into future learning.

# 4 Learning Targets

Learning targets include:

- cooking delay pattern.
- KDS bottleneck.
- packing bottleneck.
- sold-out candidate.
- delivery wait-time error.
- customer guidance delay.
- manager approval or rejection history.
- manual override history.
- failure type.
- recovery success or failure.
- SOP outcome.
- customer claim reduction.

# 5 Boundary Rules

Logical AI may:

- recommend.
- explain.
- prioritize.
- request approval.

Logical AI may not:

- silently mutate store state.
- directly execute store operations.
- finalize refunds.
- finalize payroll.
- finalize settlement.
- decide legal responsibility.
- finalize customer compensation.
- convert a decision message into a Physical AI device command without manager approval.

# 6 Human Decision Recording

Human decision recording is required because the learning asset is not only the AI output.

The learning asset includes:

- what Logical AI recommended.
- what the human approved.
- what the human rejected.
- what the human modified.
- why the human decision was made if available.
- what happened operationally afterward.

# 7 Feedback Into Future Learning

Operational result must return to Logical AI learning only after it is recorded through Event, Audit, Exception, or Recovery evidence.

Failed outcomes, rejected recommendations, and modified approvals are valuable learning data and must not be hidden.

Data-store staging for Logical AI learning follows `80170_Agent_Data_Store_And_AI_Evolution_Principles.md`: RDBMS remains canonical, and NoSQL or auxiliary stores are considered only when Logical AI learning data grows beyond PostgreSQL / pgvector suitability.

# 8 Implementation Boundary

This document defines the Logical AI learning boundary only.
It does not define implementation code, SQL, migrations, Flutter, RPC, final local database schemas, or final device protocols.
