# Developer Onboarding Doc — v2 changes (for Faral)

Draft to merge into the Google Doc [developer-onboarding-doc](https://docs.google.com/document/d/1gTqbgcXnQY08ghMOLkI2oQuS9KkZ7dpLymNpFRZraik/edit). It has three parts:

- **A.** Fixes to the current doc
- **B.** New sections, ready to paste
- **C.** What to move out of the Week 1 reading list

Faral's Week 1 Thursday task is to follow the doc's UPM install section word for word and log every place it fails. Her friction log becomes **v3**, which she owns from Week 7.

---

## A. Fixes to the current doc

| Where | Problem | Fix |
|---|---|---|
| §1 Software | `Unity Ver. {insert latest LTS version here}`: the placeholder was never filled in | Pin the exact version the games use (e.g. `6000.0.x LTS`) and name which game uses which version |
| §2 UPM paragraph | "For more information on **GoodDay work**, please check the UPM section": copy-paste error | "For more information on UPMs…" |
| §1 Accounts | Doesn't say who grants each account or how long it takes | Add an "Ask for it from" column. Lee Kang lost time waiting on repo access (the Unity Project Conventions repo, ASW) |
| §3 GoodDay example | The bug example says "Logged bugs found within a Google Doc", but gives no format | Link to the new **Bug reports** section (B2) |
| §4 GitHub | ~40% of the doc is a Git tutorial, and it comes before anything about how the team works | Move it to an appendix ("skip if you know Git") |
| §5 Coding | The design pattern exercises read like Week 1 homework | Label them **Phase 2 / Month 4** for validation-first interns (see C) |
| §6 UPM install | The SSH / PAT / manifest steps are long and branch a lot. They're the most likely place an intern gets stuck | Faral's Week 1 friction log rewrites this section. Add a "you're done when…" check at the end |
| §7 Who to ask | "Spend a bit of time troubleshooting first" isn't a clear rule, and only Kung and Lucian are listed | Replace with the **30-minute rule** and the **who-owns-what** table (B4) |
| Everywhere | Lots of `[link]` text with no URL behind it | Check every link. Faral's friction log should flag the broken ones |

---

## B. New sections to add

### B1. Your first 3 months: why validation comes first

> You'll write code here — in Month 4. First, for 3 months, you'll validate and document real releases of our live games: Postknight 2, Abyssfall, Postknight, Tiny Guardians and King's League Odyssey.
>
> This isn't a warm-up. Syntax is the easy part of engineering to teach. **Judgement is the hard part:** knowing what can go wrong, what matters to a player, and what "done" actually means. Validating real builds is the fastest way to build it. Every bug you reproduce teaches you how code fails. Every changelog you read teaches you how a change ripples through a game.
>
> In Month 4 you'll build tools. Which ones? You'll propose them, based on the friction you wrote down in Months 1–3.
>
> Your first real task: validating **Postknight 2 v2.7.16** with Hian, our QA lead, in Week 2.

### B2. Bug reports

Each game release gets one Google Sheet bug log. A report without every column filled in gets sent back.

| Column | What goes in it |
|---|---|
| ID | `PK2-2.7.16-001` (game, version, number) |
| Title | `[Area] What goes wrong, when`. Example: `[Shop] Gem count doesn't update after purchase until app restart` |
| Severity | **1** blocks play, loses player data or money · **2** wrong behaviour, a workaround exists · **3** cosmetic / polish |
| Reproducibility | always / sometimes (x of y tries) / once |
| Build + device | Version, build number, device model, OS version |
| Steps | Numbered, starting from app launch or a named save state |
| Expected vs actual | Two separate lines |
| Evidence | Link to a screenshot, clip or log. Every report has one |
| Status | new / confirmed / fixed / verified / won't fix |

Before you file, check: could someone who has never met you reproduce this on their first try?

### B3. Validation workflow (one release)

1. **Read the changelog** with Hian. For each change, ask: what changed, and what does it touch?
2. **Write a test plan** covering new features, regression around them, and edge cases (interrupted, offline, low storage, killed mid-save, upgrade from the last version's save). Hian approves it **before** you run anything. That's the gate.
3. **Run it.** Every result has evidence.
4. **File bugs** in the sheet (B2). Re-test fixes as they land.
5. **Update the regression checklist** for that game, so the next person can run it without you.
6. **Write the release validation report** on one page: scope → results table → open issues, ranked → go / no-go with your reasoning.
7. **Write a 3 / 2 / 1 note:** 3 things that worked, 2 friction points, 1 suggestion.

Your go / no-go is input. Hian makes the release call.

### B4. Who owns what, and when to ask

| Need | Ask | Channel |
|---|---|---|
| Accounts, access, anything about the internship | Kung (TD) | Google Chat |
| Builds, devices, test plans, bug standards, release calls | Hian (QA lead) | Google Chat / in person |
| Code, Git, UPMs, Unity setup | Lucian | Google Chat / in person |

- **30-minute rule:** stuck for 30 minutes with no new idea? Ask. Include what you tried. Silence costs more than a question.
- **Ask immediately** for anything risky: merge conflicts, anything touching a live build or store listing, anything involving player data.
- The **2-minute rule** (already in §7) still applies before every submission.

### B5. Reviews and feedback

- All review comments use [Conventional Comments](https://conventionalcomments.org): `praise:`, `suggestion:`, `issue:`, `question:`, `nitpick:`. Use them when giving feedback as well as receiving it.
- **1-on-1 with Kung** every Friday for your first month, then every two weeks. It's for friction and questions, not status.
- How you're assessed in Weeks 1–2: player judgement, rigour, edge-case thinking, written clarity, technical reading and working style. You'll score yourself too, and we'll compare. The rubric is on your portal page.

### B6. Glossary

| Term | Meaning |
|---|---|
| PK2 / PK | Postknight 2 / Postknight |
| ASW | Abyssfall |
| KLO | King's League Odyssey |
| TG | Tiny Guardians |
| UPM | Kurechii's in-house Unity packages (see §6) |
| TDN | Technical Design Note. A short design doc approved **before** any code is written (Phase 2) |
| UCB | Unity Cloud Build |
| Regression checklist | The reusable list of checks run on every release of a game |
| Release validation report | A one-page go / no-go summary for one build |

---

## C. Reading plan by phase

The current doc treats everything as Week 1 reading. For a validation-first intern:

| When | Read |
|---|---|
| **Week 1** | §1 Setup, §3 GoodDay, B1–B6, §4 Pull Requests + Writing Conventions only, §5 Naming Conventions (for her Tuesday review task) |
| **Phase 1, as needed** | §4 Git glossary, §6 UPMs (to install tools and builds) |
| **Month 4 (Phase 2)** | §5 Syntax Checklist, Design Principles, Design Patterns + exercises, Tracer Bullets, Class Diagrams, §6 How to upload a UPM |

The coding content stays the same. It just moves to the point where she's about to use it, so it isn't sitting unused for 3 months.
