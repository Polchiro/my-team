# Task Note · Track all team notes on GitHub (replaces the revert steps)

- Date: 2026-10-12
- From: Leader (Wailan)
- To: Member (Taroko)
- Status: To do
- Supersedes: `20261012-revert-v3-v2.md` — **read this one instead.** The revert in that note is ALREADY DONE (commit `77269c8`), so do not run it again; this note is only the notes part.

## What to do

Put **every task note and handoff note** in `workspace/inbox/` and `workspace/outbox/` onto GitHub. They are gitignored right now; the captain wants them tracked from now on.

Project folder: `C:\Users\DELL\Documents\Default Project\my-team`
Repo: `https://github.com/Polchiro/my-team`

## Format / Steps

### 1 — un-ignore the notes
Edit `.gitignore` so it reads exactly:
```
# OS junk
Thumbs.db
desktop.ini
.DS_Store
```
(Remove the four `workspace/inbox/*.md`, `workspace/outbox/*.md`, `!.../README.md` lines — the notes are wanted now.)

### 2 — stage the notes
```powershell
git add .gitignore workspace/inbox/*.md workspace/outbox/*.md
git status
```

### 3 — commit and push
```powershell
git commit -m "Track team task and handoff notes"
git push origin main
```

## Rules

- 🚫 Do **NOT** run `git revert` — the revert is already done and pushed.
- 🚫 Do **NOT** use `git reset`, `git rebase`, or `git push --force`.
- 🚫 Do **NOT** delete or edit anything from disk. The only file you may modify is `.gitignore`.
- Do not touch `git config`, do not create or delete repos.
- If anything reports a conflict, **stop and report it** — do not force anything.

## What "done" looks like

1. `git status` clean; `git status -sb` shows `main...origin/main` in sync.
2. `git ls-files 'workspace/inbox/*.md' 'workspace/outbox/*.md'` lists **every** note (including this one and the two superseded ones).
3. `git check-ignore workspace/inbox/20261012-track-notes.md` returns nothing (no longer ignored).
4. `git ls-files workspace/outbox/` still does NOT list `bmi-calculator-v3.html`, and that file still exists on disk.
5. `bmi-calculator.html` (v1) still tracked and unchanged; `git log --oneline -3` still shows `77269c8` revert in history.
6. The notes are visible on GitHub after the push.

## When finished

Leave a one-handoff line in `workspace/outbox/` (what you did, what to watch out for, ready to use or not), then **STOP** and ask the captain to go back to the leader for a check.
