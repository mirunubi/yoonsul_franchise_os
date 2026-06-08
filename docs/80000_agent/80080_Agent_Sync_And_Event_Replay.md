[ 80080_Agent_Sync_And_Event_Replay.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80070_Local_Temporary_Ledger.md %
% root\docs\80000_agent\80040_Primary_Secondary_Agent_Failover.md %

<< docs-only Agent sync and replay doctrine >>
<< sync is not blind merge, replay is not mutation >>

# 1 Purpose

This document defines the design-level sync and event replay doctrine for Agent Runtime records created during normal, degraded, offline, failover, or recovery operation.

# 2 Preservation Rules

Agent sync and replay must preserve:

- Replay != Mutation.
- Sync != Blind merge.
- No silent merge.
- No overwrite.
- conflict isolation before replay.
- replay only after verification.
- projection rebuild only after verification.
- audit lock after verification.

# 3 Replay Flow

The replay flow is:

1. Local event upload.
2. Central Event Ledger comparison.
3. Duplicate check.
4. Missing event check.
5. Sequence inversion check.
6. Reference mismatch check.
7. Conflict event isolation.
8. Safe event replay.
9. Projection rebuild.
10. Manager / HQ verification.
11. Audit lock.

# 3.1 Backup Data Center Replay And Integrity Check

When backup data center or cross-cloud failover is active, replay must include backup and restored ledger integrity checks.

The replay path must compare:

- primary Event Ledger.
- backup Event Ledger.
- Audit Ledger backup.
- Projection backup.
- Local Temporary Ledger evidence.

Secondary operation is not silent authority transfer.
After primary recovery, central verification, replay, and integrity checks are required before sensitive operations return to normal finalization.

# 4 Local Event Upload

Local event upload sends local evidence to central systems for comparison.

Upload does not mean acceptance.
Upload does not mean merge.
Upload does not mean replay.

# 5 Central Event Ledger Comparison

Central Event Ledger comparison determines how local evidence relates to central truth.

The comparison must identify:

- already known events.
- missing central events.
- local-only events.
- divergent sequence windows.
- reference mismatches.
- duplicate candidates.
- split-brain candidates.

# 6 Duplicate Check

Duplicate check prevents repeated local evidence from being replayed as new operational truth.

Duplicate candidates must be marked and reviewed before replay.

# 7 Missing Event Check

Missing event check identifies gaps between local evidence and central records.

Missing events may indicate:

- offline operation.
- failed upload.
- local queue backlog.
- central rejection.
- split-brain or timeline divergence.

# 8 Sequence Inversion Check

Sequence inversion check identifies local records that arrived or were created out of expected order.

Sequence inversion requires isolation before replay because projection rebuild depends on chronological integrity.

# 9 Reference Mismatch Check

Reference mismatch check identifies local records that point to missing, stale, or conflicting references.

Reference mismatch examples:

- order reference mismatch.
- payment reference mismatch.
- staff reference mismatch.
- device reference mismatch.
- inventory reference mismatch.
- shift reference mismatch.

# 10 Conflict Event Isolation

Conflict events must be isolated before replay.

Conflict isolation protects central truth from blind merge and protects local evidence from silent deletion.

# 11 Safe Event Replay

Safe event replay occurs only after comparison and conflict handling.

Replay applies verified event meaning to central operational projections without mutating the original evidence.

# 12 Projection Rebuild

Projection rebuild may occur only after verification.

Projection rebuild must not occur from unverified degraded records, unresolved split-brain windows, or isolated conflict events.

# 13 Manager / HQ Verification

Manager or HQ verification is required before finalizing sensitive recovery outcomes.

Verification is especially required for:

- split-brain recovery.
- refund-sensitive windows.
- settlement-sensitive windows.
- payroll-sensitive windows.
- compensation-sensitive windows.
- Physical AI task approval windows.

# 14 Audit Lock

Audit lock occurs after verification.

Audit lock preserves the reviewed recovery outcome and prevents silent mutation of the verified record chain.

# 15 Implementation Boundary

This document defines sync and replay doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
