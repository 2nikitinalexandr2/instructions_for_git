* https://stackoverflow.com/questions/19663093/apply-gitignore-on-an-existing-repository-already-tracking-large-number-of-file

```
git rm -r --cached .
git add .
git commit -m ".gitignore is now working"
git push

```