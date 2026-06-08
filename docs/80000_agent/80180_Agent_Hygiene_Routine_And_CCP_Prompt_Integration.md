[ 80180_Agent_Hygiene_Routine_And_CCP_Prompt_Integration.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %
% root\docs\80000_agent\80160_Agent_Runtime_Required_Capability_Integration.md %

<< docs-only 쨌 Agent hygiene routine and CCP prompt integration >>

# 1 Purpose

This document defines a development-design concept for hygiene routine prompts.
It supports future CCP/HACCP-lite preparation but is not a legal HACCP certification document.
It defines how SOP-driven hygiene prompts can appear on KDS, DID, staff devices, and future speakers.

The purpose is to make scheduled hygiene routines visible, confirmable, auditable, and escalatable before franchise expansion requires stronger operational proof.

# 2 Core Concept Flow

< Hygiene Routine Prompt Flow >

```text
SOP / CCP Routine Rule
        =>
Scheduled Hygiene Prompt
        =>
KDS / DID / Staff App / Future Speaker
        =>
Staff Acknowledgement / Completion / Delay
        =>
Event / Audit / Exception
        =>
Manager / Owner / HQ Visibility
```

The flow separates prompt display from completion.
A visible prompt does not prove that hygiene work was completed.
Completion requires staff acknowledgement or completion action and must be recorded through Event, Audit, or Exception concepts.

# 3 First Use Cases

## 3.1 Color-Coded Scissor Replacement Every 2 Hours

< Use Case >

- Prompt every 2 hours.
- Current color and next color may be shown.
- Staff must acknowledge or complete.
- Delay triggers manager visibility.
- Completion creates Event/Audit.

Design intent:

- The routine can help stores rotate color-coded scissors in a predictable cycle.
- The prompt may include station, due time, current color, next color, and required confirmation.
- Overdue replacement should remain visible until acknowledged, completed, delayed with reason, or escalated.

## 3.2 Handwashing Reminder After Break Return

< Use Case >

- Triggered by break return or shift re-entry.
- Prompt asks whether staff washed hands and changed gloves if required.
- Staff confirmation is recorded.
- Repeated missing confirmation escalates.

Design intent:

- Workforce break-return or shift re-entry signals may trigger a hygiene prompt.
- The prompt records staff confirmation without turning the Agent into a legal compliance certifier.
- Missing or repeated delayed confirmation should become manager-visible.

## 3.3 Open / Peak / Close Hygiene Routine Prompts

< Use Case >

- Opening hygiene checklist.
- Pre-peak tool check.
- Closing cleaning confirmation.

Design intent:

- Opening prompts can confirm baseline hygiene preparation.
- Pre-peak prompts can confirm tool readiness before rush operation.
- Closing prompts can confirm cleaning, reset, disposal, and next-day readiness.

# 4 KDS Role

KDS is staff-facing operational prompt display.

Examples:

- ?쒓???援먯껜 ?쒓컙?낅땲?? ?ㅼ쓬 ?됱긽 媛?꾨줈 援먯껜 ???꾨즺瑜??뚮윭二쇱꽭????
- ?쒗쑕寃?蹂듦? ???먯뵽湲곗? ?κ컩 援먯껜瑜??뺤씤?댁＜?몄슂.??

KDS may show:

- routine name.
- due time.
- current required action.
- responsible station or role.
- confirm / delay / manager call actions.

KDS must not treat dismissed prompt as completed.

KDS remains an operational display and action surface.
It does not become the owner of hygiene policy, legal certification, or final audit authority.

# 5 DID Role

DID has two visibility modes.

## 5.1 Staff-Only DID

Staff-only DID may:

- show hygiene routine prompts.
- show current routine status.
- show overdue state.

Staff-only DID should follow the same completion boundary as KDS:

- display is not completion.
- dismiss is not completion.
- overdue state must remain visible until a permitted action resolves or escalates it.

## 5.2 Customer-Visible DID

Customer-visible DID may show only non-sensitive quality messages.
It must not expose internal failure, delay, staff names, or hygiene non-compliance.

Example customer-visible message:

```text
?쒖쑄?ъ? ?뺢린?곸쑝濡?議곕━?꾧뎄瑜?援먯껜쨌?몄쿃?섍퀬 ?덉뒿?덈떎.??
```

Customer-visible DID messaging is brand and reassurance communication only.
It does not prove legal compliance and must not reveal internal exception details.

# 6 Future Speaker / Voice Prompt Boundary

Future speaker is a prompt channel only.
It does not approve completion.
It does not replace Event/Audit.

Speaker examples:

- ?쒓???援먯껜 ?쒓컙?낅땲?? ?ㅼ쓬 ?됱긽 媛?꾨줈 援먯껜?댁＜?몄슂.??
- ?쒗쑕寃?蹂듦? ???먯뵽湲곕? ?뺤씤?댁＜?몄슂.??

Speaker prompts may improve frontline awareness, but staff completion must still be captured through an authorized interaction surface.

# 7 Agent Responsibilities

Agent may:

- evaluate schedule.
- detect break return or re-entry trigger.
- generate hygiene prompt.
- send prompt to KDS/DID/staff device/future speaker.
- collect acknowledgement/completion.
- mark overdue state.
- escalate to manager/owner/HQ.
- create Event/Audit/Exception records.

Agent may not:

- assume completion from prompt display.
- treat dismiss as resolved.
- certify legal compliance.
- silently close overdue hygiene routines.

Agent Runtime remains an observation, prompt, audit, escalation, and recovery support layer.
Owning runtime domains and human managers retain their authority boundaries.

# 8 State Candidates

< Hygiene Routine State Candidates >

- HYGIENE_PROMPT_SCHEDULED
- HYGIENE_PROMPT_DISPLAYED
- HYGIENE_ACTION_ACKNOWLEDGED
- HYGIENE_ACTION_COMPLETED
- HYGIENE_ACTION_DELAYED
- HYGIENE_ACTION_SKIPPED
- HYGIENE_ACTION_OVERDUE
- MANAGER_CONFIRM_REQUIRED
- HYGIENE_EXCEPTION_RECORDED
- AUDIT_RECORDED

These are design candidates only.
They do not define final database schema, enum implementation, RPC contract, or UI state model.

# 9 SOP Candidates

Future SOP candidates:

- color-coded scissor rotation SOP.
- cutting board / knife replacement SOP.
- handwashing after break SOP.
- glove replacement SOP.
- opening hygiene check SOP.
- pre-peak hygiene check SOP.
- closing cleaning confirmation SOP.
- allergen order handling SOP.
- cross-contamination prevention SOP.
- refrigerator temperature check SOP.
- disposal / waste recording SOP.

SOP candidates should later be reviewed with operations, quality, and legal specialists before being treated as formal policy.

# 10 Cross-Domain Propagation

Future target documents or domains:

- KDS Runtime: hygiene prompt display and completion actions.
- DID/CMS Runtime: staff-only and customer-visible message templates.
- Store Runtime Operations: routine scheduling and station responsibility.
- Workforce: break return and role-based responsibility triggers.
- Inventory: tool/consumable replacement and sanitation relation.
- Audit/Recovery: overdue and exception handling.
- Agent Runtime: prompt generation, escalation, and audit.

This document does not create detailed KDS, DID, CMS, Workforce, Inventory, or Audit/Recovery documents.
It records future propagation candidates so later domain-specific design can stay aligned.

# 11 Non-Implementation Boundary

This document does not define:

- final DB schema.
- final RPC.
- Flutter UI.
- KDS implementation.
- DID implementation.
- speaker integration.
- legal HACCP certification process.
- final CCP checklist approval rule.

This document is development-design only.
It does not create implementation code, SQL, migrations, Flutter implementation, device integration, or legal HACCP certification material.
