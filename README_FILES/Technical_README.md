## Collaborating on GitHub

Collaborating on a GitHub repository makes it easy for multiple people to contribute, review, and maintain code together. This guide covers inviting collaborators, common workflows using branches and pull requests, and a few practical best practices.

---

## Quick links

- GitHub Docs: https://docs.github.com
- CONTRIBUTING guide (recommended): `CONTRIBUTING.md`

---


---

## 1) Typical collaborative workflow (with pull requests)

This workflow keeps the main branch stable and uses short-lived feature branches.

1. Fork (if contributing from a personal account) and clone the repo:

	git clone <repository_url>

2. Create a new feature branch:

	git checkout -b feature/short-description

3. Make changes, stage and commit them:

	git add .
	git commit -m "Short, descriptive message"

4. Push the branch and open a Pull Request:

	git push origin feature/short-description

	Then create a PR on GitHub from your branch into the repository's main branch.

5. Request reviews, address feedback, and when approved, merge using the repo's merge policy.

---

## 2) Best practices

- Use clear, imperative commit messages (e.g. "Add user login flow").
- Rebase or merge regularly to stay up to date with `main`.
- Add a `CONTRIBUTING.md` to document coding standards and PR requirements.
- Protect main with branch protection rules and required reviews.
- Keep PRs small and focused for easier review.

---

## 3) Example PR checklist

- [ ] Branch created from latest `main`.
- [ ] All tests pass locally.
- [ ] Code is linted and formatted.
- [ ] PR description explains the why and what.
- [ ] At least one reviewer requested.

---

## Common Git commands (copy / paste)

Run these commands from the repository root. They're formatted for PowerShell but work in other shells as well — replace placeholders (like <repo_url>, <branch>, <commit>) before running.

Basic setup

```powershell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git clone <repo_url>
```

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git clone <repo_url>
```

Branching

```powershell
git checkout -b feature/short-description
git checkout main
git branch -d feature/short-description
```

```bash
git checkout -b feature/short-description
git checkout main
git branch -d feature/short-description
```

Staging & committing

```powershell
git add .
git commit -m "Short, descriptive message"
git commit --amend --no-edit    # amend last commit without changing message
```

```bash
git add .
git commit -m "Short, descriptive message"
git commit --amend --no-edit    # amend last commit without changing message
```

Syncing with remote

```powershell
git fetch origin
git pull --rebase origin main
git push origin feature/short-description
```

```bash
git fetch origin
git pull --rebase origin main
git push origin feature/short-description
```

Open a Pull Request

Create a PR on GitHub after pushing, or with GitHub CLI:

```powershell
gh pr create --base main --head <your-branch> --title "Title" --body "Description"
```

```bash
gh pr create --base main --head <your-branch> --title "Title" --body "Description"
```

Undoing & fixing

```powershell
git restore --staged <file>    # unstage a file
git restore <file>             # discard local changes to a file
git reset --soft HEAD~1        # undo last commit but keep changes staged
git revert <commit>            # create a new commit that undoes <commit>
```

```bash
# Note: on older Git versions `git restore` may not be available; use `git reset`/`git checkout --` instead.
git restore --staged <file>    # unstage a file
git restore <file>             # discard local changes to a file
git reset --soft HEAD~1        # undo last commit but keep changes staged
git revert <commit>            # create a new commit that undoes <commit>
```

Inspecting & troubleshooting

```powershell
git status
git log --oneline --graph --decorate --all
git diff
```

```bash
git status
git log --oneline --graph --decorate --all
git diff
```

Notes

- Replace placeholders before running commands.
- If you don't have the GitHub CLI (`gh`) installed, open PRs via the GitHub web UI after pushing your branch.


