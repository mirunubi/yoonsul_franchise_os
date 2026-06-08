[ 3rd_00007_Directory_Map.md ]

% root\docs\0001_Md_Rules.md %
% root\docs\0002_Naming_Rules.md %
% root\docs\0004_Architecture_Numbering.md %
% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %

<< docs-only ì¨?Phase 3 civilization directory map >>
<< path visibility for the independent 3rd_* civilization namespace >>

This document maps the Phase 3 civilization namespace as a directory and document visibility tree.
It is a planning map for the independent spine, not an implementation plan.

# 1 Purpose

< Directory Map >

The map exists so that the Phase 3 civilization documents can be found without guessing.
It also makes the bridge from the current docs system explicit.

# 2 Directory Visibility Principle

< Principle >

- `0007` is the current directory visibility map for the current docs system.
- `3rd_00007` is the Phase 3 civilization directory visibility map.
- they are separate because the new civilization namespace should not be merged into the old onboarding spine yet.

# 3 High-Level Lane Topology

< Lane Topology >

```text
docs/
    0500_Franchise_Frontline_OS_Phase3_Constitution.md   (bridge / ingress only)
    3rd/
        3rd_00000_Readme.md
        3rd_00001_Md_Rules.md
        3rd_00002_Naming_Rules.md
        3rd_00005_Number_Index.md
        3rd_00007_Directory_Map.md
        3rd_00018_Governance_Constitution.md

        frontline/
        store_ops/
        hq/
        commerce/
        scm/
        wms_logistics/
        supplier/
        consumer/
        future/
```

The subdirectories above are the Phase 3 civilization boundary.
They are lane anchors first, subsystem trees later.

# 4 Band To Directory Proposal

< Mapping >

| band | proposed future directory |
| ---- | ------------------------ |
| 3rd_00000-3rd_00099 | docs/3rd/ (constitution / spine / governance) |
| 3rd_01000-3rd_01999 | docs/3rd/frontline/ |
| 3rd_02000-3rd_02999 | docs/3rd/store_ops/ |
| 3rd_03000-3rd_03999 | docs/3rd/hq/ |
| 3rd_04000-3rd_04999 | docs/3rd/commerce/ |
| 3rd_05000-3rd_05999 | docs/3rd/scm/ |
| 3rd_06000-3rd_06999 | docs/3rd/wms_logistics/ |
| 3rd_07000-3rd_07999 | docs/3rd/supplier/ |
| 3rd_08000-3rd_08999 | docs/3rd/consumer/ or reserved |
| 3rd_09000-3rd_09999 | docs/3rd/future/ |
| 3rd_10000-3rd_29999 | reserved future directories |

# 5 Current Spine Documents

< Current Spine >

- `0500_Franchise_Frontline_OS_Phase3_Constitution.md` ??bridge from current docs system.
- `3rd_00000_Readme.md` ??program hub.
- `3rd_00001_Md_Rules.md` ??markdown rules.
- `3rd_00002_Naming_Rules.md` ??naming rules.
- `3rd_00005_Number_Index.md` ??number index.
- `3rd_00007_Directory_Map.md` ??this map.
- `3rd_00018_Governance_Constitution.md` ??runtime constitution.

# 6 Cross-Lane Topology Visibility

< Topology Visibility >

The major Phase 3 civilization lanes are intentionally visible in the directory map:

- Frontline Runtime.
- Store Operations.
- HQ Operational Brain.
- Commerce / CRM.
- SCM / Manufacturing.
- WMS / Logistics.
- Supplier Ecosystem.

These lanes are distinct directories because they are distinct ownership boundaries.

# 7 Path Visibility Rules

< Path Visibility >

- keep bridge docs visible but separate from the civilization namespace.
- keep Phase 3 docs searchable by number and purpose.
- do not mix SaaS 30000 namespace docs into this map.
- do not mix current onboarding spine files into this map as if they were Phase 3 runtime docs.

# 8 Unresolved Decisions

< Unresolved Decisions >

| decision | question |
| -------- | -------- |
| future folder names | should the future folders use `docs/3rd/` as the long-term namespace root? |
| band-to-folder exactness | should every band get its own folder, or should some bands share a parent folder? |
| bridge placement | should the 0500 bridge stay at docs root or move into a bridge folder later? |

This map is a planning artifact for the Phase 3 civilization spine.
