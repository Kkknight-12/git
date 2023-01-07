# Section 9

## Stashing

Senario to understand stashing

suppose we are working on a repo, and 

- we are on a master branch and then we make some commits and
- then we switch over to a new branch and then we do some work over here. And we have some un committed work on this new branch. And due to some reason we want to switch back to masters.
- in this case what happens when we have uncommitted changes on one branch and we want to switch to another branch.
    - there are generally two option to deal with it.
        - one is those changes will come with you to the branch you want to switch.
        - other is git will message you that there is conflict between files

![Screenshot from 2023-01-04 09-22-14.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-04_09-22-14.png)

### Example for →  changes will come with you to the branch you want to switch.

on master branch we have added line 7 on songFile.txt  file and committed to master branch. 

![Screenshot 2023-01-04 at 9.25.08 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.25.08_AM.png)

now we create a new branch *stshing*

```bash
git checkout -b stshing

// or

git switch -c stshing
```

![Screenshot 2023-01-04 at 9.39.17 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.39.17_AM.png)

made some changes on this branch, and now we want to go back to master without committing the current changes.

![Screenshot 2023-01-04 at 9.43.19 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.43.19_AM.png)

checking with status we can see we have some uncommited changes that we need to stash, but we are able to switch to master

![Screenshot 2023-01-04 at 9.42.25 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.42.25_AM.png)

![Screenshot 2023-01-04 at 9.43.19 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.43.19_AM%201.png)

your changes came with you to the master.

now let’s add and commit those changes from stashing branch 

![Screenshot 2023-01-04 at 9.46.50 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.46.50_AM.png)

now if we try to switch back to master we will not see those changes as they are stashed to the stashing branch 

![Screenshot 2023-01-04 at 9.47.30 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.47.30_AM.png)

### Example → other is git will message you that there is conflict between files

now lets make some changes to the master that stashing branch don't have.

![Screenshot 2023-01-04 at 9.49.42 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.49.42_AM.png)

now lets commit those changes.

now lets switch to sashing branch, this branch have the older version of data, lets add something and switch back to master.

![Screenshot 2023-01-04 at 9.53.00 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-04_at_9.53.00_AM.png)

### Stash  Save and Pop

![Screenshot from 2023-01-05 09-18-24.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-05_09-18-24.png)

![Screenshot from 2023-01-05 09-20-00.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-05_09-20-00.png)

let's make some changes to the stashing branch and check with `git status` 

![Screenshot 2023-01-05 at 9.33.51 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.33.51_AM.png)

![Screenshot 2023-01-05 at 9.24.54 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.24.54_AM.png)

now after these changes we need to switch to back to master form some reason but we don't want to bring these to the master and also we will have conflict as master have made some commit with changes on the same file. 

here we can do `git stash`. 

```bash
git stash
```

![Screenshot 2023-01-05 at 9.28.07 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.28.07_AM.png)

we can look back to the here and check those changes are gone

![Screenshot 2023-01-05 at 9.31.07 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.31.07_AM.png)

let now check out to master

```bash
git switch master
```

![Screenshot 2023-01-05 at 9.29.44 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.29.44_AM.png)

 and now we are on the master

![Screenshot 2023-01-05 at 9.30.06 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.30.06_AM.png)

now we can switch back to the stshing branch and to get back those changes we can write

```bash
git stash pop
```

![Screenshot from 2023-01-05 09-32-39.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-05_09-32-39.png)

![Screenshot 2023-01-05 at 9.33.17 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.33.17_AM.png)

we can see we have our changes back.

![Screenshot 2023-01-05 at 9.33.51 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.33.51_AM%201.png)

### Git Stash Apply

![Screenshot from 2023-01-05 09-36-02.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-05_09-36-02.png)

apply can be used in place of pop, expect after apply the changes it won’t be removed from the stash like pop. 

lets apply the changes we have made in stshing branch on master with help of stash apply.

we on stshing branch we we to `git stash`

```bash
git stash
```

now we go back to master and try to apply the stashed changes from stshing branch.

```bash
git switch master
```

![Screenshot 2023-01-05 at 9.45.33 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.45.33_AM.png)

```bash
git stash apply
```

![Screenshot 2023-01-05 at 9.46.01 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.46.01_AM.png)

as we can see these is a conflict so lets resolve it.

![Screenshot 2023-01-05 at 9.46.43 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.46.43_AM.png)

open conflict

![Screenshot 2023-01-05 at 9.50.33 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.50.33_AM.png)

this time we will accept the incoming changes ( ACCEPT THEIRS )  from stshing.

![Screenshot 2023-01-05 at 9.51.28 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.51.28_AM.png)

![Screenshot 2023-01-05 at 9.51.57 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.51.57_AM.png)

now we do add and commit as there was a conflict. 

![Screenshot 2023-01-05 at 9.53.21 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.53.21_AM.png)

now we switch back to stshing and apply stash here also 

![Screenshot 2023-01-05 at 9.54.57 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.54.57_AM.png)

 

![Screenshot 2023-01-05 at 9.59.03 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-05_at_9.59.03_AM.png)

### Multiple Stashes

![Screenshot from 2023-01-05 20-05-52.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-05_20-05-52.png)

lets add and commit above changes to continue..

lets create a new branch to practice stashing

```bash
git switch -c practice-stashing
```

now lets add some text to it

![Screenshot 2023-01-06 at 9.47.15 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.47.15_AM.png)

 now lets add and commit

![Screenshot 2023-01-06 at 9.48.54 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.48.54_AM.png)

now lets add something new and stash it

![Screenshot 2023-01-06 at 9.50.42 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.50.42_AM.png)

```bash
git stash
```

now we are back to where we started after commtting

![Screenshot 2023-01-06 at 9.51.24 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.51.24_AM.png)

now lets add something and stash it again.

![Screenshot 2023-01-06 at 9.53.51 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.53.51_AM.png)

```bash
git stash
```

lets repeat one more time

![Screenshot 2023-01-06 at 9.54.54 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.54.54_AM.png)

```bash
git stash
```

now we have 3 stash 

![Screenshot 2023-01-06 at 9.55.33 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.55.33_AM.png)

we can view our stash with 

```bash
git stash list
```

![Screenshot 2023-01-06 at 9.56.32 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_9.56.32_AM.png)

last stash is from previous stash apply practice so we can ignore it for now.

if we do git stash pop we would we popping the last one on the list → `stash@{3}` and applying it’s changes. May be we don’t want that. We can reference particular stashed by using the stash@{ } → stash id. 

```bash
git stash apply stash@{2}
```

![Screenshot 2023-01-06 at 10.01.41 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.01.41_AM.png)

instead if we apply different stash

```bash
git stash apply stash@{1}
```

we run into a conflict

![Screenshot 2023-01-06 at 10.03.04 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.03.04_AM.png)

so we can just undo the changes we got from stashing first time in file.

![Screenshot 2023-01-06 at 10.04.20 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.04.20_AM.png)

 

![Screenshot 2023-01-06 at 10.04.28 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.04.28_AM.png)

now are can apply diff stash

```bash
git stash apply stash@{1}
```

![Screenshot 2023-01-06 at 10.07.34 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.07.34_AM.png)

![Screenshot 2023-01-06 at 10.08.01 AM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-06_at_10.08.01_AM.png)

### Dropping and clearing the Stash

![Screenshot from 2023-01-07 17-58-04.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-07_17-58-04.png)

pop removes the most recent ( top most in the list ) stash and applies it. 

lets undo the changes we have applies from the last lesson.

![Screenshot 2023-01-07 at 6.02.23 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.02.23_PM.png)

![Screenshot 2023-01-07 at 6.02.17 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.02.17_PM.png)

let's check the stash list and apply the changes with `git stash pop`

![Screenshot 2023-01-07 at 6.03.52 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.03.52_PM.png)

```bash
git stash pop
```

![Screenshot 2023-01-07 at 6.06.17 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.06.17_PM.png)

 the top most was applied and removed from the list.

if you want to remove a particular stash you can 

```bash
git stash drop stash@{1}
```

![Screenshot 2023-01-07 at 6.23.33 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.23.33_PM.png)

if you want to completely delete the stash then you can 

```bash
git stash clear
```

![Screenshot from 2023-01-07 18-24-17.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_from_2023-01-07_18-24-17.png)

![Screenshot 2023-01-07 at 6.25.09 PM.png](Section%209%20b30c53403d714721abb2acab6629e1e0/Screenshot_2023-01-07_at_6.25.09_PM.png)