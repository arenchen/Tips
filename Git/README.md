# Git-Tips
## Create an archive of changed files
```shell
git archive -o update.zip stash $(git diff --name-only HEAD)
```
OR
```shell
zip update.zip $(git diff --name-only HEAD)
```

## Delete remote last commit
```shell
git reset --hard HEAD^
git push
```

## Restore submodules from .gitmodules
```shell
#!/bin/sh

set -e

git config -f .gitmodules --get-regexp '^submodule\..*\.path$' |
    while read path_key path
    do
        url_key=$(echo $path_key | sed 's/\.path/.url/')
        url=$(git config -f .gitmodules --get "$url_key")
        git submodule add $url $path
    done
```

## Git Config
```shell
# 不驗證 SSL 憑證
git config --global http.sslverify false

# 自動轉換換行符號
git config --global core.autocrlf true
```
