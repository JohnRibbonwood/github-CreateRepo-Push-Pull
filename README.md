# GitHub: Create, Push, Pull

Step-by-step guides for one full cycle with the repository `JohnRibbonwood/github-CreateRepo-Push-Pull`, from the Windows Command Prompt (cmd), using Git and GitHub CLI (`gh`).

| Step | Guide | What you do |
| --- | --- | --- |
| 1 | [01-create-repo.md](01-create-repo.md) | One-time login and setup, then create the repo as public or private |
| 2 | [02-add.md](02-add.md) | Create `mytestfile.txt` and stage it |
| 3 | [03-modify.md](03-modify.md) | Add a second line and stage the change |
| 4 | [04-commit.md](04-commit.md) | Commit the new file |
| 5 | [05-delete.md](05-delete.md) | Delete the file and commit the deletion |
| 6 | [06-push.md](06-push.md) | Push both commits to GitHub |

## The whole cycle at a glance

```bat
REM 1. create the repository (use --public instead of --private for a public repo)
cd /d C:\GitHome
mkdir github-CreateRepo-Push-Pull
cd github-CreateRepo-Push-Pull
git init -b main
echo # github-CreateRepo-Push-Pull> README.md
git add . && git commit -m "Initial commit"
gh repo create github-CreateRepo-Push-Pull --private --source=. --remote=origin --push

REM 2. add a file
echo This is a test file.> mytestfile.txt
git add mytestfile.txt

REM 3. modify it
echo Second line, added later.>> mytestfile.txt
git add mytestfile.txt

REM 4. commit
git commit -m "Add mytestfile.txt" -m "Test file with two lines."

REM 5. delete it
git rm mytestfile.txt
git commit -m "Remove mytestfile.txt"

REM 6. push
git push
```
