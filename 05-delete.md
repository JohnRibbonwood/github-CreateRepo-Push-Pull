# Step 5: Delete a file

Delete the file you committed in [04-commit.md](04-commit.md). All commands are for the Windows Command Prompt (cmd).

`git rm` deletes the file and stages the deletion:

```bat
git rm mytestfile.txt
```

A deletion is a change too, so commit it:

```bat
git commit -m "Remove mytestfile.txt"
```

If `git rm` refuses because the file has changes that are not committed yet, use `git rm -f mytestfile.txt`. This also throws those changes away.

Next: [06-push.md](06-push.md)
