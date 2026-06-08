[ 80100_Decision_Message_Repository.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80000_Agent_Runtime_Readme.md %
% root\docs\80000_agent\80010_Agent_Server_Master_Architecture.md %
% root\docs\80000_agent\80110_Logical_AI_Learning_Interface.md %

<< docs-only Decision Message Repository doctrine >>
<< recommendation is not execution, evidence is not approval >>

# 1 Purpose

Decision Message Repository is the design-level record space for Logical AI-generated manager decision messages and the human decisions that follow them.

The repository preserves the recommendation, the manager response, the operational result, and later learning status.

The AI recommendation itself is not the most valuable learning data.
The manager approval, rejection, modification, and resulting operational outcome are the core learning asset.
The message generation context must be preserved so later learning can distinguish recommendation quality from human operational judgment.

# 2 Decision Message Scope

A decision message is a Logical AI-generated recommendation or approval request delivered to a manager, owner, or HQ reviewer.

The message may summarize:

- current situation.
- related Task records.
- related Event records.
- related Exception records.
- recommended action.
- confidence level if applicable.
- expected operational impact.
- required approval boundary.

Logical AI message != Physical AI device command.

# 3 Repository Content

Decision Message Repository should preserve:

- Logical AI-generated manager decision messages.
- situation snapshot.
- related Task, Event, and Exception context.
- message generation context.
- recommendation content.
- confidence level if applicable.
- manager approve, reject, or modify response.
- execution result.
- customer reaction if applicable.
- recovery success or failure.
- later learning status.

These are design-level record requirements, not final local database schema definitions.

# 4 Manager Response

Manager response is the authority-bearing learning signal.

Possible response meanings include:

- approved as recommended.
- rejected.
- modified before approval.
- deferred.
- escalated to owner or HQ.
- dismissed without resolution.

Dismissed != Resolved.
Evidence != Approval.

# 5 Execution Result

Execution result captures what happened after the human decision.

Execution result may include:

- action applied.
- action not applied.
- partial application.
- operational improvement.
- operational worsening.
- customer claim avoided.
- customer claim occurred.
- recovery succeeded.
- recovery failed.

# 6 Learning Status

Later learning status marks whether the decision and outcome were used for future Logical AI learning.

Learning status may indicate:

- pending review.
- eligible for learning.
- excluded from learning.
- ambiguous outcome.
- conflict isolated.
- verified learning input.

# 7 Example Manager Decision Message

Example:

> Based on current KDS load and packing backlog, it is recommended to change delivery app preparation time from 35 minutes to 50 minutes between 18:40 and 19:10.

This message requests human decision.
It is not a direct store mutation.
It is not a Physical AI command.

# 7.1 Operational Outcome Learning Example

Logical AI may recommend changing delivery app preparation time from 35 minutes to 50 minutes because KDS load and packing backlog are high.

The manager may approve, reject, or modify the decision message.
The outcome is later linked back to:

- customer wait time.
- kitchen load.
- packing backlog.
- customer complaints.
- recovery events.
- future recommendation quality.

The AI recommendation itself is not the most valuable data.
The manager's approval, rejection, modification, and the actual operational result are the core learning asset.

# 8 Implementation Boundary

This document defines the Decision Message Repository as a design boundary only.
It does not define implementation code, SQL, migrations, Flutter, RPC, final local database schemas, or final device protocols.
