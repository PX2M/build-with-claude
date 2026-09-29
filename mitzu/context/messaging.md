# Messaging

> Step 3 of the chain. Built from icp.md (who) and jtbd.md (the job). This is what we say, in
> the order we say it. Every pillar carries proof from CLAUDE.md. If a line has no proof under
> it, it does not ship.

## What Mitzu is, for someone who has never heard of it
Mitzu answers your product questions in plain English, straight from the data your company
already keeps.

## The plain-English version (for a marketer, no jargon)
Product analytics is how a product team sees what users actually do: who signs up, where they
drop off, who comes back. A data warehouse is the one big database where a company already keeps
that record, next to billing, CRM and support data. Tools like Amplitude ask you to send them a
second copy of every click, and the bill grows with every event you send. Mitzu reads the data
where it already lives, so there is one copy, no per-event bill, and your usage data sits next
to your revenue data.

(Customer-facing copy never names a competitor. There, "tools like Amplitude" becomes "most
product analytics tools". See CLAUDE.md, off-limits claims.)

## The wedge
Your events already live in your warehouse. Why pay per event to copy them somewhere else, and
then ask an AI that can only see the copy?

## Three pillars

| Pillar | The line | Proof (from CLAUDE.md) | Job it answers |
| --- | --- | --- | --- |
| 1. Your data stays put | Nothing gets copied. Mitzu reads your warehouse and leaves the data where it is. | "We don't ingest, store, or move your data. It stays in your warehouse." Read-only queries. Only query context goes to the AI, never raw event data. Self-hosting in your own VPC. (mitzu.io/privacy-security) | Job 3 |
| 2. No per-event bill | You pay per editor seat. Send as many events as you want. | Analyst US$149/month, Team US$749/month, unlimited events on every plan. (mitzu.io/pricing). Khatabook: "at half the cost of standard product analytics tools." | Job 3 |
| 3. Product people answer their own questions | Ask in plain language. Get an answer built on SQL your data team can check. | "We went from waiting days for reports to getting instant answers." (CMO, Munch). Colossyan: "ad hoc reporting is 50% faster." Answers on deterministic, reviewable SQL. (mitzu.io) | Jobs 1 and 2 |

## Say this, not that

| Say | Not | Why |
| --- | --- | --- |
| "your warehouse", "where your data already lives" | "warehouse-native" in the first line | A PM who does not know the term stops reading. Earn the category word, then use it. |
| "a second copy", "copy it somewhere else" | "data silo", "egress" | The buyer pictures a copy. Nobody pictures egress. |
| "per event" / "no per-event bill" | "cost-effective", "affordable" | Name the mechanism, not the adjective. |
| "plain language", "without writing SQL" | "democratize data" | Say what the PM does, not what the category calls it. |
| "SQL your data team can check" | "trustworthy AI" | Trust is the proof, not the claim. |

**Never:** "single source of truth" (the whole category says it, Mitzu's own security page
included), "AI-powered", "powerful", "seamless", "unlock", "game-changer", "leverage" as a verb.
Any sentence Amplitude could also say.

## What we do not claim
Session replay, in-app guides, experiments, feature flags. Mitzu does not do them. If the buyer
needs them, say so and point at the anti-ICP in icp.md.
