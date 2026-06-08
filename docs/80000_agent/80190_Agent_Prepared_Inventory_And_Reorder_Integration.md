[ 80190_Agent_Prepared_Inventory_And_Reorder_Integration.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80160_Agent_Runtime_Required_Capability_Integration.md %

<< docs-only 쨌 Agent prepared inventory and reorder integration >>

# 1 Purpose

This document defines a development-design concept for store-made prepared inventory production, inventory correction, and reorder recommendation.
It covers afternoon production routines such as hummus packs, Yoonsul custom sauces, pickled ingredients, prepared vegetables, and other long-hold prepared items.

The purpose is to make prepared inventory production visible, countable, correctable, recommendable, and auditable without turning Agent Runtime into the final inventory authority or an autonomous reorder executor.

Authority boundary:

- General inventory authority is governed by SCM/Inventory.
- Tenant/company/legal_entity/owner_group/store terms follow `62005_Franchise_Authority_And_Legal_Entity_Model.md`.
- Agent observes and recommends; it does not own inventory authority.
- Reorder recommendation does not equal reorder execution.
- Inventory gap evidence does not equal adjustment approval.

# 2 Core Flow

< Prepared Inventory And Reorder Flow >

```text
Afternoon Production Routine
        =>
Prepared Inventory Production Record
        =>
Raw Ingredient Deduction
        =>
Prepared Inventory Increase
        =>
Theoretical Inventory Update
        =>
Actual Inventory Count
        =>
Gap Detection / Adjustment
        =>
Forecast Reorder Recommendation
        =>
Agent Recommendation / Manager Approval / Audit
```

The flow separates production recording, theoretical inventory movement, actual count, gap explanation, recommendation, approval, and audit.
Agent Runtime may observe and recommend, but it must not silently adjust inventory or execute reorder decisions without required human approval.

# 3 Prepared Inventory Types

Prepared inventory examples include:

- hummus sealed packs.
- Yoonsul custom sauce portions.
- pickled vegetables.
- prepared vegetable mix.
- cooked grain or rice batch.
- protein cup components.
- long-hold sauce bases.
- sealed topping packs.
- pre-portioned side components.

Prepared inventory is store-made or store-portioned stock that sits between raw ingredients and final recipe usage.
It should be treated as operational inventory, not merely as a recipe note.

# 4 Production Record Concept

For each production event, conceptual fields may include:

- production item.
- production batch or lot.
- production time.
- responsible staff or station.
- input raw ingredients.
- expected output quantity.
- actual output quantity.
- unit size.
- storage method.
- use-by time or shelf-life.
- quality check status.
- waste or production loss.
- manager confirmation if required.

These fields are conceptual design elements only.
They do not define final database schema, table names, columns, inventory enums, RPC contracts, or implementation logic.

# 5 Raw Ingredient Deduction And Prepared Inventory Increase

Production must deduct raw ingredients and increase prepared inventory.

Example raw ingredient decrease:

- chickpeas.
- tahini.
- olive oil.
- lemon juice.
- salt.

Example prepared inventory increase:

- hummus 250g sealed pack.

Yoonsul custom sauce production may deduct raw sauce ingredients and increase pre-portioned sauce inventory.

The design principle is that prepared production is a stock conversion event:

- raw inventory decreases.
- prepared inventory increases.
- production loss or waste may be recorded.
- quality or manager confirmation may be required.
- Event and Audit concepts preserve evidence.

# 6 Theoretical Vs Actual Inventory Correction

Theoretical inventory is calculated from:

```text
inbound stock + production - recipe usage - disposal - transfer - correction
```

Actual inventory comes from staff count, weight, scan, or manager check.

Gap causes may include:

- portioning error.
- cooking loss.
- spoilage.
- unrecorded disposal.
- extra customer service.
- recipe deviation.
- yield variation.
- inbound weight difference.
- staff mistake.

State candidates:

- INVENTORY_THEORETICAL
- INVENTORY_COUNTED
- INVENTORY_GAP_DETECTED
- INVENTORY_ADJUSTMENT_REQUESTED
- MANAGER_CONFIRM_REQUIRED
- INVENTORY_ADJUSTED
- AUDIT_RECORDED

Inventory correction is sensitive operational evidence.
Agent Runtime may flag and recommend correction, but manager confirmation remains required where policy marks the adjustment as sensitive.

# 7 Forecast Reorder Recommendation

Forecast reorder recommendation may consider:

- expected sales.
- current stock.
- prepared inventory stock.
- raw ingredient stock.
- safety stock.
- lead time.
- production capacity.
- expected shortage time.
- recommended production quantity.
- recommended order quantity.

Examples:

- hummus packs may run out before dinner peak.
- Yoonsul custom sauce may require afternoon production increase.
- raw vegetables may fall below safety stock based on sales velocity.

Recommendation is advisory.
It should become manager-visible with supporting context, not silently become a supplier order or inventory adjustment.

# 8 Agent Role

Agent may:

- observe production schedule.
- prompt afternoon production routine.
- collect production completion.
- detect raw ingredient shortage.
- compare theoretical and actual inventory.
- generate reorder recommendation.
- recommend additional production.
- flag inventory gap.
- escalate manager confirmation.
- create Event/Audit/Exception.

Agent may not:

- silently adjust inventory.
- auto-finalize reorder without approval.
- hide inventory gaps.
- treat recommendation as execution.
- replace manager confirmation for sensitive adjustments.

Agent Runtime remains an observation, prompt, recommendation, escalation, Event, Audit, and Exception support layer.
Inventory, SCM, Store Operations, and manager approval boundaries remain separate.

# 9 KDS/DID Integration

## 9.1 KDS

KDS may:

- show afternoon production tasks.
- show required production quantity.
- allow start/completion/delay/shortage action.
- expose manager-call or shortage escalation where required.

KDS does not treat dismissed prompt as completed.

## 9.2 Staff-Only DID

Staff-only DID may:

- show production routine status.
- show overdue production task.
- show internal station prompt.

Staff-only DID is an internal operational visibility surface.
It must not replace production confirmation, inventory count, manager confirmation, Event, or Audit.

## 9.3 Customer-Visible DID

Customer-visible DID may show non-sensitive freshness or house-made messages only.
It must not expose inventory shortage, production delay, or internal gap.

Example customer message:

```text
?쒖쑄?ъ? 留ㅼ옣?먯꽌 吏곸젒 留뚮뱺 ?뚯뒪? ?좎꽑???щ즺瑜??ъ슜?⑸땲????
```

Customer-visible messaging is brand communication only.
It is not proof of inventory accuracy, production completion, or supplier availability.

# 10 pgvector / Future AI Use

RDBMS remains canonical.
pgvector may support similar situation search.

Examples:

- similar Friday dinner shortage patterns.
- weather + delivery demand + sauce usage pattern.
- production quantity recommendation based on similar past days.
- gap explanation candidates based on similar inventory corrections.

pgvector recommendation is advisory only.
Manager approval remains required.
NoSQL/vector/log stores may be considered later according to `80170_Agent_Data_Store_And_AI_Evolution_Principles.md`.

This document does not implement AI, pgvector, embeddings, NoSQL, or final recommendation logic.

# 11 Cross-Domain Propagation

Future target domains:

- SCM / Inventory.
- Store Runtime Operations.
- KDS Runtime.
- DID/CMS Runtime.
- Agent Runtime.
- Audit / Recovery.
- POS / Sales Forecast.
- Workforce / station responsibility.

Later design for each future domain must clarify:

- what is observed.
- what is counted.
- what is produced.
- what is deducted.
- what is adjusted.
- what requires approval.
- what is shown on KDS/DID.
- what is audited.

This document does not create detailed SCM, Inventory, KDS, DID/CMS, POS, Workforce, or Audit/Recovery documents.
It records future propagation candidates so later domain-specific design can stay aligned.

# 12 Non-Implementation Boundary

This document does not define:

- final DB schema.
- final inventory calculation formula.
- final reorder algorithm.
- final pgvector embedding model.
- final POS integration.
- final KDS UI.
- final DID UI.
- final supplier ordering automation.

This document is development-design only.
It does not create implementation code, SQL, migrations, Flutter implementation, inventory logic, AI implementation, pgvector implementation, supplier ordering automation, or final operational approval rules.
