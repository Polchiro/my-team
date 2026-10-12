# Task Note · Stop tracking the outbox handoff notes

- Date: 2026-10-12
- From: Leader (Wailan)
- To: Member (Taroko)
- Status: To do
- Context: commit `1d6d061` tracked every note. The captain wants the **inbox task notes** on GitHub, but the **outbox handoff notes are not needed there**. Undo only that half.

Project folder: `C:\Users\DELL\Documents\Default Project\my-team`
Repo: `https://github.com/Polchiro/my-team`

## What to do

Keep inbox notes tracked; untrack the outbox handoff notes. **Nothing is deleted from disk.**

## Format / Steps

### 1 — re-add an ignore rule for outbox notes only
`.gitignore` must end up as:
```
# handoff notes stay local
workspace/outbox/*.md
!workspace/outbox/README.md

# OS junk
Thumbs.db
desktop.ini
.DS_Store
```
(Leave the `workspace/inbox/` rules out — inbox notes stay tracked.)

### 2 — untrack the 6 handoff notes, keep them on disk
```powershell
git rm --cached workspace/outbox/20261012-*.md
git status
```
That targets only the dated handoff notes. `workspace/outbox/README.md` and `workspace/outbox/bmi-calculator.html` must stay tracked.

### 3 — commit and push
```powershell
git add .gitignore
git commit -m "Stop tracking outbox handoff notes"
git push origin main
```

## Rules

- 🚫 Do **NOT** delete any file from disk — `git rm --cached` only, never plain `git rm`.
- 🚫 Do **NOT** touch `workspace/inbox/` — all inbox notes stay tracked.
- 🚫 Do **NOT** use `git reset`, `git rebase`, or `git push --force`.
- Do not touch `git config`; the only file you may modify is `.gitignore`.
- If anything reports a conflict, **stop and report it** — do not force anything.

## What "done" looks like

1. `git status` clean; `git status -sb` shows `main...origin/main` in sync.
2. `git ls-files 'workspace/outbox/*.md'` returns **only** `workspace/outbox/README.md`.
3. `git ls-files 'workspace/inbox/*.md'` still lists **all 8** inbox notes + README.
4. All 6 handoff notes still exist on disk (`Test-Path workspace/outbox/20261012-track-notes.md` → `True`) and `git status` reports them as ignored, not as deletions.
5. `workspace/outbox/bmi-calculator.html` still tracked and unchanged; `bmi-calculator-v3.html` still untracked on disk.
6. On GitHub: `gh api repos/Polchiro/my-team/contents/workspace/outbox` lists only `README.md` and `bmi-calculator.html`; `gh api repos/Polchiro/my-team/contents/workspace/inbox` still lists all the notes.

## When finished

Leave a one-handoff line in `workspace/outbox/` (it will be local-only from now on), then **STOP** and ask the captain to go back to the leader for a check.
