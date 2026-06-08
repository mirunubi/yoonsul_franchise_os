[ 07020_Hybrid_FnB_Daypart_Operation_Model.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\07000_store_runtime_operations\07000_Store_Operational_Orchestration_Runtime_Constitution.md %
% root\docs\80000_agent\80160_Agent_Runtime_Required_Capability_Integration.md %
% root\docs\80000_agent\80170_Agent_Data_Store_And_AI_Evolution_Principles.md %
% root\docs\80000_agent\80190_Agent_Prepared_Inventory_And_Reorder_Integration.md %

<< docs-only · hybrid F&B daypart operation model >>

# 1 Purpose

This document defines a development-design concept for hybrid F&B space operation.

It reflects the industry shift from single-category stores toward hybrid daypart models that combine coffee/cafe, ade, kimbap/snack, meal, dessert, beverage, prepared production, pickup, and delivery operations.

This is not an implementation document.
This is not a final menu policy.
This is not a real estate investment document.

# 2 Market And Operating Rationale

< Industry Shift >

- Commercial rent pressure makes single-daypart stores inefficient.
- Coffee/cafe demand often peaks in morning and afternoon.
- Ade, dessert, and snack demand can support afternoon non-meal traffic.
- Kimbap/분식/meal demand often peaks during lunch and dinner.
- Hybrid operation can reduce idle time between meal peaks.
- Time-poor customers prefer one space where meal, drink, snack, dessert, and pickup can be solved together.
- The goal is to maximize sales per square meter and operational utilization from morning to evening.

# 3 Yoonsul Hybrid Interpretation

< Yoonsul Store Model >

Apply to Yoonsul:

- 윤슬김밥 / 윤슬마루 can combine 김밥, 웜볼, 누들, 단백 한컵, 음료, 커피, 에이드, 디저트, 포장, 정기픽업.
- The store should not be seen only as a kimbap shop.
- It should operate as a hybrid Korean meal/cafe space.
- The same space may support dine-in, takeout, delivery, pickup, prepared inventory production, and light cafe use.
- Ade can support afternoon refreshment demand and pair with kimbap, warm bowl, snack, dessert, and pickup traffic.

# 4 Daypart Operation Model

< Daypart Windows >

## 4.1 Morning

- coffee / beverage.
- light kimbap.
- commuter pickup.
- prepared breakfast set candidate.

## 4.2 Lunch

- kimbap.
- warm bowl.
- noodle.
- protein cup.
- dine-in / takeout peak.

## 4.3 Afternoon

- coffee.
- ade.
- dessert / snack.
- prepared inventory production.
- sauce / hummus / pickled item production.
- reservation pickup preparation.
- hygiene / CCP routine prompts.

Korean interpretation:

오후 시간대는 커피, 에이드, 디저트, 간식 수요를 받으면서 동시에 소스·후무스·절임류·반제품 생산과 예약포장 준비, 위생·CCP 루틴 점검을 수행하는 hybrid idle-time reduction window로 본다.

## 4.4 Dinner

- meal / takeout / delivery.
- warm bowl / noodle / kimbap.
- light casual dining.
- canned beer or low-intensity evening option if later approved.

# 5 Store Runtime Implications

< Store Runtime >

Hybrid daypart operation affects store runtime design through:

- daypart-specific operating mode.
- station load balancing.
- idle-time reduction.
- afternoon production lane.
- coffee / ade / dessert traffic support.
- menu exposure by time.
- KDS production prompts.
- DID customer-facing messages.
- staff allocation by daypart.
- prepared inventory and reorder connection.
- hygiene routine timing.

Store runtime coordinates these behaviors without becoming the final menu authority, inventory authority, or staffing authority.

# 6 Agent Runtime Implications

< Agent Runtime >

Agent may later:

- observe idle time by daypart.
- recommend afternoon production.
- recommend coffee / ade / dessert exposure windows.
- recommend menu exposure changes.
- recommend staffing adjustments.
- detect mismatch between expected demand and inventory.
- link sales, KDS load, inventory usage, and production schedule.
- feed future AI demand forecasting.

Agent may not:

- automatically change menu exposure without approval.
- automatically reorder inventory.
- automatically change staffing.
- replace manager judgment.

See `80160_Agent_Runtime_Required_Capability_Integration.md`, `80190_Agent_Prepared_Inventory_And_Reorder_Integration.md`, and `80180_Agent_Hygiene_Routine_And_CCP_Prompt_Integration.md` for related Agent integration boundaries.

# 7 KDS / DID / CMS Implications

## 7.1 KDS

KDS may later:

- show production and prep tasks by daypart.
- show afternoon production routine.
- show peak preparation checklist.
- show hygiene routine prompts.
- show beverage / ade prep load if later connected to station operations.

## 7.2 DID

DID customer-visible mode may show hybrid value:

- "식사와 음료를 한 공간에서"
- "윤슬은 매장에서 직접 만든 소스와 신선한 재료를 사용합니다."
- "상큼한 에이드와 함께 즐기는 윤슬의 한 끼"

DID staff-only mode may show production, prep, beverage, ade, and hygiene prompts.

## 7.3 CMS

CMS may later:

- manage time-based message templates.
- manage daypart menu exposure text.
- manage coffee / ade / dessert promotion text.
- manage customer-facing freshness / house-made / pickup messages.

# 8 Inventory And SCM Implications

< Inventory / SCM >

- prepared inventory production must align with afternoon idle window.
- raw inventory and prepared inventory are linked.
- daypart demand affects reorder recommendation.
- coffee / ade / beverage / dessert inventory and meal inventory must be managed together.
- syrup, fruit base, carbonation, cup, lid, straw, ice, and garnish inventory may become part of beverage/ade inventory planning.
- theoretical-vs-actual gap matters more in hybrid operation.
- pgvector / future AI may later compare similar daypart demand patterns.

See `62010_Franchise_Inventory_Master_Model.md` and `80190_Agent_Prepared_Inventory_And_Reorder_Integration.md` for inventory authority and prepared-inventory integration boundaries.

# 9 Future AI Direction

< Future AI >

Hybrid operation creates the data foundation for:

- demand forecasting by daypart.
- coffee / ade / dessert demand pattern learning.
- prepared production recommendation.
- staffing recommendation.
- smart inventory recommendation.
- menu exposure recommendation.
- personalized meal/drink combo recommendation.

This is future direction only.
No AI implementation is defined here.

See `80170_Agent_Data_Store_And_AI_Evolution_Principles.md` for staged AI evolution principles.

# 10 Non-Implementation Boundary

< Boundary >

This document does not define:

- final menu lineup.
- final coffee menu.
- final ade recipe.
- final beverage station design.
- final store layout.
- final KDS UI.
- final DID UI.
- final CMS schema.
- final inventory algorithm.
- final demand forecasting model.
- final staffing algorithm.
- final CRM personalization logic.

This document is development-design staging only.
It does not create implementation code, SQL, migrations, Flutter implementation, menu logic, inventory logic, AI logic, or final database schema.
