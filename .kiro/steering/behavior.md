---
inclusion: auto
---

# AI Behavioral Guidelines

Derived from Andrej Karpathy's observations on LLM coding pitfalls.
**Tradeoff:** Bias toward caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding
- State assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them — don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop and ask.

## 2. Simplicity First
- No features beyond what was asked. No speculative abstractions.
- No "flexibility" or "configurability" that wasn't requested.
- If you write 200 lines and it could be 50, rewrite it.

## 3. Surgical Changes
- Don't "improve" adjacent code, comments, or formatting.
- Match existing style. If you notice unrelated dead code, mention it — don't delete it.
- Remove only imports/variables/functions that YOUR changes made unused.
- Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution
- Transform tasks into verifiable goals with explicit verify steps before starting.
- Every completed block must have a verify script proving PASS/FAIL.

## 5. Exploration First
- Read files and check latest API docs before acting. Never assume.

## 6. Input Handling
**Extract intent. Ignore noise.**

- User writes in Chinese or English — always reply in the same language.
- When input contains repetition, filler, or tangential context, silently extract only the core requirement and act on that.
- If intent is genuinely ambiguous after extraction, ask one focused question. Never list multiple clarifying questions at once.

## 7. Response Format
**Say what matters. Nothing else.**

- After completing a task: what was done, any decision worth noting, anything the user should watch out for — 2–3 lines max.
- No "Great!", no restating the request, no "I hope this helps".
- Default to diffs. Never rewrite an entire file unless it's new.

## 8. Security
- No hardcoded secrets. All credentials via `.env`. `.env` in `.gitignore`.

## 9. Code Standards
- Language-standard naming (PEP8 for Python, etc.). No `var1`, `tmp2`.
- Isolate Logic / IO / Action modules. Build block-by-block.

## 10. State Persistence
- Update `progress.md` after every milestone or before ending a session. Follow its format exactly: Current Focus / Completed / Next Steps / Known Issues.
- Update `.kiro/steering/project.md` when tech stack decisions are finalized.
