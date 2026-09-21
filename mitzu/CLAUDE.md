# CLAUDE.md - Mitzu

> The brain. Every agent in this folder reads this file before it writes a word.
> Mitzu (mitzu.io) is a real company used as the demo product because everything about it is
> public. Only claims that appear on mitzu.io go in here. No invented customers, no invented numbers.
>
> TODO before 1 Oct (SCOPE build-list row 2): reconcile every line below against mitzu.io as of the
> run date and delete anything the site does not say.

## Product
- What it is, in one line: Product analytics that runs directly on your data warehouse, so the events you already store are the events you analyse.
- Who it is for: Product and growth teams at companies that already run Snowflake, BigQuery or Databricks and have a data team.
- Primary use case: Funnels, retention and feature adoption computed on the warehouse tables, with no copy of the events into a second store.
- What it does NOT do: It does not store your events. It is not a BI tool and not a CDP. If you do not have a warehouse, there is nothing for it to run on.

## ICP (the buyer)
- Title / role: VP Product, Head of Growth, Director of Product Analytics. The Head of Data is often the economic buyer.
- Company profile: B2B SaaS, already on a warehouse, with a data team of three or more.
- Their pain, in their words: "We already have the data, we are paying to copy it." "The product tool and the warehouse give different numbers." "Every metric definition lives in two places and drifts."
- Their goal: One definition of every metric, computed once, trusted by product and finance at the same time.

## Anti-ICP (who we are NOT for)
- No warehouse. The entire wedge evaporates. Disqualify and move on.
- Marketing owns analytics and wants dashboards, not SQL. Amplitude genuinely fits better. Say so.
- Under 20 people, no data team. They should buy the simplest thing and come back later.

## Positioning
- Category: Warehouse-native product analytics.
- Unlike: Amplitude and Mixpanel, which ingest a copy of your events into their own store and price on event volume. Unlike BI tools, which sit on the warehouse but were never built for funnels, retention or cohorts.
- The wedge: Your events already live in your warehouse. Why pay to copy them somewhere else, and get sampled on the way?

## Competitors (real, public, safe to crawl on camera)
- **Amplitude**. Where we win: no second data store, no metric drift, no event-volume bill. Where we lose: breadth, maturity, experimentation, brand. "Nobody gets fired for Amplitude."
- **Mixpanel**. Where we win: warehouse-native, no event-volume pricing. Where we lose: speed to first chart, self-serve motion, price at the low end.

> On camera: point the Compete agent at their public pricing and changelog pages only.

## Voice
- How we sound: plain and direct. Lead with the buyer's pain in the buyer's words. Specifics over adjectives.
- What we never say: "single source of truth" (the whole category says it). "AI-powered." Any sentence a competitor could also say.
- Pattern: name the failure, then the mechanism that removes it. Short sentences.

## Proof
- Only what mitzu.io states publicly. Nothing else goes in customer-facing copy.

## Claims that are off limits
- Any number not on mitzu.io.
- Any security or compliance claim.
- Any roadmap item stated as available today.
- Naming a competitor in customer-facing copy. Battle cards are internal.
