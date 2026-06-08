[ 80170_Agent_Data_Store_And_AI_Evolution_Principles.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80160_Agent_Runtime_Required_Capability_Integration.md %

<< docs-only 쨌 Agent data store and AI evolution principles >>
<< RDBMS remains canonical; auxiliary stores are staged future design options >>

# 1 Stage 1 쨌 Operational OS And Canonical Ledger Build

< Stage Goal >

Stage 1 creates canonical operational ledgers.

The primary DB is Supabase PostgreSQL / RDBMS.
NoSQL is not required in this stage.

Canonical structures include:

- Task Ledger.
- Event Ledger.
- Audit Ledger.
- Exception Ledger.
- Agent Recommendation Log.
- Manager Approval Log.
- Recovery Queue.
- Decision Message Repository basic form.

The purpose of this stage is to make store operations recordable, auditable, recoverable, and human-reviewable before any AI learning expansion is considered.

# 2 Stage 2 쨌 Agent Operation And Data Accumulation

< Stage Goal >

Stage 2 helps humans operate without interruption while accumulating AI-learning material.

Stage 2 includes:

- Lightweight Agent Runtime.
- POS, KDS, Kiosk, and delivery app event capture.
- exception detection.
- manager push.
- approval or rejection record.
- recovery record.
- audit accumulation.

RDBMS remains the primary store.

Raw payload may use PostgreSQL JSONB when event detail, external payload shape, or operational context requires flexible storage inside the canonical RDBMS boundary.

# 3 Stage 3 쨌 Dataset Preparation For AI Learning

< Stage Goal >

Stage 3 shapes operational data into AI-learning-ready datasets.

Dataset preparation includes:

- similar situation grouping.
- success and failure labeling.
- manager approval and rejection pattern cleanup.
- recovery success rate cleanup.
- customer reaction linkage.
- Decision Message Repository cleanup.

Supabase PostgreSQL, JSONB, Storage, and pgvector should still be sufficient in this stage.

The system is still preparing learning material.
It is not yet required to introduce NoSQL merely because AI learning is planned.

# 4 Stage 4 쨌 Logical AI Learning

< Stage Goal >

Stage 4 improves manager decision messages.

Logical AI learns from:

- RDBMS canonical ledgers.
- JSONB raw payload.
- Supabase Storage.
- pgvector candidates.

NoSQL is considered from this phase onward, but it is not automatically required.

NoSQL or auxiliary store trigger conditions include:

- Agent raw logs become too large.
- LLM prompt or context grows.
- manager message full text and edit history become large.
- customer claim text grows.
- device logs or sensor logs begin to arrive.
- similar-situation search exceeds pgvector suitability.
- device-specific JSON structures become too diverse.

NoSQL is considered after Stage 4 when Logical AI learning data grows beyond PostgreSQL / pgvector suitability.

# 5 Stage 5 쨌 Physical AI Task Translation Preparation

< Stage Goal >

Stage 5 is not physical AI device integration.

Stage 5 defines rules that translate Logical AI manager-facing decision messages into Physical AI task instructions.

Translation canonical rules remain in RDBMS.

Task instruction concepts include:

- instruction message standard.
- task type.
- task target.
- device ID.
- priority.
- constraints.
- approval condition.
- failure handling condition.
- human intervention condition.
- audit condition.
- device adapter boundary.

Example manager message:

```text
배달포장은 앞으로 10분 이내 주문을 우선 포장하는 것이 좋습니다.
```

Example Physical AI task instruction:

```text
TASK_TYPE: PACKING_PRIORITY_CHANGE
TARGET_ORDER_GROUP: DELIVERY_ORDERS_PICKUP_WITHIN_10MIN
PRIORITY: HIGH
CONSTRAINTS:
- ALLERGY_ORDER_REQUIRES_HUMAN_CHECK
- SOLDOUT_CANDIDATE_INGREDIENT_FORBIDDEN
FAILURE_ACTION:
- REQUEST_HUMAN_INTERVENTION
- CREATE_RECOVERY_EVENT
AUDIT_REQUIRED: TRUE
```

Auxiliary NoSQL may store:

- device-specific translation examples.
- failure cases.
- device raw logs.
- LLM context.
- similar task embeddings.
- manager-edited phrasing.

# 5.5 Stage 5.5 쨌 Physical AI Interface Specification

< Stage Goal >

Stage 5.5 must happen before real Physical AI device integration.

Stage 5.5 confirms the interface specification before connecting actual devices.

This stage includes:

- select target Physical AI device type.
- define executable work.
- confirm device input format.
- define device output events.
- define failure and human-intervention conditions.
- define safety constraints.
- update Translation Adapter.
- run test simulation.
- sandbox validation before real store deployment.

Stage 5.5 is the device-interface confirmation stage between translation design and actual device integration.

# 6 Stage 6 쨌 Physical AI Device Integration

< Stage Goal >

Actual Physical AI equipment may be connected in Stage 6.

Possible targets include:

- packing assembly equipment.
- automatic cooking equipment.
- smart sensors.
- robot equipment.
- automatic labeling equipment.
- kitchen assist equipment.

The Stage 6 flow is:

```text
Logical AI decision message
=> Manager approval
=> Physical AI Task Translation Module
=> Device Adapter
=> Physical AI task execution
=> task started / completed / failed Event return
=> RDBMS Event / Audit storage
=> auxiliary NoSQL raw log storage if needed
=> AI relearning
```

# 7 Core Data Store Principle

< Canonical Truth >

Original discussion principle preserved as received:

```text
RDBMS濡??뺣떟 ?먯옣??留뚮뱾怨?
4?④퀎 ?댄썑 NoSQL濡??숈뒿 ?щ즺瑜??뺤옣?섍퀬,
5?④퀎?먯꽌 ?쇱?而?AI 吏??硫붿떆吏 ?쒖???留뚮뱾怨?
5.5?④퀎?먯꽌 ?λ퉬蹂??명꽣?섏씠?ㅻ? ?뺤젙????
6?④퀎?먯꽌 ?ㅼ젣 ?쇱?而?AI瑜?遺숈씤??
```

Design interpretation:

- RDBMS remains the canonical source of truth.
- NoSQL, vector, log, or time-series stores are auxiliary stores considered after Logical AI learning begins or data volume requires separation.
- NoSQL never replaces the canonical operational ledger.
- Physical AI device integration comes only after manager-facing Logical AI, task translation rules, and device-interface specification are staged.

# 8 RDBMS And NoSQL Responsibility

< Responsibility Split >

| store class | responsibility |
| --- | --- |
| RDBMS | Task, Event, Audit, and Exception canonical ledgers |
| RDBMS | manager approval |
| RDBMS | recovery decision |
| RDBMS | task instruction canonical rule |
| RDBMS | result Event and Audit |
| RDBMS | final decision record |
| NoSQL / auxiliary future store | Agent raw logs |
| NoSQL / auxiliary future store | Physical AI device raw logs |
| NoSQL / auxiliary future store | sensor streams |
| NoSQL / auxiliary future store | LLM prompt / context history |
| NoSQL / auxiliary future store | manager message full text / edit history |
| NoSQL / auxiliary future store | customer claim text |
| NoSQL / auxiliary future store | embeddings |
| NoSQL / auxiliary future store | device-specific JSON variants |
| NoSQL / auxiliary future store | translation learning examples |

NoSQL never replaces the canonical operational ledger.

# 9 Non-Implementation Boundary

< Boundary >

This document does not define:

- actual table schema.
- migrations.
- RPC.
- Flutter screen.
- Agent process.
- final NoSQL product selection.
- final sync protocol.
- final Physical AI device protocol.
- production device integration.

This document is development-design staging only.
It does not create implementation code, SQL, migrations, Flutter implementation, Agent process code, NoSQL implementation, or final physical device protocol.
