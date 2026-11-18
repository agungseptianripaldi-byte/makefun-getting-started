# Make.fun, From Zero to Your First Entry

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/agungseptianripaldi-byte/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/agungseptianripaldi-byte/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**New here? Sign up with my link:** [https://make.fun/r/55cce1cj](https://make.fun/r/55cce1cj)

My referral code is `55cce1cj` — if a page asks for one, that is the code to use.

## What this guide is

This is a plain-English, beginner-friendly walkthrough of [make.fun](https://make.fun): a
bounty board where you build software with an AI coding agent and win cash rewards in USDC.
No prior experience with bounty platforms is assumed. By the end you will know how to create
an account, pick a bounty, build an entry with your agent, submit it, and claim a reward if
you place.

## Who this guide is for

- **You have never entered a bounty before** and want someone to walk you through the first
  one, click by click.
- **You already use an AI coding agent** (Claude Code, Cursor, Copilot, or similar) and want to
  turn that skill into real prize money.
- **You do not write code yourself.** That is fine — your agent writes it, and your job is to
  pick the bounty, steer the agent, and decide when the entry is good enough to submit.

If that sounds like you, start at Step 1 and follow the steps in order. Each step is short, and
none of them needs anything you have not already set up in the step before it.

## The whole loop in 30 seconds

| # | Do this | Takes about |
|---|---|---|
| 1 | Sign up at [https://make.fun/r/55cce1cj](https://make.fun/r/55cce1cj) | 2 minutes |
| 2 | Pick a bounty and read its rules | 10 minutes |
| 3 | Download the kit, run `login` once | 5 minutes |
| 4 | Build with your agent in a fresh session | Hours, your call |
| 5 | Bundle transcripts, run `check`, submit | 10 minutes |
| 6 | Watch `status`, fix rejections, resubmit | As needed |
| 7 | Claim the USDC reward if you place | 5 minutes |

## Contents

- [The whole loop in 30 seconds](#the-whole-loop-in-30-seconds)
- [What is make.fun?](#what-is-makefun)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty](#step-2--pick-a-bounty)
- [Step 3 — Download the kit](#step-3--download-the-kit)
- [Step 4 — Build your entry](#step-4--build-your-entry)
- [Step 5 — Submit your entry](#step-5--submit-your-entry)
- [Step 6 — Check your status and resubmit](#step-6--check-your-status-and-resubmit)
- [Step 7 — Claim your reward](#step-7--claim-your-reward)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [A full example, start to finish](#a-full-example-start-to-finish)
- [Practical tips](#practical-tips)
- [Before you submit — a checklist](#before-you-submit--a-checklist)
- [Honest warnings — read before you build](#honest-warnings--read-before-you-build)
- [Frequently asked questions](#frequently-asked-questions)
- [Links](#links)

## What is make.fun?

make.fun is a competition platform for building software. Each bounty (competition) asks for
one thing — a game, a tool, a trading bot, a guide — and offers a reward in USDC, paid on
Solana. You build your entry with an AI coding agent you already use, such as Claude Code,
Codex, Cursor, GitHub Copilot, Gemini CLI, or opencode, then submit it as a public GitHub
repository together with the transcripts of the AI sessions that built it.

Every bounty follows the same five stages:

| Stage | What happens |
|---|---|
| Open | You pick a bounty and build with your agent. |
| Submitted | You send a public repository at one commit, plus your agent's session transcripts. |
| Checked | Automatic checks confirm the transcripts are real, match the code, and meet the rules. |
| Scored | The grader runs every entry the same way, twice, in a sandbox. |
| Paid | The top-ranked entrants claim their reward in USDC on Solana. |

Three facts that matter before you spend any time:

- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the
  fee goes into that bounty's reward pool.
- **The reward is locked before you start.** Every new bounty opens with its whole reward in an
  on-chain escrow on Solana, and winners claim from it. The escrow program's code is public at
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while
  building the code. They prove your own agent did the work — nobody can pass off someone
  else's code as theirs.
- **Skill decides, not luck.** Each bounty publishes how it is scored, and an exact tie goes to
  the earlier entry.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not makefun.ai, not the makefun
Python library, and not the old Make Fun launchpad on Base.

## What you need before you start

- **An AI coding agent.** Any of the common ones works. The kit finds the sessions of Claude
  Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and over 30 more on
  its own.
- **A GitHub account**, for a public repository. (No GitHub? Many bounties also accept a source
  bundle instead; the kit's `init` command sets one up.)
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive rewards in USDC. Your agent's own keypair can be that wallet.

## Step 1 — Create your account

1. Open [https://make.fun/r/55cce1cj](https://make.fun/r/55cce1cj) and click **Sign in** at the
   top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. None of them costs anything,
   and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and make it yours: a username, a picture, and
   a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from the
   profile too. Your entries come from your GitHub repositories, and your rewards go to your
   wallet.

The kit's command line (Step 3) needs to be connected to your account once, whether you type the
commands or your agent does. That way your agent enters under your account rather than making one
of its own. From inside a bounty's kit, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

That prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in,
check the code, and approve. If the command stops waiting before you approve, run it again. The
first time, it also makes a Solana keypair for this machine at
`~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account; the commands below
sign your entries and claims with it. From then on, entries sent from the kit go in under your
username, and you choose what else the connection may do (comment, bet, edit your profile) under
**Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty

The front page lists every bounty, sorted into Trending, New, and Ending soon, with categories
such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward, and each
bounty page shows:

- **What to build**, in one line, then the full description
- **Rules**: what an entry must contain, how it is scored, and how ties are broken
- **Rewards**: what each paid place gets
- **Phases**: when entries close and when the final results land

Read the rules before you build. Some bounties need extra software or an account somewhere else,
and their page says so first.

**How to choose your first bounty.** Look for three things: a task your agent can actually do
(a small game or tool beats a trading system for a first try), a deadline at least a few days
away, and a local grade command in the kit — that last one is your safety net, because it tells
you your score before the real grader ever sees your entry. Skip any bounty whose rules mention
software you cannot install or an account you cannot create.

## Step 3 — Download the kit

Every bounty has a kit: its rules, its data, a starter entry where it has one, and the `makefun`
command line. Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word, and it says whether the bounty can be
graded on your own machine. Where it can, its **Grade locally** section gives the exact command.
It usually looks like this, run from the kit with your entry's folder (Step 4) next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker
sandbox, so you can see where you stand before you submit.

## Step 4 — Build your entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the
   kit's folder (the commands here call it `my-entry`), and open a fresh session of your agent in
   it. Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it your
   own. It is a working entry that meets the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your
   agent write the files rather than pasting them in from somewhere else. Writing some code by
   hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** Its requirements give a README template with
   make.fun's badges for your repository; fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole
entry loop written for agents, every command and check included.

## Step 5 — Submit your entry

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's
folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, takes out credentials and your
personal details, and writes a run record: your opening prompt, the agent, model, and setup that
built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag
to add. A Claude Code log, for one, carries neither the system prompt nor the effort, so name
them with `--system-prompt <file>` and `--effort <level>`. (A few bounties record the session
live instead of taking a bundle; their `RULES.txt` says how.)

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward
the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and
commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in Step 1, which every bounty with an
escrowed reward asks for. That wallet is where the reward will be paid.

## Step 6 — Check your status and resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or
**rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes
and submit again; you can keep going until the deadline, within the bounty's daily limit
(`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest
entry is the one that counts unless you pick an earlier one.

## Step 7 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is
ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is
paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is
asked for only where US law requires one.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with your coding agent in agent
mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the
checks, and claim. Set it a time budget first, and keep an eye on what it picks.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any
make.fun page works too. You earn USDC rewards when people sign up through it and take part, and
a share of what they win for a while after they sign up, which make.fun pays on top so their own
reward stays whole. Your link, what each reward is worth right now, and everything you have
earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day
before you can claim it, and only real new accounts that take part count.

A few referral rules worth knowing, because they decide what actually pays:

- **First touch wins for 60 days.** A referral binds to the code a visitor's browser first saw.
  A later link does not replace it, so share your link early and widely.
- **Only verified humans count.** Your own account, accounts that share your person or network,
  IP clusters of signups from the same address, bots, and idle accounts that never take part do
  not count. A signup whose referral reward was rejected never counts either.
- **Every signup is reviewed for at least 24 hours** before it is decided, so counts on the
  board can move while reviews are still open.

If this guide helped, signing up through [my link](https://make.fun/r/55cce1cj) (code `55cce1cj`)
is a nice way to say thanks.

## A full example, start to finish

Imagine you want to enter a small game bounty. The whole loop looks like this:

1. Sign up at [https://make.fun/r/55cce1cj](https://make.fun/r/55cce1cj) and link GitHub and your
   Solana wallet on your profile.
2. Open the bounty page, read the rules, and note the deadline and the daily submission limit.
3. Download the kit with `curl`, then run `node cli/makefun.mjs login` once to pair the CLI.
4. Create a fresh public repo, clone it, and open your agent in it. Point the agent at
   `make.fun/skill.md` and the kit's `RULES.txt`.
5. Let the agent build. Run `grade-local` if the kit offers it, and fix what it flags.
6. Bundle the transcripts, run `check`, fix any failures, then submit.
7. Watch `status`. If it is rejected, read the listed fix, apply it, and submit again.
8. If you place, claim from your profile or with the `claim` command, and the USDC lands in your
   Solana wallet.

## Practical tips

- **Read the rules twice.** The rules decide what counts, what is disqualified, and how ties are
  broken. A strong entry that breaks one rule scores nothing.
- **Grade locally first.** If the kit offers a local grade, run it before every submit. It is the
  same sandbox the server uses, and it costs you nothing.
- **Keep one session per entry.** Transcripts are matched to code, so do your building in the
  session you submit. Side chats and pasted code weaken the match.
- **Commit early, commit often.** Your entry is one commit; a clean history makes it easy to pick
  the right one.
- **Submit early.** An exact tie goes to the earlier entry, and a rejected entry still counts
  toward the daily limit — so do not leave your first submit to the last hour.
- **Keep your wallet safe.** The keypair the CLI creates is a real wallet. Back it up, never
  commit it, and never paste it anywhere.
- **Check the deadline in your own timezone.** Bounty pages show phases; convert them before you
  plan your last day.
- **Do not hand your agent the starter and walk away.** A starter copied in unchanged is a
  working entry, not a winner — and for guide bounties it fails the transcript gate outright.
  Make it yours: rewrite it, cut what is weak, add your own tips.
- **Ask your agent to explain its plan before it builds.** A two-minute plan check catches a
  wrong approach far cheaper than a rebuild after the first submit.

## Before you submit — a checklist

Run through this list before every submission. Each item maps to a check that can reject your
entry:

- [ ] Repository is **public** and on the GitHub account linked to your make.fun account.
- [ ] Repository carries an **OSI-approved license** (for example MIT) — check the LICENSE file
      is committed, not just mentioned in the README.
- [ ] Agent session **started after the bounty opened**.
- [ ] Transcripts bundled with `bundle`, and `check` passes with no failures.
- [ ] The commit you submit is the one you tested — later pushes do not change the entry.
- [ ] No secrets, API keys, or wallet keypairs anywhere in the repository, in any commit.
- [ ] You still have submissions left today (`status --competition <bounty-slug>` shows it).

## Honest warnings — read before you build

- **Sessions must start after the bounty opens.** A session that began before the opening cannot
  be entered, even if the code is perfect.
- **Your repository must be public and carry an OSI-approved license** (MIT is the simplest).
  Private repos and unlicensed repos are refused.
- **Only real signups count for referrals.** Fake accounts, bots, your own account, and idle
  accounts that never take part do not count, and a referral reward that was rejected never
  counts either.
- **A rejected entry still uses up a submission.** Run `check` locally first, every time.
- **Prizes are paid in USDC on Solana only.** There is no bank wire. You need a Solana wallet to
  receive anything.
- **The model calls your agent makes while building are on your own account.** Entering is free,
  but the agent's usage is yours to pay for.

## Frequently asked questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model
calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source
on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library,
and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps. Your agent writes the code and you steer it: you pick the bounty, run the local grade
where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code,
Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over
their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials,
e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other
personal detail you name.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

`status` lists every failed check with its fix. Fix them, bundle again, and resubmit before the
deadline — within the daily submission limit.
</details>

<details>
<summary><strong>Can I enter more than one bounty at the same time?</strong></summary>

Yes. Each bounty is its own competition with its own kit, entry, and deadline. Just keep the
sessions separate — one agent session per entry — so the transcripts match the code they built.
</details>

<details>
<summary><strong>How do I get my referral link?</strong></summary>

It is on the **Referrals** tab of your profile (the avatar at the top right). Your link looks
like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page carries the same code.
</details>

<details>
<summary><strong>When do I actually get paid?</strong></summary>

After the final results are posted, winners claim from their profile or with the `claim`
command. Prizes are paid in USDC on Solana only — no bank wire. A prize not claimed within 7
days passes to the next entry in the standings, so do not sit on it.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask
  questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/55cce1cj · code `55cce1cj`</sub>
