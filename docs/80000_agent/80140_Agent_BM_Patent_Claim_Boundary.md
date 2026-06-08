[ 80140_Agent_BM_Patent_Claim_Boundary.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80010_Agent_Server_Master_Architecture.md %
% root\docs\80000_agent\80070_Local_Temporary_Ledger.md %
% root\docs\80000_agent\80110_Logical_AI_Learning_Interface.md %
% root\docs\80000_agent\80120_Physical_AI_Task_Translation_Module.md %
% root\docs\80000_agent\80150_Agent_Backup_Data_Center_And_Cross_Cloud_Failover.md %

<< docs-only Agent BM patent claim boundary >>
<< this is not a legal filing; patent attorney review is required >>

# 1 Purpose

This document defines a design-level boundary for Agent BM patent-oriented thinking.

This is not a legal filing.
Patent attorney review is required before any filing, claim drafting, prior art analysis, or legal representation.

# 2 Patent-Oriented Summary

The Agent Server concept is a lightweight store-side operational runtime that observes store systems, translates activity into Task, Event, Audit, and Exception evidence, detects exceptions, manages local queues, supports recovery, records audit trails, syncs with central systems, and creates bounded interfaces for Logical AI learning and future Physical AI translation.

The core differentiator is not ordinary POS, KDS, Kiosk, or delivery processing.
The differentiator is the recovery-first runtime structure around local evidence, degraded operation, backup and cross-cloud failover, human approval, replay integrity, Logical AI decision learning, and future Physical AI task translation.

# 3 BM Claim Layer Vs Implementation Layer

The BM claim layer describes system concept, runtime relationship, evidence flow, failover doctrine, recovery doctrine, learning loop, and translation boundary.

The implementation layer describes concrete software, storage, protocol, screen, process, and vendor mechanics.

The BM claim layer must remain separate from implementation details.

# 4 Differentiation From Ordinary Store Systems

Ordinary POS, KDS, Kiosk, and delivery systems generally process domain-specific store functions.

Agent Runtime is different because it:

- observes across store runtime domains.
- preserves local evidence during degraded operation.
- treats local queue as evidence, not central truth.
- supports Primary / Secondary promotion without automatic overwrite.
- isolates conflicts before replay.
- learns from manager approval, rejection, modification, and outcome.
- separates Logical AI message from Physical AI device command.
- requires manager approval before physical task translation.
- requires device result return as Event and Audit.
- creates Recovery Event on Physical AI failure.

# 5 Claim Candidate Groups

Claim candidate groups include:

- DB backup / replay / integrity check.
- Local Temporary Ledger.
- cross-cloud / backup data center failover.
- Agent module failure.
- module-level failover.
- lightweight Agent deployment.
- Primary / Secondary promotion.
- Logical AI decision message.
- Physical AI task translation.
- Physical AI result event collection.

# 6 BM Claim Layer

BM Claim Layer includes:

- system concept.
- runtime structure.
- ledger structure.
- backup/failover concept.
- exception and recovery concept.
- Agent failover concept.
- Logical AI learning concept.
- Physical AI translation concept.

# 7 Implementation Layer

Implementation Layer includes:

- actual DB schema.
- RPC.
- Flutter screen.
- Agent process.
- local storage engine.
- sync protocol.
- device protocol.
- cloud vendor configuration.

Implementation Layer content must not be placed in this document.

# 8 Boundary Principles

Boundary principles:

- Agent != Operator.
- Recommendation != Execution.
- Evidence != Approval.
- Dismissed != Resolved.
- Replay != Mutation.
- Logical AI message != Physical AI device command.
- Manager approval is required before physical task translation.
- Device result must return as Event and Audit.
- Physical AI failure must create Recovery Event.
- Human intervention path is required.

# 9 Implementation Prohibition

Do not put implementation code into this document.

This document does not define SQL, migrations, Flutter, RPC, final local database schemas, final sync protocols, final device protocols, or actual Agent process code.
