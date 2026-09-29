# Signals: Amplitude and Mixpanel

Run: 2026-09-29, by hand, following `compete-agent.md`. Every page below was fetched on that date.
The wedge filter: does it touch **cost at scale**, **data movement**, or **where the AI reads**? If not, it is dropped.

One honest limit first: a pricing page has no dates on it. A single fetch shows what the page
says today, not what changed. Nothing below claims a price moved unless a dated page says so.

---

## Kept (ranked)

### 1. Amplitude makes moving data IN self-serve. Data movement.
- **What:** Release dated Sep 08, 2026, "Self Service Data Migrations": "Users of all tiers now have the ability to migrate event data among projects and organizations they control, as well as to pull in data from Mixpanel and Posthog."
- **Why it matters:** The incumbent is lowering the cost of switching INTO a copy. "Migration is painful" is no longer an objection only we face; Amplitude is actively removing it for Mixpanel users.
- **Move:** Do not argue that migration is hard. Ask where the data ends up after the migration: in Amplitude's store, or still in your warehouse.
- **Source:** https://amplitude.com/releases/self-service-data-migrations

### 2. Warehouse-native Amplitude is closed to new customers. Where the AI reads.
- **What:** Amplitude's docs: "Warehouse-native Amplitude is a legacy feature and is no longer available to new customers."
- **Why it matters:** The only incumbent product that ran on the customer's warehouse is no longer sold. For a new buyer who wants analytics on their own warehouse, Amplitude's answer today is its own store. The page does not say when this changed; treat the date as unknown.
- **Move:** When a buyer says "Amplitude does warehouse-native too", point them at this page.
- **Source:** https://amplitude.com/docs/data/warehouse-native/overview

### 3. Mixpanel's warehouse connectors copy the data in, and the copy is billed. Data movement + cost at scale.
- **What:** "Sync data from your data warehouse into Mixpanel." Supported: BigQuery, Snowflake, Databricks, Redshift, Postgres. Synced event inserts are billed on all sync types; updates and deletes are billed in Mirror mode. The connectors are "a free add-on" on paid event-based plans. Homepage language: "so your data lives where you need it."
- **Why it matters:** Mixpanel's warehouse story is a sync, not a query in place. Standing fact, not a new change, but it is the most direct proof of the wedge on a competitor's own page.
- **Move:** "Their warehouse connector is a pipe into their store, and every row that goes through it is on the bill."
- **Sources:** https://docs.mixpanel.com/docs/tracking-methods/warehouse-connectors , https://mixpanel.com/

### 4. Both price on events. Cost at scale. (Standing, no dated change found.)
- **Amplitude:** Free "2M Events/month forever". Plus "Starts at $0", "First 2M Events/month free". Growth and Enterprise "Custom", "Event based pricing". Retention 1 year on Free and Plus.
- **Mixpanel:** priced on monthly events. Free "Up to 1M events / month", unlimited seats. Growth "Up to 20M events / month", "First 1M free". Enterprise "Up to 1T events / month", "Let's chat".
- **Mitzu, for contrast:** Analyst US$149/month, Team US$749/month, Enterprise custom, "Unlimited events" on every plan.
- **Why it matters:** The event bill is the cost-at-scale story. It also cuts the other way: under 1M to 2M events a month, both incumbents are free and Mitzu is not.
- **Sources:** https://amplitude.com/pricing , https://mixpanel.com/pricing , https://www.mitzu.io/pricing

### 5. Mixpanel moves experiments and feature flags onto Free and Growth. Pricing change, widens where we lose.
- **What:** Changelog 2026-08-24, "Experiments and Feature Flags: Now on Free and Growth plans". Free plan: unlimited experiments, 1k monthly experiment users.
- **Why it matters:** Does not touch our wedge directly, but it is a dated pricing move, and it widens a gap Mitzu itself concedes (no experimentation). Kept for the "Where we lose" section, not for a pitch line.
- **Source:** https://docs.mixpanel.com/changelogs

### 6. Positioning: both incumbents widen away from "product analytics". Positioning shift (undated).
- **Amplitude homepage:** "A new era for product teams." "From analytics to feedback to code, Amplitude brings AI into every step of building self-improving products."
- **Mixpanel homepage:** "product intelligence platform for the AI era."
- **Why it matters:** Both are selling a broader platform. Mitzu stays narrow on purpose ("narrower scope than a full BI suite", in its own words). No date on either page, so this is a state, not a change.
- **Sources:** https://amplitude.com/ , https://mixpanel.com/

---

## Dropped (no bearing on cost at scale, data movement, or where the AI reads)

| Date | Company | Item | Why dropped |
| --- | --- | --- | --- |
| 2026-09-24 | Amplitude | Zoning Insights access expansion | Feature access, not wedge |
| 2026-09-23 | Amplitude | User properties on survey responses | Surveys |
| 2026-09-14 | Amplitude | AI-generated descriptions for events and properties | Taxonomy |
| 2026-09-12 | Amplitude | MCP: taxonomy delete and restore | Taxonomy |
| 2026-09-10 | Amplitude | Even distribution for Guides and Surveys | Guides |
| 2026-09-04 | Amplitude | Shadow DOM support for Guides and Surveys | Guides |
| 2026-09-01 | Amplitude | Schedule experiment stop | Experimentation |
| 2026-08-29 | Amplitude | Session Replay for React Native | Replay |
| 2026-09-28 | Mixpanel | Audit log streaming to your own cloud storage | Governance; noted for the security objection, not the wedge |
| 2026-09-09 | Mixpanel | Agent board editing; report version history | UI |
| 2026-08-27 | Mixpanel | First-party domains | Tracking plumbing |
| 2026-08-24 | Mixpanel | Mixpanel plugin for Claude Code | Interesting for this audience, not the wedge |
| 2026-08-07 | Mixpanel | Automated metadata enrichment; mobile autocapture | Taxonomy, capture |

Sources: https://amplitude.com/releases , https://docs.mixpanel.com/changelogs

---

## Checked and rejected: "they run on sampled data"

This was in the wedge before the run. The sources do not support it.
- Mixpanel: query-time sampling is an optional toggle ("To turn off sampling, simply click the lightning bolt toggle again"), sample size 10%, and "Mixpanel will not sample or drop events at ingestion." https://docs.mixpanel.com/docs/reports
- Amplitude's pricing page does not mention sampling at all. https://amplitude.com/pricing
- Mitzu itself uses sampling for filter values during indexing. https://docs.mitzu.io/indexing

Verdict: do not use sampling as an attack. It was removed from the brief and the brain.
