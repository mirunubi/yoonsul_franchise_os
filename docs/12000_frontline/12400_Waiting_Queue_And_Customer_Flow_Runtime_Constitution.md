[ 3rd_01400_Waiting_Queue_And_Customer_Flow_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Readme.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01200_POS_Transactional_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01100_KDS_Operational_Recovery_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01350_CMS_Operational_Projection_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01050_Operational_Agent_Runtime_Constitution.md %

<< 3rd frontline waiting / queue / customer flow constitution >>
<< customer flow runtime worldview only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines Waiting / Queue / Customer Flow as a frontline runtime lane.
It governs customer arrival, queue state, waiting visibility, table-readiness signaling, and customer flow projection without owning POS, KDS, CMS, payment, or recovery authority.

# 1 What Waiting Runtime Is

< Waiting Runtime >

Waiting Runtime is the customer flow lane that manages the visible state of waiting, queueing, arrival, and readiness signaling at the frontline boundary.

It exists to:

- show customer waiting and queue state honestly.
- project table readiness or pickup readiness as a visible runtime condition.
- keep customer flow understandable while the store continues operating.

Waiting is a customer flow runtime, not the owner of payment truth or operational truth.

# 2 Core Relationships

< Runtime Relations >

| system | waiting relationship |
| ------ | -------------------- |
| POS | may confirm transactional or order authority |
| KDS | may expose kitchen readiness signals |
| CMS | may project waiting, queue, and event messages |
| Operational Agent | may observe and recommend, but does not mutate final state |
| Store Operations | may handle human override and operational intervention |
| DID | may display waiting and customer flow visibility |

Rules:

- waiting does not own POS order truth.
- waiting does not own KDS readiness truth.
- waiting does not own CMS projection authority.
- waiting does not own recovery authority.
- waiting may present the flow, but it does not become the source of truth for every upstream lane.

# 3 Customer Flow Philosophy

< Customer Flow >

Waiting exists to make customer arrival and queue progression legible.
It should help the customer understand where they are in the flow without pretending certainty that is not there.

Principles:

- waiting visibility must not override operational readiness.
- queue state must not override POS order truth.
- table-ready signal does not mean actual service completion.
- customer-called does not mean customer-arrived.
- waiting estimate does not mean guaranteed service time.

# 4 Queue State And Arrival Concepts

< Queue Concepts >

Waiting / Queue / Customer Flow should distinguish between:

- customer called.
- customer arrived.
- customer waiting.
- table or service readiness signaled.
- queue still unresolved.
- flow recovered or resumed.

The lane should remain readable enough for humans to act on it and for the customer to understand what is happening.

# 5 No-Show / Absent / Delayed Customer Handling

< Customer Conditions >

The lane may describe no-show, absent, or delayed customer conditions as runtime state philosophy.
That means the lane can show that a customer did not arrive, arrived late, or is still pending in the visible flow.

Rules:

- such conditions are visible runtime states, not punishment states.
- the lane should support honest flow handling rather than hidden assumptions.
- customer flow should remain recoverable even when the customer does not appear on time.

# 6 Emergency / Minimal Mode

< Emergency Mode >

If network, server, or runtime instability occurs, Waiting must degrade to text-first and data-first minimal customer guidance.

Emergency mode principles:

- stale waiting estimates must be visibly marked.
- uncertain queue state must not appear authoritative.
- low-bandwidth guidance is better than rich but misleading projection.
- customer-facing waiting state should remain useful even when the runtime is degraded.

# 7 Human Final Authority

< Human Authority >

Staff and manager may override customer flow decisions when needed.

Principles:

- human final authority remains explicit.
- overrides should not be hidden from later governance layers.
- dismiss does not mean resolved.
- evidence does not mean approval.
- recommendation does not mean execution.

Store Operations is the natural lane for override and escalation handling in this area.

# 8 Relationship To Neighbor Lanes

< Neighbor Relations >

Waiting / Queue / Customer Flow relates to other lanes as follows:

- POS may confirm transactional and order authority.
- KDS may expose kitchen readiness signals.
- CMS may project waiting and event messages.
- Operational Agent may observe and recommend, but does not mutate final state.
- Store Operations may handle human override and operational interventions.

This lane belongs to Frontline Runtime, but it coordinates with the broader operational mesh.

# 9 Boundary Split: Surface, Authority, Recovery

< Boundary Split >

| boundary | meaning |
| -------- | ------- |
| customer flow surface | visible waiting, queue, and arrival projection |
| transaction authority | POS-owned transactional truth |
| operational authority | store and governance interventions |
| recovery coordination | broader mesh handling instability and restoration |

Waiting belongs to the customer flow surface boundary only.

# 10 What Does Not Belong Here

< Out Of Scope >

Waiting / Queue / Customer Flow does not own:

- payment authority.
- inventory truth.
- payroll or workforce truth.
- final recovery resolution.
- POS transaction authority.
- KDS recovery authority.
- CMS projection authority.
- deep constitutional governance language that belongs in `3rd_00018`.
- implementation details, SQL, Flutter, RPC, or contracts.

# 11 Future Surfaces

< Future Surfaces >

Possible future surfaces for this lane include:

- kiosk waiting.
- mobile waiting.
- DID waiting board.
- table orchestration.
- customer notification.
- event queue.
- pickup queue.

These are future surface candidates, not implementation commitments.

# 12 No Implementation Details

< Non-Goals >

This document does not define:

- database tables or schemas.
- SQL, triggers, migrations, or RPC contracts.
- Flutter pages or route flows.
- device SDK behavior.
- detailed event catalogues.
- state machine code.

The job of this constitution is to define the waiting boundary, not the implementation.
