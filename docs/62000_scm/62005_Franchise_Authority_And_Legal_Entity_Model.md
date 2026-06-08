[ 62005_Franchise_Authority_And_Legal_Entity_Model.md ]

% root\docs\00001_Md_Rules.md %
% root\docs\00002_Naming_Rules.md %
% root\docs\00005_Number_Index.md %

<< docs-only 쨌 franchise authority and legal entity model >>

# 1 Purpose

This document defines the development-design boundary for tenant, company, legal_entity, owner_group, and store in the franchise_os.
It is not an implementation schema.
It does not define database tables, RLS, or production authorization code.

The purpose is to prevent franchise authority from collapsing into a single `company` concept.
Tenant, company, legal_entity, owner_group, and store must remain separate so brand policy, internal operating responsibility, legal/accounting responsibility, multi-store operating authority, and store-level events stay understandable.

# 2 Tenant

Tenant means brand / OS runtime space.

Examples:

- ?ㅼ뒳源諛?
- ?ㅼ뒳蹂댁슱
- ?ㅼ뒳?ㅼ씠??
- future external SaaS brand.

Tenant owns or scopes:

- brand runtime.
- menu/SOP/policy namespace.
- store operating model.
- KDS/DID/CMS policy surface.
- inventory policy namespace.
- membership namespace if applicable.
- franchise operating rules.

Tenant does not mean each franchisee legal corporation.

# 3 Company

Company means Yoonsul ecosystem internal operating company.

Examples:

- ?ㅼ뒳 蹂몄궗 踰뺤씤
- ?ㅼ뒳 ?댁쁺 踰뺤씤
- ?ㅼ뒳 SCM / 臾쇰쪟 踰뺤씤
- ?ㅼ뒳 SaaS 踰뺤씤
- ?ㅼ뒳 ?꾨옖李⑥씠利?愿由?踰뺤씤

Company may define or manage:

- HQ policies.
- standard recipe policy.
- SCM policy.
- supplier relationship.
- franchise operation rules.
- SaaS operation responsibility.
- HQ audit and governance.

Important:

Do not place every franchisee corporation under company by default.
Franchisee corporations or sole proprietors belong under legal_entity unless a later design explicitly defines them as an internal operating company.

# 4 Legal Entity

Legal Entity means the legal/accounting/tax/settlement/contract responsibility unit.

Examples:

- ?ㅼ뒳 蹂몄궗 踰뺤씤
- ?ㅼ뒳 ?댁쁺 踰뺤씤
- 源???媛留뱀젏 踰뺤씤
- 諛뺣???媛쒖씤?ъ뾽??
- 吏???댁쁺 踰뺤씤
- supplier legal entity if later needed.

Legal Entity owns or carries:

- contract responsibility.
- tax invoice responsibility.
- settlement responsibility.
- payroll responsibility if applicable.
- order/payment settlement account.
- franchise agreement party.
- supplier or lease party if applicable.

# 5 Owner Group

Owner Group means operational ownership or multi-store management group.

Examples:

- 源????ㅼ젏???댁쁺洹몃９
- 諛뺣????댁쁺洹몃９
- 蹂몄궗 吏곸쁺 ?댁쁺洹몃９
- 吏???댁쁺洹몃９

Owner Group may:

- view assigned stores.
- manage multiple stores under its authority.
- approve store-level reorder if allowed.
- approve inter-store transfer if allowed.
- review inventory loss/gap across assigned stores.
- compare store performance within its group.

Owner Group does not automatically have HQ authority.
Owner Group cannot view unrelated owner groups.

# 6 Store

Store means the actual physical or operating store.

Store owns or generates:

- inventory events.
- production events.
- sales usage.
- disposal events.
- actual count.
- prepared inventory production.
- staff action logs.
- KDS/DID operational prompts.
- hygiene routine evidence.
- local Agent events.

Most operational events occur at store level.

# 7 Recommended Relationship

< Conceptual Authority Shape >

```text
Tenant
  => Company
  |    => HQ / operations / SCM / SaaS / franchise policy
  |
  => Legal Entity
       => Owner Group
            => Store
                 => Inventory / Staff / Sales / Events / Agent Logs
```

Example:

```text
Tenant: ?ㅼ뒳源諛?

Company:
- ?ㅼ뒳 蹂몄궗 踰뺤씤
- ?ㅼ뒳 ?댁쁺 踰뺤씤
- ?ㅼ뒳 SCM 踰뺤씤

Legal Entity:
- 源???二쇱떇?뚯궗
- 諛뺣???媛쒖씤?ъ뾽??

Owner Group:
- 源????ㅼ젏??洹몃９
  - ?щ떦??
  - ?댁닔??
- 諛뺣???洹몃９
  - ?숈꽦???
```

# 8 Authority Principles

< Separation Principles >

- Tenant != Legal Entity.
- Company != Franchisee Corporation by default.
- Legal Entity != Owner Group.
- Owner Group != Store.
- Store Visibility != Cross-store Authority.
- Owner Group Visibility != HQ Authority.
- HQ Policy != Silent Store Mutation.
- Agent != Authority Owner.
- Recommendation != Execution.
- Evidence != Approval.

Korean equivalents:

- Tenant??釉뚮옖??OS 怨듦컙?대떎.
- Company???ㅼ뒳 ?대? ?댁쁺?뚯궗??
- Legal Entity??怨꾩빟쨌?멸툑쨌?뺤궛 梨낆엫 二쇱껜??
- Owner Group? ?ㅼ젏???댁쁺 沅뚰븳 臾띠쓬?대떎.
- Store???ㅼ젣 ?댁쁺 ?⑥쐞??

# 9 Inventory And Agent Boundary

Inventory authority belongs to the SCM/Inventory domain and the human authority model defined by tenant, legal_entity, owner_group, and store assignment.

Agent Runtime may observe inventory events, prompt staff actions, recommend reorder or correction, escalate gaps, and record Event/Audit/Exception concepts.
Agent Runtime does not own inventory authority, legal responsibility, cross-store visibility, or reorder execution.

Franchise visibility must be scoped by the correct authority unit:

- tenant scopes the brand / OS policy namespace.
- company scopes internal Yoonsul operating responsibility.
- legal_entity scopes contract, tax, settlement, and accounting responsibility.
- owner_group scopes assigned multi-store operational authority.
- store scopes local operational evidence.

# 10 Non-Implementation Boundary

This document does not define:

- final DB schema.
- final tenant schema.
- RLS.
- final authorization code.
- final reorder algorithm.
- final inventory count logic.
- final supplier ordering automation.

This document is development-design only.
It does not create tenant tables, legal entity tables, owner group tables, RLS policies, authorization code, SQL, migrations, Flutter implementation, inventory logic, reorder logic, AI, or pgvector implementation.
