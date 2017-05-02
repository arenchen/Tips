# Git-Tips
## Create an archive of changed files
```shell
git archive -o update.zip stash $(git diff --name-only HEAD)
# OR
zip update.zip $(git diff --name-only HEAD)
```

## Delete remote last commit
```shell
git reset --hard HEAD^
git push
```
