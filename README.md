# Build With Claude: three agents every PMM should own

The take-home from the PMMCA webinar, 1 October 2026. Everything that was on
screen is in here: the brain, the three briefs, the outputs, and the step by
step to build the first agent yourself, by hand, tonight.

You do not need a GitHub account. Use the green **Code** button above and
**Download ZIP**. Unzip it anywhere.

---

## What you need

- A **paid** Claude plan (Pro or Max). The free plan does not include Claude Code.
- A terminal. It is already on your machine. Mac: open **Terminal** (Cmd+Space, type Terminal). Windows: open **PowerShell** (Start menu, type PowerShell).
- Claude Code installed. Paste ONE line into the terminal, press Enter, wait for it to finish:

Mac:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://claude.ai/install.ps1 | iex
```

Then **close the terminal and open a new one**, and type `claude --version`. If it prints a
version number, you are installed. The first time you type `claude` it opens your browser to sign
in. That is the whole install. If something fails, the official troubleshooting
page is https://code.claude.com/docs/en/troubleshoot-install

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

## How the pieces fit

The brain is not written in one go. It is built in layers, and each layer comes from the one
above it. Skip a layer and the agent fills the gap with generic.

```
  ICP              who buys, who uses, what they object to      context/icp.md
   |
   v
  Job to be done   what they are trying to get done             context/jtbd.md
   |
   v
  Messaging        what we say, in their words, with proof      context/messaging.md
   |
   v
  CLAUDE.md        the brain: the three above, plus the rules   CLAUDE.md
   |
   v
  Agent brief      one job for the agent                        compete-agent.md
   |
   v
  Outputs          what it wrote, graded against evals/         outputs/
```

The top three are yours to write, once. The brain sums them up and adds what is off limits. The
brief is the only part that changes between agents. Compete, Position and Launch all read the
same brain.

For Mitzu, the chain reads like this:

- **ICP:** product managers and product leads, plus the data lead who owns the warehouse.
- **Job:** "When I have a product question, I want to answer it myself, so I can decide this
  week instead of waiting days in the data team's queue."
- **Messaging:** Mitzu answers your product questions in plain English, straight from the data
  your company already keeps.
- **Brain:** `mitzu/CLAUDE.md`, with a "Built from" list at the top pointing back at all three.
- **Brief:** `mitzu/compete-agent.md`. **Output:** `mitzu/outputs/battle-card.md`.

---

## Step by step: your first agent, v1

Five steps. Same five as the webinar. Do them on Mitzu first, exactly as
written, so you know what a working run feels like. Then point the same files
at your own product.

### Step 1. Name it

Open a terminal **inside the `mitzu` folder** of the unzipped download. The easiest way:

- **Mac:** open Terminal, type `cd ` (with a space after it), drag the `mitzu` folder from Finder
  onto the Terminal window, press Enter.
- **Windows:** open the `mitzu` folder in File Explorer, click the address bar at the top, type
  `powershell`, press Enter. A PowerShell window opens already in the right place.

Type `ls`. You should see `CLAUDE.md`, `compete-agent.md` and a `context` folder. If you do, you
are in the right place.

The job tonight is Compete: watch two named competitors and write the battle
card a rep opens ninety seconds before a demo. Notice what it is not. "Track our
competitors" is not a job. Two named companies, one reader, one output is.

### Step 2. Feed it

Read the brain before you run anything. It is short on purpose. Same commands on Mac and Windows:

```
cat CLAUDE.md
cat context/icp.md
cat context/jtbd.md
cat context/messaging.md
```

(Prefer a normal editor? Open the same files in any text editor. They are plain text.)

`CLAUDE.md` is what the agent reads before it writes a word: the product, the
buyer, the anti-buyer, the voice, the claims that are off limits. The
`context/` folder holds the layers it is built from: the ICP with the four objections the buyer
raises, the jobs to be done, the messaging, the named competitors and the voice notes. Open
`CLAUDE.md` and look at the "Built from" list at the top. That is the chain, in one file.
This is the step most people skip, and it is the reason their output comes back
generic. Context is the whole difference, and context is a file you write once.

### Step 3. Write it

```
cat compete-agent.md
```

That is the brief. It is a job description, not code. Watch, flag, ignore,
output, and the rules: every claim needs a source, and name where we lose. A
card with no losing case gets ignored by reps.

### Step 4. Run it

Before you run, read `evals/expected-output.md`. It says what a good battle card
looks like, and it was written before the run. Grading on vibes afterwards is
how an agent drifts for three weeks without anyone noticing.

Your run will overwrite our battle card, so keep a copy of ours to compare against:

```
cp outputs/battle-card.md outputs/battle-card-ours.md
```

Now start Claude Code, in the same terminal:

```
claude
```

Then type this (it is one message):

```
Using my CLAUDE.md and compete-agent.md, go to amplitude.com/pricing and
mixpanel.com/pricing, find what changed recently and what touches our wedge,
and write me the battle card in the format in the brief.
Save it to outputs/battle-card.md.
```

It will ask permission before it fetches a web page and before it writes a file. Read the
request, then approve it. It reads the brain, reads the brief, fetches the pages, ranks what it
found against the wedge, and writes the file. Open `outputs/battle-card.md` and compare it with
`outputs/battle-card-ours.md`, the one we got on the run before the webinar.

### Step 5. Fix it

Score the card against `evals/expected-output.md`. Where is it weak? Now edit
the brief, not the prompt. If it made a claim with no source, add the rule in
plainer words. If it flattered you, add "name where we lose" higher up. Run it
again. Every run makes the next one better, and the fix lives in a file, so it
survives.

Step 5 is the one nobody does. It is the one that compounds.

---

## Plug it into your own brain

Same files, your product. The agent briefs do not change much. The brain does.

**1. Make the folder.** Next to `mitzu/`, make a folder for your product and copy the templates in:

```
your-product/
  CLAUDE.md                 <- from templates/CLAUDE.template.md
  compete-agent.md          <- from templates/compete-agent.template.md
  context/
    icp.md                  <- from templates/icp.template.md
    jtbd.md                 <- from templates/jtbd.template.md
    messaging.md            <- from templates/messaging.template.md
    competitors.md          <- two named competitors, their pricing and changelog URLs
    voice.md                <- how you sound, what you never say
  evals/
    expected-output.md      <- from templates/expected-output.template.md
  outputs/                  <- empty. The agent writes here.
```

Copy `mitzu/context/competitors.md` and `mitzu/context/voice.md` as a starting shape for the last
two. Rename every template as you copy it: drop the `.template`.

**2. Write the chain, top down.** In this order, because each one feeds the next:

- `icp.md`: who uses it, who signs, and the three to five objections your reps actually hear,
  in the buyer's words. The anti-ICP does more work than the ICP.
- `jtbd.md`: two or three jobs. When, I want to, so I can. One quote under each.
- `messaging.md`: the one line a stranger understands, the wedge, three pillars. No pillar
  without proof.

**3. Write the brain from them.** Fill `CLAUDE.md`. Most of it is a summary of the three files
above, plus the parts only the brain holds: what the product does not do, and the claims that
are off limits. Keep the "Built from" list at the top so the next person can see where every
line came from. Twenty minutes, if the three files are done.

**4. Reuse the briefs.** Copy `mitzu/compete-agent.md` (or the template), and change only what
is Mitzu-specific: the two competitors and the wedge. The rules stay. Same for
`mitzu/position-agent.md` and `mitzu/launch-agent.md`: they already point at `CLAUDE.md` and
`context/`, so they work on your brain as written. Once Compete works, they take an evening each.

**5. Write the eval, then run.** Fill `evals/expected-output.md` before the first run. Then do
step 4 and step 5 above, from inside your folder, with your competitors' pricing pages.

When an output comes back generic, walk the chain upward. A weak battle card is usually a thin
objection list in `icp.md`, not a bad brief.

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
| `mitzu/context/` | The layers the brain is built from: ICP (with the four buyer objections and the anti-ICP), jobs to be done, messaging, competitors, voice. |
| `mitzu/compete-agent.md` | The Compete brief, the one on screen in the webinar. |
| `mitzu/position-agent.md`, `mitzu/launch-agent.md` | The other two briefs. Same shape, different job. |
| `mitzu/evals/` | Expected output, written before the run, and the scorecard rubric. |
| `mitzu/outputs/` | What the agents produced. Compare yours against these. |
| `templates/` | Blank ICP, jobs to be done, messaging, brain, brief and expected output. For your product. |
| `docs/LADDER.md` | v0 to v5. What each version adds, what it costs, and how it fails. |

## Going further

The free skills the course agents run, one install, no course required. This one line needs
Node (nodejs.org, the LTS button) installed first:

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
