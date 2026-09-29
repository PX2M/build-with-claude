# Battle card: Mitzu vs Amplitude and Mixpanel

INTERNAL. For reps. Run 2026-09-29; every source fetched that day. Facts go stale; re-check before quoting a price.

**The wedge, one line:** Your events already live in your warehouse. Why pay per event to copy them somewhere else, and then ask an AI that can only see the copy?

---

## 1. "Why would I bet on a startup over Amplitude?"

**Why it lands:** It is a fair risk. Amplitude is the safe name, and Mitzu's own comparison page credits Amplitude's "mature product analytics methodology". Mitzu publishes no funding, headcount or founding date.

**Say back:** "Fair. Look at what you would actually be betting. We do not hold your data. Your events stay in your warehouse, under your access rules. If you ever leave us, the data does not move, because it never left. With a tool that ingests a copy, the copy is what you leave behind."

**Proof:**
- "We don't ingest, store, or move your data. It stays in your warehouse." https://www.mitzu.io/privacy-security/
- Named customers on the homepage include Prezi, Suunto, Shapr3D, Khatabook, Colossyan. https://www.mitzu.io/
- Be straight about what you would rebuild: the semantic layer metadata is stored on Mitzu's side. https://docs.mitzu.io/indexing

---

## 2. "Moving our data is going to be painful, and IT will have questions."

**Why it lands:** Every analytics switch they have lived through meant a migration. And the competition just made moving easier the other way: Amplitude now lets every tier pull in data from Mixpanel and PostHog (release, Sep 08, 2026).

**Say back:** "First question: are your events already landing in the warehouse, through Segment, Snowplow, RudderStack or your own pipeline? Then nothing moves. We read the tables where they sit. What IT reviews is a read-only connection, not a new pipeline." If the answer is no, go to Where we lose.

**Proof:**
- "No ETL pipelines, no duplicate raw data stores, no third-party replication." https://www.mitzu.io/privacy-security/
- Mitzu's own limit, say it before they find it: "Requires event data already in the warehouse." https://www.mitzu.io/post/amplitude-agentic-vs-mitzu/
- The other side of the move: Amplitude "pull in data from Mixpanel and Posthog", and Mixpanel's connectors "Sync data from your data warehouse into Mixpanel". Both are a copy. https://amplitude.com/releases/self-service-data-migrations , https://docs.mixpanel.com/docs/tracking-methods/warehouse-connectors

---

## 3. "Our PMs and marketers don't write SQL."

**Why it lands:** "Warehouse-native" sounds like a tool for the data team. Amplitude and Mixpanel are known as point-and-click.

**Say back:** "They will not write any. They ask in plain language, in the app or in Slack. The agent does not write the SQL; a deterministic engine does, and it shows the SQL on every answer. Your data team checks it instead of writing it."

**Proof:**
- "Ask funnel, retention, and cohort questions in plain language." "No SQL, no tickets, no waiting." https://www.mitzu.io/
- "Agent does not write SQL." "Same specification produces the same SQL every time." https://www.mitzu.io/post/mixpanel-agentic-analytics-vs-mitzu/
- Customer: "We went from waiting days for reports to getting instant answers." Albert Wettstein, CMO, Munch. https://www.mitzu.io/
- Know the plan before you promise the team: the Analyst plan has no viewers; the Slack agent and unlimited viewers start on Team (US$749/month). https://www.mitzu.io/pricing

---

## 4. "Security won't let a new tool into our warehouse."

**Why it lands:** Warehouse access is the crown jewels, and a new vendor with a service account is a real review. Mixpanel's pricing page states "Native SOC 2 type II compliant". Mitzu's public pages state no certification.

**Say back:** "Good, bring security in early. Here is what they will review: read-only queries that run under the warehouse roles you already have, no raw data replicated, and the AI gets query context, never raw events. On Enterprise, the whole stack can run in your own VPC. Then ask them which is the bigger review: a read-only connection, or every event shipped to a third party's store."

**Proof:**
- "Read-only query execution with no raw data replication." "Role-based data access remains enforced at the warehouse layer." "Only query context is sent to the AI, never raw event data." "Customer data is never used to train or fine-tune LLMs." https://www.mitzu.io/privacy-security/
- Enterprise: "Private VPC, Self-hosted option, Enterprise SSO." https://www.mitzu.io/pricing
- What security will find, so you raise it first: indexing stores metadata on Mitzu's side, including up to 500 filter values per property (https://docs.mitzu.io/indexing). The general setup page suggests a "BigQuery Admin role" ("You can change this later"), while the BigQuery page lists read roles (https://docs.mitzu.io/setup-data-warehouse , https://docs.mitzu.io/bigquery). Send the BigQuery page, not the setup page.
- Never claim SOC 2. It is not on any public page.

---

## Where we lose

Say these out loud. A card with no losing case gets ignored.

1. **No warehouse, or the events are not in it.** Mitzu "requires event data already in the warehouse" (https://www.mitzu.io/post/amplitude-agentic-vs-mitzu/). Walk-away: *"Get your events into a warehouse first. Call us when they land."*
2. **They want replay, guides, surveys, experiments and flags in one tool.** Amplitude includes session replay, experimentation, guides and surveys on every plan (https://amplitude.com/pricing). Mixpanel put experiments and feature flags on Free and Growth on 2026-08-24 (https://docs.mixpanel.com/changelogs). Mitzu calls session replay, feature flags and experiments out of scope (https://www.mitzu.io/post/posthog-agentic-vs-mitzu/) and has "no native session replay or in-app guides surface" (https://www.mitzu.io/post/amplitude-agentic-vs-mitzu/). Walk-away: *"If one tool for analytics and experimentation is the requirement, Amplitude or Mixpanel is the right buy."*
3. **Procurement requires a SOC 2 report.** Mixpanel states SOC 2 Type II on its pricing page (https://mixpanel.com/pricing); Mitzu states none (https://www.mitzu.io/privacy-security/). Walk-away: *"Check with our team before the review. If it is a hard gate and we cannot meet it, say so now, not in week six."*
4. **Small volume.** Amplitude is free to 2M events a month; Mixpanel free to 1M with unlimited seats (https://amplitude.com/pricing , https://mixpanel.com/pricing). Mitzu starts at US$149/month (https://www.mitzu.io/pricing). Below those volumes there is no event bill to save. Walk-away: *"If you are under a million events a month, the free tier is the right answer today."*
5. **They want always-on monitoring agents now.** Mitzu's own page credits Mixpanel's always-on KPI monitoring and root-cause agents, and says scheduled background agents are "on roadmap, not yet shipped at full breadth" (https://www.mitzu.io/post/mixpanel-agentic-analytics-vs-mitzu/). Do not sell the roadmap.
