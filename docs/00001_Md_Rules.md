[ 3rd_00001_Md_Rules.md ]

% root\docs\0001_Md_Rules.md %
% root\docs\3rd_00000_Readme.md %

<< docs-only · Phase 3 runtime Markdown rules >>
<< adapted from 0001 only where necessary for Phase 3 runtime docs >>

This document defines the Markdown rules for the Phase 3 Runtime Program documents.
It mirrors the current Markdown constitution, but it is scoped to the 3rd_* Phase 3 civilization space.

# 1 Markdown Header Rule

< Markdown Structure >

    ( Header Depth )

        (( Numbered Heading ))

- Use numbered headings for all substantive sections.
- Keep heading depth stable and predictable.
- Avoid unnumbered headings for core constitutional content.

Example:

```text
# 1 Main Topic

## 1.1 Sub Topic

### 1.1.1 Detail Topic
```

# 2 Topic Symbol Rule

< Topic Symbol >

    ( Required Meaning )

        (( Visual Parsing ))

- `[ FILE_NAME.md ]` : title block for the document.
- `% root\docs\3rd_00000_Readme.md %` : reference document marker.
- `< >` : level 1 topic.
- `( )` : level 2 topic.
- `(( ))` : level 3 topic.
- `<< >>` : requirement, check, or constraint.
- `{ }` : exception handling, special state, or fallback candidate.
- `-` : markdown list item.

# 3 Required Header Rule

< Markdown Structure >

    ( Required Header )

Every Phase 3 runtime markdown document should start with:

```text
[ FILE_NAME.md ]

% root\docs\0001_Md_Rules.md %
% root\docs\3rd_00000_Readme.md %

<< docs-only · Phase 3 runtime constitution candidate >>
```

# 4 Hyphen Rule

< Markdown Symbol >

    ( Hyphen Scope )

- Use `-` for Markdown list markers.
- Do not use hyphenated file names for document names.
- Use underscore-separated file names with numeric prefixes.

Allowed:

```text
- define the runtime universe
- keep recovery first
```

Not allowed:

```text
phase-3-runtime.md
10000-phase3-readme.md
```

# 5 Reference Rule

< Documentation Reference >

    ( Stable Path )

- Reference Phase 3 documents explicitly.
- Keep the bridge document visible when the current docs system needs a landing path.
- When a document moves later, update index and map documents together.

Preferred patterns:

```text
% root\docs\3rd_00000_Readme.md %
% root\docs\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\0500_Franchise_Frontline_OS_Phase3_Constitution.md %
```

# 6 Good Markdown Document Rule

< Markdown Quality >

    ( Human And AI Readable )

Phase 3 documents should be easy to scan for:

- role.
- layer boundary.
- recovery rule.
- human override.
- non-goals.
- future band placement.

Good Phase 3 Markdown documents explain the runtime universe without implementing it.

# 7 Good Markdown Checklist

< Markdown Quality >

    ( Required Checklist )

| No | Condition | Check |
| --- | --- | --- |
| 1 | Role | constitution, readme, naming, index, map, or governance intent is clear |
| 2 | Location | the document belongs to the 10000~29999 Phase 3 space |
| 3 | Pipeline Position | the document shows where it sits in the Phase 3 read order |
| 4 | Domain Boundary | the document stays inside runtime constitution scope |
| 5 | State | state, recovery, override, or orchestration language is explicit when needed |
| 6 | Exception / Fallback | failure and recovery paths are stated when relevant |
| 7 | Active / Future / Deprecated | current, future, or reserved status is visible |
| 8 | Links | bridge and related documents are visible |
| 9 | Implementation Level | conceptual only unless a later document explicitly changes scope |
| 10 | Machine Readability | numbering, sections, and constraints are easy to follow |
| 11 | Why | rationale is present |
| 12 | Operational Reality | the document reflects real frontline/HQ/supply/customer reality |

# 8 Phase 3 Specific Rule

< Phase 3 Specific >

- keep the bridge document visible, but separate from the independent 10000~29999 spine.
- do not mix SaaS 30000 namespace material into Phase 3 runtime docs.
- do not put SQL/RPC/Flutter implementation details into constitution docs.
- do not use the current 0000/0005/0007/0018 onboarding spine as a substitute for Phase 3.

# 9 Pipeline Navigation Rule

< Navigation >

Recommended related documents should point to:

- the Phase 3 readme.
- the Phase 3 naming rules.
- the Phase 3 number index.
- the Phase 3 directory map.
- the Phase 3 governance constitution.
- the 0500 bridge document when needed.

# 10 State And Fallback Rule

< State Fallback >

When a Phase 3 document describes state:

- name the state.
- show the transition.
- show the recovery or fallback lane.
- show the human owner.
- avoid confusing projection with authority.

# 11 Document Status Rule

< Document Status >

Phase 3 docs should explicitly say whether they are:

- constitution.
- bridge.
- index.
- map.
- governance.
- future reserve.

This keeps the new program spine searchable and predictable.
