[ 3rd_01050_Operational_Agent_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Readme.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Readme.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01100_KDS_Operational_Recovery_Runtime_Constitution.md %

<< 3rd frontline operational agent constitution >>
<< cross-runtime operational intelligence and recovery mediation only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines the Operational Agent Runtime as a cross-runtime operational intelligence and recovery mediation layer.
It exists to observe, correlate, recommend, escalate, and assist recovery across runtimes without replacing human authority or owning runtime truth.

# 1 What Operational Agent Runtime Is

< Operational Agent Runtime >

Operational Agent Runtime is the mediation layer that watches across operational surfaces and helps humans keep the runtime honest during normal, degraded, or recovery conditions.

It exists to:

- observe runtime conditions across lanes.
- correlate signals that matter operationally.
- recommend next steps or escalations.
- assist recovery by surfacing visibility and context.

It is not an autonomous operator.
It is not a substitute for human authority.

# 2 Core Relationships

< Runtime Relations >

| system | agent relationship |
| ------ | ------------------- |
| POS | observes and correlates order-intent state, anomalies, and recovery context |
| Kiosk | observes customer entry and projection-side issues without owning them |
| KDS | observes kitchen coordination conditions and recovery signals without owning the queue |
| DID | observes customer-facing projection and uncertainty states without owning truth |
| CMS | observes content / rollout side effects and operational surface changes without owning CMS authority |
| Store Operations | receives escalations, coordination hints, and recovery context |
| HQ Operational Brain | receives visibility, support context, and escalation summaries |

Rules:

- Agent does not own POS.
- Agent does not own KDS.
- Agent does not own HQ.
- Agent may observe and help coordinate, but it does not replace the runtime owner of any lane.

# 3 Cross-Runtime Operational Mediation Philosophy

< Mediation >

Agent is a mediation and intelligence layer.
It sits across runtimes so humans can understand what is happening without forcing every lane to collapse into one authority plane.

Principles:

- visibility is not ownership.
- correlation is not mutation authority.
- recommendation is not execution.
- escalation is not override.
- recovery assistance is not final judgment.

The agent exists to make the runtime more legible, not more authoritarian.

# 4 Recovery Assistance Concepts

< Recovery >

Agent may help with recovery by:

- surfacing uncertainty.
- grouping related anomalies.
- preserving context for human review.
- suggesting likely recovery lanes.
- helping humans understand what broke, what is still broken, and what has already been resolved.

Recovery assistance must remain human-supervised.
The agent may recommend recovery actions, but it does not close recovery by itself.

# 5 Operational Anomaly Observation

< Anomaly Observation >

Agent may observe:

- delayed state.
- conflicting projections.
- missing confirmations.
- repeat failures.
- recovery lag.
- cross-lane mismatch.

Operational anomaly observation should improve human understanding, not hide the anomaly.

# 6 Escalation And Routing Assistance

< Escalation >

Agent may assist with escalation and routing by:

- identifying which lane likely needs attention.
- summarizing why the anomaly matters.
- grouping evidence and context.
- recommending an escalation path.

It does not decide the final escalation authority.
It does not auto-route in a way that overrides human judgment.

# 7 Human-Final-Authority Principle

< Human Authority >

Human final authority remains explicit.

Principles:

- the agent may recommend, but the human decides.
- the agent may correlate, but the human approves.
- the agent may escalate, but the human or designated authority executes the decision.
- the agent may assist recovery, but it does not own closure.

# 8 Difference Between Recommendation, Escalation, Override, Execution

< Action Types >

| action | meaning | agent role |
| ------ | ------- | ---------- |
| recommendation | suggested next step | allowed |
| escalation | routed attention to higher or adjacent authority | allowed as assistance |
| override | explicit human interruption or replacement of a path | not owned; may be surfaced |
| execution | actual runtime mutation or authoritative action | forbidden as agent authority |

Rules:

- recommendation != execution.
- escalation != ownership transfer.
- override belongs to humans or designated authorities.
- execution belongs to the lane owner or human authority, not the agent.

# 9 Runtime Visibility Vs Runtime Ownership

< Visibility >

Agent can improve visibility across runtimes, but it must not convert visibility into ownership.

Principles:

- observing a runtime does not mean owning it.
- summarizing a runtime does not mean mutating it.
- correlating runtimes does not mean becoming the authority plane.

# 10 Agent Boundaries And Forbidden Authority Patterns

< Boundaries >

Forbidden authority patterns:

- autonomous operator behavior.
- silent mutation of runtime truth.
- implicit approval through recommendation.
- ownership drift into POS, KDS, CMS, Store Ops, or HQ.
- hiding uncertainty behind a confident agent display.

Dismiss does not mean resolved.
Evidence does not mean approval.
Recommendation does not mean execution.

# 11 What Does Not Belong Here

< Out Of Scope >

Operational Agent Runtime does not own:

- POS runtime truth.
- kiosk authority.
- KDS queue ownership.
- DID projection authority.
- CMS content authority.
- store-level governance.
- HQ Operational Brain authority.
- implementation details, SQL, Flutter, RPC, or contracts.

# 12 Future Subsystem Candidates

< Future Candidates >

Possible future subsystem directions from this lane include:

- anomaly correlation dashboards.
- cross-runtime recovery summaries.
- escalation recommendation lanes.
- human review assist surfaces.
- operational visibility synthesis.

These are future subsystem candidates, not implementation commitments.

# 13 No Implementation Details

< Non-Goals >

This document does not define:

- database tables or schemas.
- SQL, triggers, migrations, or RPC contracts.
- Flutter pages or route flows.
- device SDK behavior.
- detailed event catalogues.
- state machine code.

The job of this constitution is to define the agent boundary, not the implementation.
