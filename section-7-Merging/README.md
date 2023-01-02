## Merging

Merging is when we want to incorporate changes from one branch into another.

There can be two type types of merges.

- fast forward merge -> when your feature branch have few commits and your main branch have no commit after creating
  feature branch.
- recursive & -> when your main branch also have some commits after creating feature branch which has it's own commits
-

### Fast Forward Merge

- To do so switch over to the branch you want to merge the current branch. Example if you want to merge the changes
  to tha main branch switch to the main branch.
- git merge <branch-name>, let's say bug-fix, which will merge the changes from that branch ( bug-fix ) to the current
  branch we
  are on, in this
  case
  main
  branch.
- In this case we are not considering the commit we have done on the main branch after creating bug-fix branch. We
  are considering that on main branch no work, commit has been done.

```shell
git merge <branch-name>
```

![Screenshot 2023-01-02 at 8.41.06 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_8.41.06_AM.png)

<br>
<hr>
<br>

### When you have changes to the main branch

#### -> merge with recursive strategy

![Screenshot from 2023-01-02 08-44-16.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_from_2023-01-02_08-44-16.png)

if you some commit on feature branch which are not present on main and there are some commits on main branch after
feature branch was created or commits that are not present on feature. In such case if you try to merge the feature with
main branch, git will make a commit and send you message → Merge made by the '**recursive' strategy**.

an auto generated git message will be shown on the terminal. With :q you can close the message and the git will make
a commit for you with a commit message.

![Screenshot 2023-01-02 at 9.19.35 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.19.35_AM.png)

#### -> Conflicting Changes

example 1 → on one branch somebody modified a file, and on second branch which we are merging somebody deleted the same
file .

example 2 → if on one branch we added a line, and somebody else on other branch we added the same line

. Git don’t know how to automatically merge them. It can;t decide what to keep and what to get rid off.

![Screenshot from 2023-01-02 09-26-57.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_from_2023-01-02_09-26-57.png)

### Senario

Suppose we have two branches which do some work on same file

- raju branch
- babu rao branch

these both branch work on same file songs.txt. As they are working on same file they have changes which don’t match with
each other.

to merge the changes we create a new branch from branch raju

![Screenshot 2023-01-02 at 9.45.41 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.45.41_AM.png)

Then we can merge the changes from babu rao

![Screenshot 2023-01-02 at 9.50.23 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.50.23_AM.png)

![Screenshot 2023-01-02 at 9.52.22 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.52.22_AM.png)

choosing option merge

![Screenshot 2023-01-02 at 9.53.14 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.53.14_AM.png)

![Screenshot 2023-01-02 at 9.54.02 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.54.02_AM.png)

![Screenshot 2023-01-02 at 9.54.20 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.54.20_AM.png)

now we should add and commit

![Screenshot 2023-01-02 at 9.55.22 AM.png](Section%207%209dea4a80f4ba4e25ab3fa34b79f15752/Screenshot_2023-01-02_at_9.55.22_AM.png)