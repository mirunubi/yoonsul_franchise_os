[ 62010_Franchise_Inventory_Master_Model.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\62000_scm\62005_Franchise_Authority_And_Legal_Entity_Model.md %

<< docs-only 쨌 franchise inventory master model >>

# 1 Purpose

This document defines the development-design master boundary for franchise inventory concepts.
It is not an implementation schema and does not define database tables, RLS, inventory calculation code, supplier ordering automation, or production authorization code.

The authority terms tenant, company, legal_entity, owner_group, and store follow `62005_Franchise_Authority_And_Legal_Entity_Model.md`.

# 2 Inventory Scope

Prepared Inventory is one inventory subtype, not the whole inventory system.

General inventory includes:

- raw materials.
- prepared items.
- finished/sellable items.
- packaging.
- operating supplies.
- tools.
- sanitation supplies.

Inventory type candidates:

- RAW_MATERIAL
- PREPARED_ITEM
- FINISHED_ITEM
- PACKAGING
- OPERATING_SUPPLY
- TOOL
- SANITATION_SUPPLY

These are design candidates only.
They do not define final database enum values, table structures, application constants, or migration content.

# 3 Authority Boundary

Inventory authority belongs to SCM/Inventory domain.

Agent observes, recommends, prompts, escalates, and records Event/Audit/Exception.
Agent does not silently adjust inventory or execute reorder.

Reorder recommendation does not equal supplier order execution.
Inventory gap evidence does not equal adjustment approval.
Manager or authorized owner-group approval may be required according to policy and store assignment.

# 4 Prepared Inventory Position

Prepared inventory represents store-made or store-portioned stock such as hummus packs, custom sauce portions, pickled ingredients, prepared vegetables, and other long-hold prepared items.

Prepared inventory may relate to:

- raw ingredient deduction.
- prepared item increase.
- production batch visibility.
- actual count.
- gap detection.
- reorder recommendation.

Prepared inventory remains inside the broader inventory model.
It should not replace raw materials, finished items, packaging, operating supplies, tools, or sanitation supplies.

# 5 Store-Level Evidence

Most inventory evidence is generated at store level.

Store-level inventory evidence may include:

- inbound stock receipt.
- prepared production event.
- recipe usage.
- disposal.
- transfer.
- actual count.
- gap detection.
- adjustment request.
- manager confirmation.
- Event/Audit/Exception record.

Store-level evidence may become visible to owner_group, legal_entity, company, HQ, or tenant-level roles only according to authority rules.
Store visibility does not automatically create cross-store authority.

# 6 Agent Integration

Agent Runtime may integrate with SCM/Inventory for:

- production prompts.
- inventory gap visibility.
- reorder recommendation.
- shortage escalation.
- Event/Audit/Exception preservation.
- manager or owner-group confirmation routing.

Agent Runtime may not:

- own inventory truth.
- silently adjust inventory.
- execute supplier ordering automation.
- bypass legal_entity, owner_group, or store authority boundaries.
- treat recommendation as execution.
- treat evidence as approval.

# 7 Non-Implementation Boundary

This document does not define:

- final DB schema.
- final tenant schema.
- RLS.
- final authorization code.
- final reorder algorithm.
- final inventory count logic.
- final supplier ordering automation.

This document is development-design only.
It does not create SQL, migrations, Flutter implementation, inventory logic, reorder logic, tenant tables, RLS policies, AI, pgvector implementation, or supplier ordering automation.
