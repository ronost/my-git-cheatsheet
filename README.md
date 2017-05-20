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
