[ 3rd_00002_Naming_Rules.md ]

% root\docs\0002_Naming_Rules.md %
% root\docs\3rd_00000_Readme.md %

<< docs-only · Phase 3 runtime naming rules >>
<< adapted from 0002 only where necessary for Phase 3 runtime docs >>

This document defines the naming rules for the Phase 3 Runtime Program.
It keeps naming stable, searchable, and compatible with the independent 3rd_* civilization space.

# 1 Naming Principle

< Naming Rules >

    ( Predictable Name )

        (( Searchable ))

        (( Durable ))

- Names must reveal role, scope, and place in the runtime universe.
- Temporary names should not become permanent architecture.
- Searchability matters for humans and machine-assisted tooling.

# 2 Document File Naming Rule

< Document >

    ( File Name Format )

Phase 3 runtime Markdown documents use:

```text
NNNN_Phase3_Runtime_Domain_Purpose_Type.md
```

Examples:

```text
3rd_00000_Readme.md
3rd_00018_Governance_Constitution.md
3rd_10510_Frontline_Order_Capture_Constitution.md
3rd_10620_Runtime_Orchestration_Model.md
```

Not allowed:

```text
phase3-readme.md
10000-phase3-runtime.md
Phase3Runtime.md
```

# 3 Document Numbering Rule

< Document >

    ( Global Unique Number )

- Every Phase 3 Markdown document must use a unique 4-digit numeric prefix.
- Prefixes in the 3rd_* Phase 3 civilization space are reserved for the Phase 3 program only.
- The same numeric stem must not be reused for different files in the same namespace.
- The index document is the source of discoverability, not the authority itself.

# 4 Directory Naming Rule

< Directory >

    ( Lower Snake Case )

Phase 3 directories must use lower_snake_case.

Allowed examples:

```text
docs/phase3_runtime
docs/frontline_runtime
docs/hq_operational_brain
docs/supply_runtime
docs/customer_runtime
docs/runtime_orchestration
```

Not allowed:

```text
Phase3Runtime
frontline-runtime
HQRuntime
```

# 5 Naming And Bridge Rule

< Bridge Naming >

- `0500` is the bridge from the current docs system into Phase 3.
- `3rd_*` is the independent Phase 3 civilization namespace.
- bridge documents should be named so humans can tell they are ingress documents, not subsystem implementation docs.

Suggested bridge-style pattern:

```text
0500_Franchise_Frontline_OS_Phase3_Constitution.md
```

# 6 Runtime Surface Naming Rule

< Runtime Surface >

Runtime surfaces in Phase 3 should name their role clearly.

Examples:

```text
frontline
hq
supply
customer
orchestration
recovery
override
audit
```

Avoid names that hide authority or blur layer boundaries.

# 7 Reference Rule

< Reference >

- Use explicit `root\docs\NNNN_File_Name.md` references while the spine is still in the docs root.
- When later moving to subdirectories, update the index and map together.
- Keep the bridge document visible in navigation until subsystem split is mature.

# 8 Good Naming Checklist

< Naming Quality >

    ( Required Checklist )

| No | Condition | Check |
| --- | --- | --- |
| 1 | Role | the name tells whether the document is readme, index, map, or constitution |
| 2 | Location | the band makes the Phase 3 position obvious |
| 3 | Pipeline Position | the document can be found in the read order |
| 4 | Domain Boundary | the name does not leak implementation scope |
| 5 | State | state-related docs are labeled as such |
| 6 | Exception / Fallback | recovery-oriented docs are easy to identify |
| 7 | Active / Future / Deprecated | status is obvious when relevant |
| 8 | Links | related documents can be discovered through naming |
| 9 | Implementation Level | conceptual docs are distinguishable from implementation docs |
| 10 | Machine Readability | names are machine-searchable and human-readable |
| 11 | Why | the name reflects the why of the doc |
| 12 | Operational Reality | the name maps to the real operational layer |

# 9 Forbidden Naming Patterns

< Forbidden >

- hyphenated document file names.
- ambiguous abbreviations that hide layer or authority.
- names that imply implementation when the doc is constitutional.
- names that collapse bridge docs and Phase 3 docs into one bucket.

# 10 Unresolved Decisions

< Unresolved Decisions >

| decision | question |
| -------- | -------- |
| future directory namespace | should Phase 3 docs eventually move under docs/phase3_runtime/ or remain root-indexed? |
| band granularity | should future bands be grouped by 10s, 50s, or 100s? |
| bridge naming | should all bridge docs share a common `0500_*` pattern or vary by program entry? |

The naming rules are stable enough for Phase 3 documentation authoring.
