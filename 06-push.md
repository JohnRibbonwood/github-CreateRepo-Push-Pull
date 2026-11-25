# Step 6: Push to GitHub

Upload your commits to GitHub. All commands are for the Windows Command Prompt (cmd).

```bat
git push
```

The output looks like this. The numbers and commit IDs will differ:

```text
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 24 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 450 bytes | 450.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/JohnRibbonwood/github-CreateRepo-Push-Pull.git
   06d5afe..6324c47  main -> main
```

Check the result in your browser. The commit list shows both "Add mytestfile.txt" and "Remove mytestfile.txt":

```bat
gh repo view --web
```

| Message | Fix |
| --- | --- |
| Updates were rejected ... fetch first | GitHub has changes you don't have yet. Run `git pull`, then `git push` again. |
| The current branch main has no upstream branch | Run `git push -u origin main` once. After that, `git push` is enough. |
| Everything up-to-date | There is nothing new to push. Check that you committed (step 4). |
