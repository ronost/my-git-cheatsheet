# my-git-cheatsheet
Config and cheat sheet

# Undo example (accidently adding private.key):
```bash
git add .
git commit . -m "Add public key to repository"

git reset --soft HEAD^
git reset private.key

printf 'private.key\n' > .gitignore

git add .gitignore

git commit . -m "Add public key to repository"
```

# Undo hard reset example:
Hard reset latest commit by:
```bash
git reset --hard HEAD^
```
To undo hard reset (check reflog for index):
```bash
git reset --hard HEAD@{1}
```
