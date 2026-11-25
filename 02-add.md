# Step 2: Add a file

Create a new file and tell Git to track it. All commands are for the Windows Command Prompt (cmd).

Go into the repo folder:

```bat
cd /d C:\GitHome\github-CreateRepo-Push-Pull
```

Create the file with one line of text:

```bat
echo This is a test file.> mytestfile.txt
```

Don't leave a space before `>`, or it ends up in the file. You can also create the file with Notepad: `notepad mytestfile.txt`.

Stage the new file, so it goes into the next commit:

```bat
git add mytestfile.txt
```

To stage all new and changed files at once, use `git add .`.

Next: [03-modify.md](03-modify.md)
