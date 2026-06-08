[ 3rd_01210_CMS_Projection_And_Customer_Expectation_Runtime_Constitution.md ]

% root\docs\3rd\3rd_00000_Cross_Runtime_Interaction_And_Boundary_Master_Constitution.md %
% root\docs\3rd\3rd_00018_Governance_Constitution.md %
% root\docs\3rd\frontline\3rd_01000_Frontline_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01100_KDS_Operational_Recovery_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01150_KDS_Bridge_And_Recovery_Interlock_Runtime_Constitution.md %
% root\docs\3rd\frontline\3rd_01160_Agent_Runtime_Federation_And_Intelligence_Boundary_Constitution.md %
% root\docs\3rd\frontline\3rd_01180_Recovery_Runtime_And_Append_Only_Incident_Governance_Constitution.md %

<< 3rd cms projection and customer expectation runtime constitution >>
<< customer-facing visibility and expectation projection worldview only >>
<< no implementation; no SQL; no Flutter; no RPC; no contracts >>

This document defines CMS Projection Runtime as the bounded customer-facing visibility and expectation projection layer that publishes operational visibility, delay projection, readiness estimation, and recovery messaging without becoming operational truth, recovery authority, fulfillment authority, or transactional authority.

The runtime exists to help customers and staff understand what the system believes is happening without turning that belief into truth.

# 1 Runtime Separation

< Separation >

CMS Projection Runtime is separate from:

- KDS Runtime.
- KDS Bridge Runtime.
- Agent Runtime.
- Recovery Runtime.
- POS Runtime.

These runtimes may coordinate, but they must not collapse into one another.

# 2 Core Axioms

< Axioms >

The projection doctrine obeys the following axioms:

| axiom | meaning |
| ----- | ------- |
| projection != truth | what is shown is not the same as what is authoritative |
| visibility != authority | showing state is not the same as owning state |
| recommendation != execution | advice is not automatic action |
| projected ETA != guaranteed ETA | estimate is not a promise |
| customer messaging != operational mutation | messaging does not change runtime truth |
| delay visibility != compensation approval | seeing delay does not approve compensation |
| recovery messaging != recovery completion | messaging does not complete recovery |
| dismiss != resolved | dismissal is not the same as resolution |

# 3 CMS Runtime Responsibilities

< Responsibilities >

CMS Runtime owns:

- customer-facing visibility.
- expectation projection.
- delay messaging.
- readiness estimation visibility.
- bounded recovery messaging.

It exists to keep the customer-facing surface honest, legible, and survivable.

# 4 CMS Runtime Boundaries

< Boundaries >

CMS Runtime does not own:

- operational execution.
- kitchen truth.
- POS transaction truth.
- recovery approval.
- payment authority.
- compensation authority.
- fulfillment authority.

CMS may describe the world, but it does not become the world.

# 5 Projection Quality Doctrine

< Projection Quality >

The projection layer must stay honest about uncertainty.

Principles:

- stale projection must remain visibly degraded.
- uncertain projection must not appear authoritative.
- intelligence-generated projection must remain bounded and discardable.
- late projection == low operational value.

If the projection is old, weak, or uncertain, it must look old, weak, or uncertain.

# 6 Customer Expectation Synchronization

< Expectation >

CMS exists in part to synchronize customer expectations with operational reality.

Principles:

- customer expectation synchronization should be honest.
- delay and readiness projection must not overpromise.
- recovery messaging should help customers understand state without claiming completion.
- store continuity remains prioritized over projection perfection.

CMS should help customers know what to expect, not manufacture false certainty.

# 7 Cross-Runtime Projection Coordination

< Coordination >

CMS Projection Runtime coordinates with:

- KDS visibility.
- fulfillment pacing.
- recovery visibility.
- queue congestion visibility.

Principles:

- projection may be informed by other runtimes.
- projection does not own those runtimes.
- projection should remain a bounded visibility layer.

# 8 Customer-Facing Survivability Doctrine

< Survivability >

CMS projection must survive degradation without taking the store down.

Principles:

- degraded projection != operational collapse.
- offline operation may reduce projection quality without stopping store operation.
- text-first and data-first communication should remain possible.
- projection should degrade honestly rather than fail theatrically.

Projection quality may fall, but store operation must continue.

# 9 Recovery Visibility Continuity

< Recovery Continuity >

CMS may participate in append-only recovery visibility continuity.

Principles:

- recovery visibility may be projected.
- recovery visibility must not be rewritten into recovery completion.
- append-only continuity is preferable to silent mutation.
- stale recovery visibility should remain visible as stale.

Recovery messaging is a visibility function, not a recovery authority.

# 10 Human Final Authority

< Human Authority >

Human final authority remains preserved.

Principles:

- staff and manager judgment remain explicit.
- recovery and compensation decisions remain lane-bounded.
- humans may accept, ignore, or override projections where their lane permits it.

The projection runtime supports human judgment; it does not replace it.

# 11 Runtime Interaction Boundaries

< Interaction >

CMS Projection Runtime may interact with:

- KDS Runtime.
- KDS Bridge Runtime.
- Recovery Runtime.
- Agent Runtime.
- POS Runtime.
- Store Operations Runtime.

But the interaction is one-way in authority:

- data flows upward.
- authority commands downward.

CMS may project signals outward, but it must not absorb the authority of those lanes.

# 12 Future Projection Federation Surfaces

< Future Surfaces >

Possible future surfaces for this lane include:

- multi-store visibility.
- predictive congestion projection.
- fulfillment delay projection.
- customer recovery coordination.
- operational expectation federation.

These are future surface candidates, not implementation commitments.

# 13 What Does Not Belong Here

< Out Of Scope >

CMS Projection Runtime does not own:

- KDS truth.
- Agent ownership.
- Recovery approval.
- POS transaction truth.
- payment settlement authority.
- compensation authority.
- fulfillment authority.
- implementation details, SQL, Flutter, RPC, or contracts.

# 14 No Implementation Details

< Non-Goals >

This document does not define:

- tables, schemas, or storage models.
- RPC shapes, transport details, or function names.
- Flutter pages or route logic.
- device SDK behavior.
- code-level projection algorithms.

The job of this constitution is to define projection governance, not the implementation.
