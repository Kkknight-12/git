### git add and commit short version

```shell
git commit -a -m "message"
```

### show all branches

```shell
git branch
```

or

```shell
git branch -a
```

or

```shell
git branch -v
```

### create a new branch

```shell
git branch <name-of-branch>
```

### create a new branch and switch to it

```shell
git checkout -b <name-of-branch>
```

or
below command works on new git version

```shell
git switch  -c <branch-name>
```

### switch to another branch

```shell
git checkout <name-of-branch>
```

or
below command works on new git version

```shell
git switch <branch-name>
```

### Delete Branch
If you want to delete a branch, you must not be on it. Else you will fall down on the ground. 
```shell
git branch -d <name-of-branch>
```
if you want to delete a branch that is not merged. -D is equivalent to --force

```shell
git branch -D <name-of-branch>
```


### Renaming a Branch
If you want to rename a branch you must be on that branch. -m is 
move/Rename
```shell
git branch -m <name-of-branch>
```

<br/>
<hr/>
<br/>


## Scenarios

- before switching to the another branch you should do
  - git add . and git -m "message"
  - else the changes will be lost
- when you are on a branch which is up-to-date with the branch on git and create a new file, and then you try to switch 
  the repo, that file also be 
  carried 
  forwarded to the changed branch. 