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

# Squash commits made since branching:
Squash commits made on branch1 since branching from master:
```bash
git rebase -i $(git merge-base branch1 master)
```

# Rebase n commits from feature1 to master
```bash
git checkout feature1
git rebase master
git checkout master
git merge feature1
```

# Rebase and squash n commits from feature1 to master
```bash
git checkout feature1
git rebase -i master
# pick, squash.. etc
git checkout master
git merge feature1
```
