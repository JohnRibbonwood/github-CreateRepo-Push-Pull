# Step 1: Create a repository

Create the repository `github-CreateRepo-Push-Pull` on GitHub, public or private. All commands are for the Windows Command Prompt (cmd).

## One-time setup

Do this once on each PC. You need Git and GitHub CLI (gh) installed. Check with `git --version` and `gh --version`.

### 1. Make a working folder

```bat
mkdir C:\GitHome
cd /d C:\GitHome
```

### 2. Log in to GitHub

First check whether you are already logged in, and with which account:

```bat
gh auth status
```

If you are logged in with the wrong account, run `gh auth logout` first. Then log in:

```bat
gh auth login
```

Answer the questions in this order:

| Question | Answer |
| --- | --- |
| Where do you use GitHub? | GitHub.com |
| Preferred protocol for Git operations? | HTTPS |
| Authenticate Git with your GitHub credentials? | Y |
| How would you like to authenticate GitHub CLI? | Login with a web browser |

gh shows a one-time code (like XXXX-XXXX). It is different every time. Press Enter, and the browser opens https://github.com/login/device. Paste the code there and click Authorize.

### 3. Set your name and e-mail for commits

Use your own name and e-mail:

```bat
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Create the repository

Choose public **or** private, not both, because both use the same name.

**Public** (anyone can see it):

```bat
cd /d C:\GitHome
mkdir github-CreateRepo-Push-Pull
cd github-CreateRepo-Push-Pull

git init -b main
echo # github-CreateRepo-Push-Pull> README.md
git add . && git commit -m "Initial commit"

gh repo create github-CreateRepo-Push-Pull --public --source=. --remote=origin --push
```

**Private** (only you, and people you invite, can see it): run the same commands, but end with `--private` instead of `--public`:

```bat
gh repo create github-CreateRepo-Push-Pull --private --source=. --remote=origin --push
```

What the lines do:

- `git init -b main` makes the folder a Git repository with a branch called `main`.
- `echo # github-CreateRepo-Push-Pull> README.md` creates a README file. Don't put quotes around the text: cmd would write the quotes into the file.
- `git add` and `git commit` save the first version.
- `gh repo create ... --push` creates the repo on GitHub, links it as `origin`, and uploads your commit. You don't need a separate `git push -u origin main`.

You can change the visibility later. Use `--visibility private` to make it private again:

```bat
gh repo edit JohnRibbonwood/github-CreateRepo-Push-Pull --visibility public --accept-visibility-change-consequences
```

## Check the result

Run these inside the repo folder:

```bat
REM show the link to GitHub (should list origin twice)
git remote -v

REM open the new repo in your browser
gh repo view --web
```

## Common problems

| Message or symptom | Fix |
| --- | --- |
| Name already exists on this account | The repo is already on GitHub. Skip this step. If it is not on this PC yet, get it with `gh repo clone JohnRibbonwood/github-CreateRepo-Push-Pull`. |
| A subdirectory or file ... already exists | The folder is already on this PC. Don't run `echo ... > README.md` there: it overwrites the existing README. |
| Author identity unknown | Run the two `git config` commands from step 3, then commit again. |
| src refspec main does not match any | There is no commit yet, or the branch is called `master`. Commit first, or run `git branch -M main`. |
| fatal: not a git repository | You are in the wrong folder. `cd` into the repo folder. |
| Repo not visible or push refused | You are logged in with the wrong account. Check with `gh auth status`. |

Next: [02-add.md](02-add.md)
