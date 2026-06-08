[ 3rd_01250_Kiosk_Self_Service_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Readme.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01200_POS_Transactional_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01050_Operational_Agent_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01100_KDS_Operational_Recovery_Runtime_Constitution.md %

<< 3rd frontline kiosk self-service constitution >>
<< customer-facing transactional intake under POS governance only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines Kiosk as a customer-facing self-service transactional surface operating under POS runtime governance.
It is a customer entry point, not an independent operational authority.

# 1 What Kiosk Runtime Is

< Kiosk Runtime >

Kiosk Runtime is the self-service customer-facing intake surface that helps the customer initiate a transaction in a controlled frontline environment.

It exists to:

- present self-service transactional intake.
- guide the customer through entry and selection.
- hand transactional intent into POS governance.

Kiosk is not an independent operational authority.

# 2 Core Relationships

< Runtime Relations >

| system | kiosk relationship |
| ------ | ------------------ |
| POS | transaction authority owner; kiosk operates under POS governance |
| Operational Agent | observation / mediation layer that may assist visibility and recovery context but does not own kiosk |
| KDS | downstream kitchen coordination runtime; kiosk does not own it |
| DID | customer-facing projection and continuity surface; separate from kiosk intake authority |
| CMS | content/surface guidance that may shape kiosk presentation, but not kiosk authority |
| Store Operations | operational governance lane that can intervene or coordinate around kiosk conditions |

Rules:

- kiosk is subordinate to POS runtime governance.
- kiosk may intake intent, but it does not own transaction authority.
- kiosk does not own recovery coordination.
- kiosk does not own escalation authority.
- kiosk presentation is not operational authority.

# 3 Self-Service Transactional Philosophy

< Self Service >

Kiosk is designed to let the customer initiate and proceed through a transaction without requiring staff to act as the primary input surface.
That convenience does not make kiosk a separate authority plane.

Principles:

- self-service is still governed.
- the surface may guide, but it does not independently decide.
- customer convenience must not become silent authority drift.
- the intake path should remain legible, bounded, and recoverable.

# 4 Customer Interaction And Intake

< Intake >

Kiosk is the customer interaction surface for transaction intake.
It helps the customer express intent, choose items, and move toward POS-governed transaction processing.

Concepts:

- customer interaction.
- self-service selection.
- intake confirmation.
- guided continuation into POS-owned transactional authority.

Kiosk should make the intake path easy to use, but it must not confuse convenience with authority.

# 5 Transactional Intake, Payment Initiation, Recovery, Escalation

< Flow Split >

| concept | kiosk relationship |
| ------- | ------------------ |
| transactional intake | owned as a surface for customer entry |
| payment initiation | may be initiated through the surface, but authority remains with POS |
| operational recovery | outside kiosk ownership |
| escalation | outside kiosk ownership |

Rules:

- kiosk can help start the transaction.
- POS owns the transaction authority.
- recovery and escalation belong to the broader operational mesh.

# 6 Runtime Authority Vs Runtime Surface

< Surface And Authority >

Kiosk is a runtime surface, not a runtime authority.

Principles:

- the surface can collect intent.
- the authority can validate and advance state.
- the surface can present state.
- the authority owns the transactional truth.

# 7 Human Intervention And Correction

< Human Intervention >

Human intervention may still be needed when the kiosk path is ambiguous, interrupted, or incorrect.
That intervention belongs to the broader human-governed runtime, not to kiosk autonomy.

Principles:

- humans may correct or interrupt.
- kiosk should not silently hide correction history.
- dismissal is not resolution.
- evidence is not approval.
- recommendation is not execution.

# 8 Boundary Split: Surface, Transaction, Operation, Recovery

< Boundary Split >

| boundary | meaning |
| -------- | ------- |
| customer interaction surface | kiosk's visible self-service interface |
| transaction authority | POS-owned transactional state authority |
| operational authority | store / HQ / operational governance authority |
| recovery coordination | broader mesh handling anomalies, escalation, and restoration |

Kiosk belongs to the first boundary only.

# 9 What Does Not Belong Here

< Out Of Scope >

Kiosk does not own:

- POS transaction authority.
- operational recovery governance.
- escalation routing.
- kitchen coordination authority.
- HQ policy and rollout governance.
- customer commerce experience ownership beyond the intake surface.
- deep constitutional governance language that belongs in `3rd_00018`.
- implementation details, SQL, Flutter, RPC, or contracts.

# 10 Future Subsystem Candidates

< Future Candidates >

Possible future subsystem directions from this lane include:

- kiosk intake flow governance.
- self-service guidance and correction surfaces.
- customer entry and assisted self-service boundaries.
- kiosk projection and intake continuity summaries.

These are future subsystem candidates, not implementation commitments.

# 11 No Implementation Details

< Non-Goals >

This document does not define:

- database tables or schemas.
- SQL, triggers, migrations, or RPC contracts.
- Flutter pages or route flows.
- device SDK behavior.
- detailed event catalogues.
- state machine code.

The job of this constitution is to define the kiosk boundary, not the implementation.
