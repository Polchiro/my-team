# Task Note · Git + GitHub setup

- Date: 2026-10-12
- From: Leader (Wailan)
- To: Member (Taroko)
- Status: To do

## What to do

Put this project folder under **git** and publish it to **GitHub using the GitHub CLI (`gh`)**. Everything is already installed and signed in — do not install or log in to anything.

Project folder: `C:\Users\DELL\Documents\Default Project\my-team`

## Format / Steps

**1. Initialise the repo** (inside the project folder only, `main` branch):
```powershell
git init -b main
```

**2. Create `.gitignore`** in the project folder with exactly these rules:
```
# task notes stay local
workspace/inbox/*.md
workspace/outbox/*.md
!workspace/inbox/README.md
!workspace/outbox/README.md

# OS junk
Thumbs.db
desktop.ini
.DS_Store
```
> Note: this ignores the **notes** (`*.md`) but keeps the finished app `workspace/outbox/bmi-calculator.html` and all READMEs tracked. Do not ignore `opencode.json` — it holds no secrets.

**3. Set the identity — repo-local only, never `--global`:**
```powershell
git config user.name "Polchiro"
git config user.email "Polchiro@users.noreply.github.com"
```
(If `gh api user/emails` shows a different `@users.noreply.github.com` address for this account, use that one instead.)

The reason: the current global email contains a student ID and must NOT appear in a public repo.

**4. Stage and check before committing:**
```powershell
git add -A
git status
```
Must be tracked: `AGENTS.md`, `leader.md`, `member.md`, `leader.cmd`, `member.cmd`, `opencode.json`, `workspace/*/README.md`, `workspace/shared/*`, `workspace/outbox/bmi-calculator.html`.
Must NOT appear: anything in `workspace/inbox/`, and `workspace/outbox/20261012-bmi-calculator*.md`.

**5. Commit:**
```powershell
git commit -m "Initial commit: AI team starter with BMI calculator"
```

**6. Create the public repo and push:**
```powershell
gh repo create my-team --public --source=. --remote=origin --push --description "Two-AI team workspace: leader/member relay with a BMI calculator app"
```

**7. Verify:**
```powershell
git log --oneline -1
git status
gh repo view Polchiro/my-team --json url,defaultBranchRef,visibility
git log --format='%ae' -1
```

## What "done" looks like

1. `git status` reports a clean working tree; `git log` shows exactly one commit.
2. `gh repo view` returns a **public** repo named `my-team` on branch `main`, and the push succeeded.
3. The commit author email is the `@users.noreply.github.com` address — **the student-ID email appears nowhere** in `git log --format='%ae'`.
4. `.gitignore` is present; no `workspace/inbox/*.md` or handoff `.md` is tracked.
5. Global git config is unchanged (`git config --global user.email` still the original value).
6. Nothing outside this folder was created, changed or deleted.

## When finished

Leave a one-handoff line in `workspace/outbox/` (what you did, what to watch out for, ready to use or not), then **STOP** and ask the captain to go back to the leader for a check.
