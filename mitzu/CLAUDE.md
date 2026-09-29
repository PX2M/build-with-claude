# CLAUDE.md - Mitzu

> The brain. Every agent in this folder reads this file before it writes a word.
> Mitzu (mitzu.io) is a real company used as the demo product because everything about it is
> public. Only claims that appear on mitzu.io or docs.mitzu.io go in here. No invented customers,
> no invented numbers. Reconciled against the public pages on 2026-09-29; sources at the bottom.

## Built from
This file is assembled, not invented. Each layer is written first, in its own file, then
summed up here. Change the source file, then update the line here.

1. `context/icp.md`: who buys, who uses, the four objections, the anti-ICP.
2. `context/jtbd.md`: the three jobs they hire Mitzu for, each tied to a public quote.
3. `context/messaging.md`: the one-liner, the wedge, three pillars with proof, words to use and avoid.
4. `context/competitors.md` and `context/voice.md`: who to watch, how we sound.

Agents read this file first, then open the context file their brief names.

## Product
- What it is, in one line: Agentic product analytics that runs on your data warehouse. You ask funnel, retention and cohort questions in plain language and get answers built on reviewable SQL, with your events left where they are.
- Runs on: Databricks, Snowflake, BigQuery, Redshift, ClickHouse, AWS Athena, PostgreSQL, Trino, Firebolt, Microsoft Fabric.
- Primary use case: Funnels, segmentation, retention, journeys and cohorts, computed on the warehouse tables. Asked through an in-app agent, a Slack agent, or an MCP server.
- What it does NOT do: It does not ingest, store or move your event data. It does not do session replay, in-app guides, experiments or feature flags. It is narrower than a full BI suite. It needs your events to already be in a warehouse.

## ICP (the buyer). Full version: context/icp.md
- Product people (PMs, product leads) who need answers about how the product is used, plus the data lead who owns the warehouse.
- The user is the product person. The buyer and the gate is the data lead: it is their warehouse.
- Company profile: product and business data already in a warehouse, often collected through Segment, Snowplow or RudderStack.
- The jobs (context/jtbd.md): answer my own product question without the queue; stop the data team being a bottleneck; keep one copy of the data and stop paying for the second.

## Anti-ICP (who we are NOT for)
- No warehouse, and no plan to get one. Mitzu says it "requires event data already in the warehouse". Disqualify and move on.
- They want session replay, in-app guides, experiments or feature flags in the same tool. Mitzu calls these out of scope; Amplitude and Mixpanel ship them. Say so.
- They want open-ended statistical exploration. Mitzu's own words: that belongs in a notebook.

## Positioning
- Category: Warehouse-native, agentic product analytics.
- Unlike: Amplitude and Mixpanel, which analyse the copy of your events they ingested into their own store and price on event volume. Unlike text-to-SQL and BI agents, which Mitzu says need weeks of hand-written YAML before they answer anything.
- The wedge: Your events already live in your warehouse. Why pay per event to copy them somewhere else, and then ask an AI that can only see the copy?

## Competitors (real, public, safe to crawl on camera)
- **Amplitude**. Where we win: no data egress, no per-event bill (Mitzu prices per editor seat, unlimited events), native joins to billing, CRM and support data. Where we lose: breadth (session replay, guides, surveys, experimentation, all on every Amplitude plan), a mature methodology Mitzu itself credits, brand, and a free plan of 2M events a month.
- **Mixpanel**. Where we win: no data egress, no per-event bill; Mixpanel's own warehouse connectors copy data in and bill the synced rows. Where we lose: always-on monitoring and root-cause agents, experimentation, a mature ecosystem, a free plan with unlimited seats, and a public SOC 2 Type II statement.

> On camera: point the Compete agent at their public pricing and changelog pages only.

## Messaging and voice. Full versions: context/messaging.md, context/voice.md
- Say it to a stranger: Mitzu answers your product questions in plain English, straight from the data your company already keeps.
- Three pillars: your data stays put; no per-event bill; product people answer their own questions.
- How we sound: plain and direct. The buyer's words before ours. Name the failure, then the mechanism that removes it.
- What we never say: "single source of truth", "AI-powered". Any sentence a competitor could also say.

## Proof (only what mitzu.io states publicly)
- Pricing: Analyst US$149/month, Team US$749/month, Enterprise custom. Unlimited events on every plan. 14-day free trial, no card. (mitzu.io/pricing)
- "We don't ingest, store, or move your data. It stays in your warehouse." Read-only query execution. Warehouse role-based access stays enforced. Only query context goes to the AI, never raw event data. Full self-hosting in your own VPC. (mitzu.io/privacy-security)
- Setup: connect the warehouse in 2 minutes, semantic layer in 5. Mitzu's claim, not a measured number. (mitzu.io)
- Named customers on the homepage: BrokerChooser, Prezi, Khatabook, Suunto, Colossyan, Shapr3D, Transfr, Munch, NoRedInk, 52 Entertainment and others.
- Customer numbers, always attributed, never restated as Mitzu's own: Colossyan, "the onboarding funnel improved by 30%, and ad hoc reporting is 50% faster." Khatabook, "at half the cost of standard product analytics tools."

## Claims that are off limits
- Any number not on mitzu.io, and any customer number without the customer's name next to it.
- Any security or compliance claim beyond the exact wording on mitzu.io/privacy-security. No SOC 2, ISO, HIPAA or GDPR certification claim: none is stated publicly.
- Anything about funding, headcount or company age. None of it is public.
- Any roadmap item stated as available today (Mitzu says scheduled background agents are not yet shipped at full breadth).
- Naming a competitor in customer-facing copy. Battle cards are internal.

## Sources (fetched 2026-09-29)
- https://www.mitzu.io/
- https://www.mitzu.io/pricing
- https://www.mitzu.io/privacy-security/
- https://www.mitzu.io/post/amplitude-agentic-vs-mitzu/
- https://www.mitzu.io/post/mixpanel-agentic-analytics-vs-mitzu/
- https://www.mitzu.io/post/posthog-agentic-vs-mitzu/
- https://docs.mitzu.io/setup-data-warehouse
