# Learning Log

A daily record of what I built, what I learned and what went wrong.

---

## Day 1
**What I did**
- Created the `teamboard` repo on GitHub (public, README, Node .gitignore, no license)
- Cloned it to my computer with `git clone`
- Learned the difference between Git (the tool on my computer) and GitHub (the online copy)

**What I learned**
- Repo, remote, local, clone
- `git status` shows what changed
- `.gitignore` keeps secrets (`.env`) and heavy folders (`node_modules`) out of the repo
- `origin` is the nickname for the GitHub copy, `main` is a branch

**Problems faced**
- None today

---

## Day 2
**What I did**
- Created the `client`, `server` and `docs` folders with placeholder `.gitkeep` files
- Made my first commit and tried to push
- Wrote the README and `features.md`

**What I learned**
- `git add` stages changes, `git commit` saves a snapshot locally, `git push` uploads it
- Git does not track empty folders, so folders need a placeholder file
- `git mv` only works on files that are already tracked

**Problems faced**

1. **Push failed: "Authentication failed"**
   - Cause: GitHub no longer accepts account passwords in the terminal
   - Fix: removed the old saved credential in Windows Credential Manager and signed in through the browser

2. **Push rejected: "non-fast-forward"**
   - Cause: I committed the README twice by accident, then used `git reset --soft` to undo it. It went back one commit too far and removed the folder-structure commit that was already on GitHub. My history and GitHub's history split apart.
   - Fix: `git pull --rebase`, which put GitHub's commit underneath mine, then `git push`
   - Lesson: do not rewrite commits that are already pushed, and check `git log --oneline` before using `git reset`

3. **Typed `git --rebase` instead of `git pull --rebase`**
   - Lesson: the format is `git <command> <options>`

**Key commands used**