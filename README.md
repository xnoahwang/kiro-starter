# kiro-starter

A minimal Kiro configuration template for AI-assisted development — clean, no redundancy, ready to fork.

Combines [Andrej Karpathy's LLM coding guidelines](https://github.com/forrestchang/andrej-karpathy-skills) with practical engineering standards into a lean file structure that works out of the box.

## File Structure

```
.kiro/
  steering/
    behavior.md   ← AI behavior rules, auto-injected every session
    project.md    ← Project context, reference with #project in chat
.kiro-rules       ← Kiro-specific interaction settings (Plan Gate, Eco-Mode)
progress.md       ← Project state log
```

## How It Works

**`behavior.md`** is automatically injected into every Kiro session — no setup needed. It covers:

1. Think Before Coding — state assumptions, ask before guessing
2. Simplicity First — minimum code, no speculative features
3. Surgical Changes — touch only what's needed
4. Goal-Driven Execution — verifiable success criteria
5. Exploration First — read before writing
6. Input Handling — extract intent from Chinese or English input, filter noise
7. Response Format — 2–3 line summaries, no filler
8. Security — no hardcoded secrets, `.env` only
9. Code Standards — clean naming, modular architecture
10. State Persistence — keep `progress.md` and `project.md` up to date

**`project.md`** is a manual-inclusion file. Fill it in when your project is defined, then reference it in chat with `#project`.

**`.kiro-rules`** enforces two Kiro-specific behaviors: Plan Gate (output a plan and wait for "GO" before writing code) and Eco-Mode (concise, technical responses).

## Getting Started

**Option A — Download (recommended)**

1. Download this repo as a ZIP and extract it into your project root
2. Delete this `README.md`
3. Fill in `.kiro/steering/project.md` with your tech stack and project details
4. Open the folder in Kiro — `behavior.md` is already working in the background

**Option B — Clone**

```bash
git clone https://github.com/YOUR_USERNAME/kiro-starter.git my-project
cd my-project
rm README.md
```

Then fill in `.kiro/steering/project.md` and start building.

## Design Principles

- **No redundancy** — every rule lives in exactly one place
- **No cross-tool overhead** — built specifically for Kiro, no compatibility shims
- **Minimal surface area** — 4 files, each with a single clear purpose
- **Fills in as you go** — `project.md` and `progress.md` start as templates and grow with the project

## Credits

Behavior rules derived from [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) by [@jiayuan_jy](https://x.com/jiayuan_jy), based on [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on LLM coding pitfalls.
