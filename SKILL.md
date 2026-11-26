---
name: phased-plan
description: Write a phased implementation plan for a medium or large task (3+ files, new architecture, several valid approaches) without implementing it. Use on "plan this", "make a plan", "วางแผนก่อนทำ", "break this into phases".
---

# Phased plan
Deliverable is a plan file. Do not implement.

1. Triage. 1-2 files and an obvious approach: say no plan is needed and stop. Otherwise continue.
2. Read `<library-root>/shared-agent-rules.md` and `memory/preferences/user.md` once; they bind the plan.
3. Fix scope with the user: what is in, what is explicitly out, constraints, and what "done" looks like. If the request already says so, restate it in one line and continue.
4. Explore with `Explore` subagents (Haiku or Sonnet), in parallel for independent areas: existing code, conventions, dependencies, tests. Do not explore large areas in the main context.
5. Match installed skills to the work (see the skill list) and name them per phase.
6. Write the plan to `<project>/docs/plans/<NN>-<slug>/overview.md` plus one `phase-<N>.md` per phase. Outside a project, use `<projects>/Plans/<NN>-<slug>/`. Format in [templates](references/templates.md).
7. Phase sizing: one function/type plus its tests, or one bug fix; at most 2-3 files; prefer 8-10 small phases over 3-4 large; split a phase with more than 5 test cases. Phases that share a type or contract run in sequence.
8. For changes to existing code ask "built from scratch, what would we build?" and plan that, not a bolt-on. For architecture choices sketch 2-3 approaches in the overview and say why one wins.
9. Self-check before presenting: each phase lists at most 3 files; phase files contain prose and names, not code; the overview has a verification section with a command or observable result per phase.
10. Summarize phases, scope, skills and verification in at most 10 lines and stop. The user decides when to execute (use `execute-plan`).
