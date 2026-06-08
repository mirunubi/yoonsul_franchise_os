[ 80070_Local_Temporary_Ledger.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80010_Agent_Server_Master_Architecture.md %
% root\docs\80000_agent\80080_Agent_Sync_And_Event_Replay.md %

<< docs-only Local Temporary Ledger doctrine >>
<< local queue is not central truth >>

# 1 Local Temporary Ledger Definition

Local Temporary Ledger is the store-side evidence record maintained by Agent Runtime during normal, degraded, offline, failover, or recovery operation.

It preserves operational evidence until central comparison, conflict isolation, verification, replay, and audit lock can complete.

# 2 Local Ledger Is Not Central Truth

Local Temporary Ledger is not central truth.

Local records are evidence.
They must be compared with the Central Event Ledger before merge, replay, projection rebuild, or final sensitive decision.

# 3 Local Ledger As Evidence During Degraded Operation

During degraded operation, the local ledger preserves what the store-side runtime observed and attempted.

It supports:

- continuity.
- auditability.
- recovery.
- conflict detection.
- human review.
- central verification.

It does not approve sensitive operations by itself.

# 4 Append-Only Principle

Local Temporary Ledger should follow an append-only principle at the design level.

Corrections, dismissals, conflicts, recoveries, and reversals must be recorded as new evidence records rather than silent mutation of prior evidence.

Replay != Mutation.
Dismissed != Resolved.
No silent merge.
No overwrite.
Replay only after verification.

# 5 Required Evidence Fields

Design-level evidence fields include:

- offline operation ID.
- device ID.
- staff ID.
- local sequence number.
- local timestamp.
- checksum / hash.
- sync status.
- conflict status.
- replay status.

These fields are design requirements, not final database schema definitions.

# 6 Local Queue Candidates

Local queue candidates:

- Local Event Queue.
- Local Audit Queue.
- Local Task Queue.
- Failed Sync Queue.
- Manual Recovery Queue.

# 6.1 Local Ledger Components

Local ledger components include:

- Local Event Queue.
- Local Audit Queue.
- Local Task Queue.
- Failed Sync Queue.
- Manual Recovery Queue.
- Offline Operation ID.
- Device ID.
- Staff ID.
- Local Sequence Number.
- Local Timestamp.
- Checksum / Hash.
- Sync Status.
- Conflict Status.
- Replay Status.

# 7 Sync Status Meaning

Sync status indicates where a local record stands in the central comparison and upload process.

Examples:

- pending local upload.
- uploaded for comparison.
- duplicate candidate.
- missing event candidate.
- sequence conflict candidate.
- reference mismatch candidate.
- isolated conflict.
- verified for replay.
- audit locked.

# 8 Conflict Status Meaning

Conflict status indicates whether the local evidence conflicts with central truth, another local timeline, or required references.

Conflict status must be visible before replay.
Conflict isolation must happen before projection rebuild.

# 9 Replay Status Meaning

Replay status indicates whether the local evidence has been safely replayed into central projections after verification.

Replay status must never imply that the original local evidence was mutated.

# 10 Implementation Boundary

This document defines local ledger doctrine only.
It does not define implementation code, SQL, migrations, Flutter, RPC, or final local database schemas.
