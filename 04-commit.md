# Step 4: Commit the changes

Save the staged changes as a commit in the local repository. All commands are for the Windows Command Prompt (cmd).

Check what will go into the commit. mytestfile.txt should be listed as a **new file**:

```bat
git status
```

Commit. The first `-m` is a short title, the second `-m` adds more detail:

```bat
git commit -m "Add mytestfile.txt" -m "Test file with two lines."
```

Check that the commit is there:

```bat
git log --oneline -3
```

The commit is only on this PC until you push it in [06-push.md](06-push.md).

| Message | Fix |
| --- | --- |
| nothing added to commit but untracked files present | You forgot `git add mytestfile.txt`. |
| Changes not staged for commit | You changed the file after `git add`. Run `git add mytestfile.txt` again. |
| Author identity unknown | Set your name and e-mail (see [01-create-repo.md](01-create-repo.md), step 3). |

Next: [05-delete.md](05-delete.md)
