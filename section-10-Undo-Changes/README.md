# Section 10

# Undoing Changes

We will be reading out checkout to a commit

![Screenshot from 2023-01-07 21-45-04.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-07_21-45-04.png)

we can get these commit with git log

```bash
git log

```

![Screenshot 2023-01-07 at 9.46.03 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_9.46.03_PM.png)

or better we can write oneline

```bash
git log --oneline
```

![Screenshot 2023-01-07 at 9.52.55 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_9.52.55_PM.png)

so if you want to go back in time you can take the commit hash which is the abbreviated version ( first 7 digits ) for the commit that is what you need.

now lets check out to old commit → 699589b

```bash
git checkout 699589b
```

![Screenshot 2023-01-07 at 9.55.58 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_9.55.58_PM.png)

![Screenshot 2023-01-07 at 9.56.28 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_9.56.28_PM.png)

we have jumped back in time where have just created a file and a line to it before making a commit.

![Screenshot from 2023-01-07 21-57-37.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-07_21-57-37.png)

lets see where the head is pointing to 

![Screenshot 2023-01-07 at 9.58.19 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_9.58.19_PM.png)

### Reattaching our detached head

![Screenshot from 2023-01-07 22-03-08.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-07_22-03-08.png)

we have our head detached which used to point at a branch. we can see that with git status

```bash
git status
```

![Screenshot 2023-01-07 at 10.04.07 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.04.07_PM.png)

we can re-attach the head by checking to a branch name

![Screenshot from 2023-01-07 22-05-32.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-07_22-05-32.png)

```bash
git checkout master
```

![Screenshot 2023-01-07 at 10.07.51 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.07.51_PM.png)

![Screenshot 2023-01-07 at 10.08.55 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.08.55_PM.png)

now lets go back in time and create a new branch and save your changes to it. So that Head can point to a new branch.

```bash
git checkout 699589b
```

now lets create a new branch

```bash
git checkout -b time-t-branch
```

![Screenshot 2023-01-07 at 10.14.25 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.14.25_PM.png)

or

```bash
git switch -c time-t-branch
```

now our head is pointing to an actual branch

![Screenshot 2023-01-07 at 10.15.20 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.15.20_PM.png)

we can add commit to this branch.

![Screenshot 2023-01-07 at 10.17.23 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.17.23_PM.png)

now we can switch to master and continue our work.

![Screenshot 2023-01-07 at 10.18.32 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.18.32_PM.png)

![Screenshot 2023-01-07 at 10.18.57 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-07_at_10.18.57_PM.png)

### Referencing Commits Relative to HEAD

![Screenshot from 2023-01-08 12-46-08.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_12-46-08.png)

so our head is pointing to the 38a3377

![Screenshot 2023-01-08 at 2.19.48 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_2.19.48_PM.png)

we can go back one commit with 

```bash
git checkout HEAD~<Number>
```

![Screenshot from 2023-01-08 14-20-17.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_14-20-17.png)

let go back 2 commit

```bash
git checkout HEAD~2
```

![Screenshot 2023-01-08 at 2.24.13 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_2.24.13_PM.png)

now we are at → 315903c 

![Screenshot 2023-01-08 at 2.25.19 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_2.25.19_PM.png)

yellow tag is at 315903c

we can go back with

```bash
git switch master
```

![Screenshot 2023-01-08 at 2.26.16 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_2.26.16_PM.png)

![Screenshot 2023-01-08 at 2.27.00 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_2.27.00_PM.png)

yellow tag is pointing to 38a3377e

if you don’t remember from which branch you tried to go back on you commit you can just write

```bash
git switch -
```

you go back to your last branch

### Discard Changes with git Checkout

if you want to undo your changes you have to a file you can do that with

 

```bash
git checkout HEAD <name-of-file.extention>
```

all the changes made to this file after last commit will be removed. 

![Screenshot from 2023-01-08 17-22-40.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_17-22-40.png)

Another option to do the same is 

```bash
git checkout -- <name-of-file.extention>
```

![Screenshot from 2023-01-08 17-24-32.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_17-24-32.png)

### Un-modifying with Git Restore

![Screenshot from 2023-01-08 17-25-31.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_17-25-31.png)

![Screenshot from 2023-01-08 17-27-12.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_17-27-12.png)

after the last commit we have made some change to a file

![Screenshot 2023-01-08 at 5.38.04 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.38.04_PM.png)

we can undo all the change made after last commit with

```bash
git restore timeTravel.txt
```

which is same as `git checkout HEAD timeTravel.txt`

![Screenshot 2023-01-08 at 5.39.17 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.39.17_PM.png)

![Screenshot 2023-01-08 at 5.39.12 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.39.12_PM.png)

it just restore the HEAD to last commit

![Screenshot from 2023-01-08 17-40-53.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-08_17-40-53.png)

Another thing which can do with **restore** is reference a particular commit and go back, which will restore the content of file to that commit. 

As we can see in the picture we are changing the source to refer as the default source is just HEAD.  We can also replace the `HEAD~<Number>`

with`<Commit Hash>` . 

Lets go back 2 commit. 

```bash
git restore --source HEAD~2 timeTravel.txt
```

![Screenshot 2023-01-08 at 5.45.59 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.45.59_PM.png)

![Screenshot 2023-01-08 at 5.46.27 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.46.27_PM.png)

the content of the file is restore to 2 commit back but we are still on master and head is not detached. 

if we want to restore the context of the file to the last commit we can write

```bash
git restore timeTravel.txt
```

![Screenshot 2023-01-08 at 5.48.29 PM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-08_at_5.48.29_PM.png)

### Unstaging the commit with git restore

![Screenshot from 2023-01-09 08-48-22.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-09_08-48-22.png)

we will staging the changes and the undoing that

![Screenshot 2023-01-09 at 8.50.39 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-09_at_8.50.39_AM.png)

```bash
git add .
```

![Screenshot 2023-01-09 at 8.51.54 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-09_at_8.51.54_AM.png)

now we will be un- staging the changes with restore

```bash
git restore --staged timeTravel.txt
```

![Screenshot 2023-01-09 at 8.53.58 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-09_at_8.53.58_AM.png)

![Screenshot from 2023-01-09 08-55-58.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-09_08-55-58.png)

### Undoing Commits with Git Reset

![Screenshot from 2023-01-09 08-57-47.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-09_08-57-47.png)

let’s do some mistake commits

![Screenshot 2023-01-12 at 9.28.22 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.28.22_AM.png)

![Screenshot 2023-01-12 at 9.29.55 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.29.55_AM.png)

![Screenshot 2023-01-12 at 9.35.59 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.35.59_AM.png)

now lets revert the changes with `git reset`

![Screenshot 2023-01-12 at 9.31.52 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.31.52_AM.png)

```bash
git log --oneline
```

let go back to mistake 1 commit

```bash
git reset 65feff6
```

![Screenshot 2023-01-12 at 9.34.59 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.34.59_AM.png)

the changes are still there but we removed the commit.

 so we don’t lose the work on local but we loose the commits

Alternative to this is `Hard Reset`

![Screenshot from 2023-01-12 09-37-39.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-12_09-37-39.png)

 it’s works the same except the changes are also removed which we have made since this commit. 

```bash
git reset --hard c9e6f1e
```

![Screenshot 2023-01-12 at 9.40.02 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.40.02_AM.png)

As we can see the changes we have made after this commit is removed form our local system.

![Screenshot 2023-01-12 at 9.40.27 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.40.27_AM.png)

Although we can move to the commits we have made after mistake commit 2 and have the changes back.

![Screenshot 2023-01-12 at 9.41.27 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.41.27_AM.png)

but if in the current state you do

```bash
git log --oneline
```

you will see latest commit till the hard reset to remember the hash commit id

![Screenshot 2023-01-12 at 9.42.33 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-12_at_9.42.33_AM.png)

### Git Revert

![Screenshot from 2023-01-12 09-46-27.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-12_09-46-27.png)

![Screenshot from 2023-01-12 09-47-44.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_from_2023-01-12_09-47-44.png)

Now rather than going back and undoing the commit we can make a new commit which will have what we want, so that the history is not changed. 

![Screenshot 2023-01-13 at 9.22.09 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-13_at_9.22.09_AM.png)

![Screenshot 2023-01-13 at 9.21.40 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-13_at_9.21.40_AM.png)

```bash
git log --oneline
```

```bash
git revert 6f60eb3
```

As we can see the changes of commit 3 are removed from local, and we have made a new commit to correct it and the 
previous commit are there as well

![Screenshot 2023-01-13 at 9.23.22 AM.png](Section%2010%201cc0054a8f8e4bf59331a027580c2f38/Screenshot_2023-01-13_at_9.23.22_AM.png)