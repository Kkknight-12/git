### Initialize a new git repo

```shell
git init
```
the command will initialize a new git repo.

### .git
initializing a repo creates a hidden folder named .git. Deleting it will delete all your git history

#### delete .git file
```shell
rm -rf .git
```

### git log
```shell
git log
```
git log retrieve the log of commits for a given repo

## steps to push a file/folder to git
1. stack all the files to 
```shell
git add .
```

2. optional ->  if you want to stack any specific file
```shell
git add fileName.extension
```
3. write a commit message
```shell
git commit -m "your message"
```
we can add and commit in one line
```shell
git commit am - "add and commit in single line"
```
4. push to git
```shell
git push
```