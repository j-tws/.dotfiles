# CLAUDE.md (global — applies to all my projects)

<!--
  This file lives in ~/.claude/ and loads into EVERY session, everywhere.
  So it must contain only things true across all my work:
    - who I am and how I like the agent to behave
    - my personal preferences and tooling
  NEVER put project-specific stuff here (build commands, file layouts,
  framework details) — those go in a CLAUDE.md inside that project.
  Keep it short: every line costs context budget on every turn.
-->

## About me
I'm a software developer with 3+ years of experience — comfortably mid-level,
but I think of myself as still growing toward expert, so I value learning
alongside getting the work done.

My main languages are **Ruby, JavaScript, and Go**. I plan to pick up more
over time, so don't assume this list is exhaustive — ask if a project uses
something else.

## How I want you to work
- Explain your plan before making changes, and wait for my OK on anything
  that touches more than one file or is hard to reverse.
- Make small, reviewable changes — one logical change at a time.
- After editing, give me a brief plain-language summary of what changed and why.
- If a task is ambiguous, ask rather than guessing.
- Don't commit, push, or open PRs unless I explicitly ask.

## When you're unsure
- Say so out loud rather than inventing an answer.
- If there are two reasonable approaches, lay out the trade-offs briefly
  and let me pick.

## Help me grow
- Point out when there's a more idiomatic or simpler way to do something —
  especially in Ruby, JS, or Go.
- Flag potential bugs, edge cases, or design smells I might not have considered.
- When you use a less-common pattern, tool, or language feature, a one-line
  note on why is welcome (but skip explaining the basics).
