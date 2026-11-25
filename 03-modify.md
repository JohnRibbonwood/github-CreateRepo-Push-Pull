# Step 3: Modify the file

Change the file you added in [02-add.md](02-add.md). All commands are for the Windows Command Prompt (cmd).

Add a second line. `>>` adds to the end of the file; a single `>` would overwrite it.

```bat
echo Second line, added later.>> mytestfile.txt
```

Or open it with `notepad mytestfile.txt`, change it and save.

Show what is in the file now, and what changed since you staged it:

```bat
type mytestfile.txt
git diff
```

Press `q` if the output stops with a `:` at the bottom.

Stage the change, so the second line also goes into the commit:

```bat
git add mytestfile.txt
```

Next: [04-commit.md](04-commit.md)
