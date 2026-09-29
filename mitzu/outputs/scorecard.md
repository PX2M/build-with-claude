# Scorecard: the Compete run, 2026-09-29

Scored against `evals/expected-output.md`, which was written before the run.

## Pass / fail checklist
- [x] Covers the four objections from `context/icp.md`, in the buyer's words.
- [x] Every objection has why it lands, what to say back, and proof with a source URL.
- [x] A "Where we lose" section with walk-away lines (five cases).
- [x] No number that is not on a source page. Customer numbers stay attributed.
- [x] No certification claimed. The card says out loud that none is public.
- [ ] Skimmable in ninety seconds. Close, not there: objection 4 carries five proof lines. A rep reads the "Say back" lines only.

## Scores (1 to 5)

| Dimension | Score | Why |
| --- | --- | --- |
| Ownability: could only we say this? | 4 | "Your events never leave your warehouse, and you do not pay per event" is not sayable by either incumbent: Amplitude closed warehouse-native to new customers, and Mixpanel's connectors copy and bill. Loses a point because other warehouse-native tools could say the same sentence. |
| Provability: does every line carry a source? | 4 | Every claim has a URL fetched on the run date. Loses a point because most of our proof is Mitzu describing itself (setup in "2 minutes", "no data egress"). No independent source, and the security answer rests on one page. |
| Recognition: would the buyer recognise the objection? | 4 | The four objections are the ones a warehouse-native challenger hears: vendor risk, migration, SQL, security. Loses a point because they were written for this demo, not pulled from call recordings. |
| Buyer urgency: does the response give them a reason to move now? | 2 | Nothing on the card forces a move this quarter. No dated price rise was found on either pricing page. The two dated signals (Amplitude self-serve imports, Mixpanel free experiments) both make staying with an incumbent easier, not harder. |

**Average: 3.5.**

## What to fix, in the brief, not the prompt
Urgency is under 3, so this is a brief fix. Add one line to `compete-agent.md`:

`Flag: anything with a date that raises the cost of staying (a price change, a plan retired, a limit lowered). If none is found, say so.`

Then run it again. The honest reading of this run: strong wedge, weak trigger. The card tells a rep how to win the argument; it does not yet tell them why the buyer should have it this quarter.
