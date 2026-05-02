# The Weft manifesto

> **Weft** is a working name. The product is a headless, agent-native, sovereign-by-design CRM for the next decade of business software.

## Why this exists

Every CRM built between 2000 and 2020 made the same three bets. They bet that the spreadsheet was the right mental model. They bet that humans would be the only meaningful users of the system. And they bet that data could live wherever the vendor's cloud happened to be.

All three bets are now wrong.

The spreadsheet model breaks the moment your customers come through three channels, your partners play five roles, and a single trip has six events across four systems. You end up with denormalised fields, duplicated entities, and reports that no two people in the company can reconcile. The graph model that real businesses operate on never fit.

The human-only assumption ages worse. Agents now read, write, summarise, and act inside operational systems. The CRMs built for humans expose their data through scraping APIs with rate limits designed to prevent automation. The result: the most useful new class of software user is the worst-served customer of the last generation's tools.

The cloud-anywhere assumption is dying under regulation. DPDP in India, GDPR in Europe, sectoral mandates from IRDAI, IFSCA, FCA, MAS, the CFTC. Every jurisdiction now treats data residency as an architectural concern. CRMs that treat it as a sales conversation lose the deal.

Weft is built from a clean sheet on three corrections.

## What we believe

**Relationships are graphs, not records.** A person, a company, a deal, a policy, a trip, an introduction. These are nodes. Their connections (who works where, who introduced whom, who travelled together, who paid for whom) are typed, time-bounded edges. Every CRM that forces these into a flat Account-Contact-Deal hierarchy throws away the structure that makes the data valuable. We model the graph as the graph.

**Time is the missing dimension.** Most CRMs store the current state and overwrite history. They tell you Alice "is" a customer; they cannot tell you that Alice was acquired through Channel A in April, dormant in May, reactivated through Channel B in July, and is now a 7-trip repeat. The sequence is the product in many businesses. Every state in Weft is derived from an append-only event log. The history is the truth; the snapshot is a projection.

**Agents are first-class citizens.** Not an export, not a Zapier integration, not an MCP afterthought bolted on in 2024. Agents enter through the same API surface as humans, with their own identities, their own scoped capabilities, their own rate limits, their own audit trails. The same row-level security that protects data from a malicious user protects it from a hallucinating agent. We design for the agent because the agent is the consumer that will scale fastest and break things hardest.

**Sovereignty is the default, not the upsell.** Every workspace is pinned to a region. Every cross-region read is explicit, audited, and revocable. A firm with operations in India, the EU, and the US can run three workspaces, each holding its data in its jurisdiction, without standing up three separate CRMs. The boring path is the safe path.

**Markdown is the new JSON.** Free-form content is stored as markdown, not as HTML, not as proprietary rich-text JSON. Every entity renders to a markdown card that humans read in the UI and agents read as MCP resources. The same document serves both consumers because both consumers process structured prose well. JSON keeps its job for typed exchange between machines.

**Schema is law.** The database schema, the API contracts, the validation rules, and the agent tool definitions are generated from a single source. Drift between layers is mathematically impossible because they share a generator. Code that touches the database without going through the typed layer fails at compile time, not in production.

**Audit is product, not afterthought.** Every read of PII, every write to a customer record, every action proposed by an agent, every approval granted by a human, lives in an event log designed for regulators and curious engineers in equal measure. When DPDP or IRDAI or your compliance officer asks "who did what to this customer's data and when", the answer is one query.

**Honesty about complexity.** Some problems are genuinely hard (identity resolution across channels, cross-border data residency, agent permission models). We expose the complexity, name it clearly, and give operators the tools to manage it. Hiding hard problems behind a friendly UI is how trust is destroyed.

## What we reject

**The everything-platform fallacy.** Salesforce, HubSpot, and Microsoft sell platforms that do CRM, marketing automation, support ticketing, accounting, and increasingly your taxes. The integration tax is paid by every customer in the form of a UI nobody loves and an architecture nobody trusts. Weft does one thing: it is the relationship-and-event substrate. Marketing tools, support tools, accounting tools, dashboards, and AI agents read from it. We do not try to be them.

**The headless-as-marketing fallacy.** "Headless" has come to mean "the same product with a worse UI". A real headless CRM is one where the API is the product, the schema is published and stable, and any UI (admin, partner portal, mobile app, voice assistant, agent loop) is a peer consumer. We commit to API stability, semantic versioning, and a frozen public schema with deprecation windows measured in years.

**The walled-garden fallacy.** Your data is yours. Export is a button, not a sales call. The schema is documented and portable. If you want to leave, the export contains your full graph, your full event history, your full markdown content, and your full audit log. We compete on quality, not on lock-in.

**The compliance-by-promise fallacy.** Trust statements are theatre. We commit to compliance through architecture: row-level security in every table, purpose-bound access controls on every column, and audit logs that make non-compliance mechanically visible. Trust is what survives an adversarial audit, not what fits on a slide.

**The premature-AI fallacy.** We will not ship features that look like AI but are not useful. We will not autosummarise things that don't need summarising. We will not put a chat box in every corner. Agentic features ship when they meaningfully save time or reveal patterns humans miss; they do not ship to satisfy a board.

## Who we serve

The first ring: operators at small companies running unusual graphs. Insurance MGAs, embedded-finance distributors, multi-channel brokerages, regulated marketplaces. Companies whose entity shape doesn't fit a standard CRM and whose compliance posture doesn't fit a standard SaaS contract. Their pain today is loud; their willingness to adopt new tools is high; their feedback compounds.

The second ring: mid-market firms with multi-region operations. Financial services holding companies with subsidiaries in three to ten jurisdictions. SaaS firms that have outgrown a single Salesforce org but cannot consolidate due to data residency. They need the sovereignty primitives without rebuilding their stack.

The third ring: agents and the developers who build them. The agent that drafts your investor update, the agent that triages partner emails, the agent that summarises a customer's full history before a renewal call. These agents need a CRM whose API was built to be called by an LLM, not scraped by one.

The fourth ring, eventually: large enterprises with regulated workloads who currently run hand-built internal CRMs because no vendor product fits. The same primitives that serve the first ring serve them, at higher scale and tighter constraints.

## The vision

A decade from now, the operational graph of every serious business is in a system that respects three things: the shape of the graph, the sovereignty of its data, and the agency of the systems that read it. That system runs on commodity cloud, exposes its API as the product, and treats the schema as a public commitment. Its UI is one of many surfaces; its substrate is the asset.

Weft is that substrate. We are not the last CRM. We are the first system that treats relationship data as the durable artefact and the consumer surfaces (UI, agents, integrations) as the changing seasons around it. The graph outlives any particular consumer. So should the system that holds it.

## The wager

The wager underneath all of this: the next decade rewards the systems that are honest about their structure. Not the prettiest, not the most feature-complete, not the cheapest. The ones whose schema, audit trail, and access model are correct enough to survive contact with adversarial agents, regulators, and the kind of multi-region growth that breaks badly designed software. We are building for that decade.

If you are building inside a graph that doesn't fit your tools, in a jurisdiction your vendors don't take seriously, with agents your CRM treats as second-class users, this product is for you. Tell us what breaks. We will fix it in the substrate, where it stays fixed.
