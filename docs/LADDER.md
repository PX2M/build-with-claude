# The ladder

Six versions of the same agent. Each rung adds one capability and one new way
to fail. The point of teaching it as a ladder is that most people try to start
at v4, build something they cannot debug, and quietly stop using it.

You are building a small car. You need to understand the small car. Then we
talk about the Ferrari.

---

## v0, the cron job

**What it is.** A scheduled prompt. Reads an RSS feed or a changelog, posts a
digest. This is what most "AI agent" demos actually are.

**What it costs.** An afternoon.

**What it unlocks.** Nothing you could not do with a Zapier. It proves the
plumbing works, which is worth something on day one and nothing on day thirty.

**How it fails.** Nobody reads the digest. It has no memory, so every post
starts from zero and repeats what it said yesterday. Within two weeks it is
muted.

**The lesson.** A schedule is not an agent. Automation with no state is a
newsletter you send yourself.

---

## v1, state

**What it adds.** A file the agent reads and writes. The launch brief.

**What it unlocks.** "What changed since yesterday." That single question is
the whole difference between a digest and a colleague.

**How it fails.** The agent answers from conversation memory instead of
re-reading the file, so the number never moves. Test for this deliberately: it
is the most common bug and it is invisible unless you look.

**The lesson.** Memory is a file, not a feature. If you cannot open it and read
what your agent believes, you do not have an agent, you have a slot machine.

---

## v2, judgment

**What it adds.** Skills and a rubric. `launch-readiness` scores the gate.
`message-consistency` checks copy. The persona says what it will refuse.

**What it unlocks.** The agent can disagree with you. It scores red when the
launch is red, and it will not mark its own gate items done.

**How it fails.** The rubric is too kind, or the persona is too polite, and the
agent tells you what you want to hear. Write the verdict bands before you write
the prompt, and write acceptance criteria before you run it once.

**The lesson.** This is where an agent stops being a text generator. Judgment
is a document you author, not a capability you enable.

**The course ends here.** v0 to v2 is a car you can drive, park, and fix
yourself.

---

## v3, senses

**What it adds.** Script gates and mounts. A Bash gate hashes the launch folder
every 30 minutes and wakes the model only when something moved. Read-only
calendar and inbox where it earns its keep.

**What it unlocks.** The agent notices without being asked, and costs nothing
on the runs where there is no news.

**How it fails.** Every new source is a prompt injection surface. A vendor's
marketing email is now something your agent reads and might act on. And the
maintenance tax starts here: credentials expire, mounts break, schedules
silently stop firing.

**The lesson.** Cheap perception beats expensive perception. Ninety percent of
what an always-on agent should do is decide not to wake up.

---

## v4, the team

**What it adds.** Multiple agents in one workspace, each with its own Slack
identity, container, and memory. Compete feeds Position. Position feeds Launch.
Multiple concurrent launches, one agent per launch, stamped from one template.

**What it unlocks.** Portfolio-level questions. "Which of our four launches is
actually at risk." Versioning across clients: fix the template once, restamp
everyone.

**How it fails.** Agents talking to agents amplifies a wrong belief instead of
catching it. If Compete is confidently wrong about a competitor's pricing,
Position bakes it into messaging and Launch ships it.

**The lesson.** The unit of scale is the template, not the agent. And every
handoff between agents needs a human who can see both sides.

---

## v5, the Ferrari

**What it adds.** Approval-gated outbound action. Credentials never touch the
agent: they sit in a proxy that holds a request and requires a human to approve
it before it leaves. The agent can finally send, book, and publish, and every
one of those still passes a person.

**What it unlocks.** The agent stops drafting and starts doing. Outreach goes
out. Assets get published. Enforcement lives outside the model, so it does not
matter whether the agent was talked into it.

**What it costs.** This is the part people underestimate. Not build time,
operating time. Someone owns this. Someone gets paged when it breaks at 7am
before a launch.

**The lesson.** The safety comes from architecture, not from a good prompt.
Anything you can talk an agent out of, you never really had.

---

## Reading the ladder honestly

The gap between v2 and v5 is not intelligence. It is operations. Same model,
same skills, radically different amount of somebody's Tuesday.

Which is exactly why v0 to v2 should be self-serve and v3 and up should not.
