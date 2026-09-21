# Build With Claude: three agents every PMM should own

The take-home from the PMMCA webinar, 1 October 2026. Everything that was on
screen is in here: the brain, the three briefs, the outputs, and the step by
step to build the first agent yourself, by hand, tonight.

You do not need a GitHub account. Use the green **Code** button above and
**Download ZIP**. Unzip it anywhere.

---

## What you need

- A **paid** Claude plan (Pro or Max). The free plan cannot sign in to Claude Code.
- A terminal. It is already on your machine. Mac: Terminal. Windows: PowerShell.
- Claude Code installed. One line, then sign in:

```bash
npm install -g @anthropic-ai/claude-code
claude
```

If `npm` is not found, install Node from nodejs.org first (the LTS button), then
run the two lines again. That is the whole install.

---

## The agent, from 20,000 feet

Every agent you will ever build is these five parts. The only thing that changes
between agents is what you write in the brief.

| # | Part | In this repo | What it is |
| --- | --- | --- | --- |
| 01 | **Brain** | `mitzu/CLAUDE.md` | Product, buyer, voice, what is off limits. Written once, read on every run. |
| 02 | **Brief** | `mitzu/compete-agent.md` | The job, in English. Watch, flag, output, rules. |
| 03 | **Harness** | `claude`, in a terminal | Where it runs. Your laptop tonight. A box or Slack later, same files. |
| 04 | **Evals** | `mitzu/evals/` | What good looks like, written *before* the run. Then the scorecard. |
| 05 | **Memory** | `mitzu/outputs/` | What it wrote and what was wrong. The next run reads it. |

**v1 is all five, run by hand from a terminal.** Nothing scheduled, nothing in
Slack, nothing that sends. That is what you build tonight. The rest is the
ladder, and it comes later, one rung at a time.

---

## Step by step: your first agent, v1

Five steps. Same five as the webinar. Do them on Mitzu first, exactly as
written, so you know what a working run feels like. Then point the same files
at your own product.

### Step 1. Name it

Open a terminal in the `mitzu/` folder and start Claude Code.

```bash
cd mitzu
claude
```

The job tonight is Compete: watch two named competitors and write the battle
card a rep opens ninety seconds before a demo. Notice what it is not. "Track our
competitors" is not a job. Two named companies, one reader, one output is.

### Step 2. Feed it

Read the brain before you run anything. It is short on purpose.

```
cat CLAUDE.md
ls context/
```

`CLAUDE.md` is what the agent reads before it writes a word: the product, the
buyer, the anti-buyer, the voice, the claims that are off limits. The
`context/` folder holds the named competitors, the ICP and the voice notes.
This is the step most people skip, and it is the reason their output comes back
generic. Context is the whole difference, and context is a file you write once.

### Step 3. Write it

```
cat compete-agent.md
```

That is the brief. It is a job description, not code. Watch, flag, ignore,
output, and two rules: every claim needs a source, and name where we lose. A
card with no losing case gets ignored by reps.

### Step 4. Run it

Before you run, read `evals/expected-output.md`. It says what a good battle card
looks like, and it was written before the run. Grading on vibes afterwards is
how an agent drifts for three weeks without anyone noticing.

Then, in Claude Code, type this (it is one message):

```
Using my CLAUDE.md and compete-agent.md, go to amplitude.com/pricing and
mixpanel.com/pricing, find what changed recently and what touches our wedge,
and write me the battle card in the format in the brief.
Save it to outputs/battle-card.md.
```

It reads the brain, reads the brief, fetches the two pages, ranks what it
found against the wedge, and writes the file. Open `outputs/battle-card.md`.
The one we got on the night is committed next to it, so you can compare.

### Step 5. Fix it

Score the card against `evals/expected-output.md`. Where is it weak? Now edit
the brief, not the prompt. If it made a claim with no source, add the rule in
plainer words. If it flattered you, add "name where we lose" higher up. Run it
again. Every run makes the next one better, and the fix lives in a file, so it
survives.

Step 5 is the one nobody does. It is the one that compounds.

---

## Then point it at your product

1. Copy `templates/CLAUDE.template.md` to a new folder as `CLAUDE.md` and fill
   it in. Twenty minutes. The anti-ICP section does more work than the rest.
2. Copy `templates/compete-agent.template.md` next to it. Name two competitors.
   Not a category, two companies.
3. Copy `templates/expected-output.template.md` into `evals/`. Write what a good
   card looks like before you run.
4. Run step 4 with your competitors' pricing pages. Then step 5.

The Position and Launch briefs (`mitzu/position-agent.md`,
`mitzu/launch-agent.md`) are the same shape with a different job. Once Compete
works, they take an evening each.

---

## Where most people go wrong

Picture a metro line. One main line that always works, which is the run you do
by hand. Every new piece of automation is a side road: it leaves the line, gets
proven, and only then rejoins. Nothing experiments on the main line, because
people are riding it.

Most people skip the main line. They start at the Ferrari: scheduled, in Slack,
sending, on day one. Then it breaks at 7am before a launch and there is nothing
to come back to.

- **The Ferrari first.** Scheduled, in Slack, sending, before the manual run
  worked once. You build something you cannot debug, then quietly stop using it.
- **No main line.** Nothing you trust runs today, so every change is a change to
  everything. You cannot answer "what happens if I touch this."
- **Grading on vibes.** No expected output written before the run. It drifts for
  three weeks and nobody notices.

One element at a time. The full ladder, v0 to v5, with what each rung adds,
what it costs and how it fails, is in [`docs/LADDER.md`](docs/LADDER.md). Tonight
is v1 to v2. Stop there until it has run by hand ten times.

---

## What is in here

| Path | What it is |
| --- | --- |
| `mitzu/CLAUDE.md` | The brain for the demo product. Built from Mitzu's public pages only. |
| `mitzu/context/` | The named competitors, the ICP and the anti-ICP, the voice. |
| `mitzu/compete-agent.md` | The brief we ran live. |
| `mitzu/position-agent.md`, `mitzu/launch-agent.md` | The other two briefs. Same shape, different job. |
| `mitzu/evals/` | Expected output, written before the run, and the scorecard rubric. |
| `mitzu/outputs/` | What the agents produced. Compare yours against these. |
| `templates/` | Blank brain, blank brief, blank expected output. For your product. |
| `docs/LADDER.md` | v0 to v5. What each version adds, what it costs, and how it fails. |

## Going further

The free skills the course agents run, one install, no course required:

```bash
npx skills add PX2M/pmm-skillset-pmmca
```

The course, *Claude Code for Product Marketers: Build Your First 3 AI Agents*,
takes you from never having opened a terminal to three agents on your own
product, inside PMMCA. Seventeen lessons, one step each.

---

Mitzu (mitzu.io) is a real company used as the demo product because everything
about it is public. Nothing in this repo is affiliated with or endorsed by
Mitzu, Amplitude or Mixpanel. Competitor facts come from their public pricing
and changelog pages on the date of the run and will go stale.
