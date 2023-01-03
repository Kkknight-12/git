# Git Diff

### check git commits

```bash
git log --oneline
```

![Screenshot 2023-01-02 at 6.46.46 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_6.46.46_PM.png)

### Diff

![Screenshot from 2023-01-02 18-48-33.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_18-48-33.png)

![Screenshot 2023-01-02 at 6.49.47 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_6.49.47_PM.png)

it looks gibberish.

### Guide to read git diff

![Screenshot from 2023-01-02 18-56-24.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_18-56-24.png)

![Screenshot from 2023-01-02 18-57-47.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_18-57-47.png)

![Screenshot from 2023-01-02 18-58-34.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_18-58-34.png)

![Screenshot from 2023-01-02 18-58-57.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_18-58-57.png)

![Screenshot from 2023-01-02 19-02-16.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_19-02-16.png)

![Screenshot from 2023-01-02 19-03-15.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_19-03-15.png)

### Viewing unstaged changes

![Screenshot 2023-01-02 at 7.16.09 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.16.09_PM.png)

![Screenshot from 2023-01-02 19-17-31.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_19-17-31.png)

below are all the changes that we have not staged.

![Screenshot 2023-01-02 at 7.23.55 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.23.55_PM.png)

![Screenshot 2023-01-02 at 7.24.17 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.24.17_PM.png)

### Viewing working directory changes

![Screenshot from 2023-01-02 19-27-24.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_19-27-24.png)

![Screenshot 2023-01-02 at 7.30.48 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.30.48_PM.png)

if we do `git add` and then we check the difference with `git diff`  we see nothing as it shows the difference between the working directory and the staging area.

![Screenshot 2023-01-02 at 7.32.10 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.32.10_PM.png)

but with git diff head we can still the changes as it compare the difference between working directory and HEAD ( show all staged and un-staged changes ).

### Viewing Staged Changes

![Screenshot from 2023-01-02 19-41-48.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-02_19-41-48.png)

now after making few changes to file.

![Screenshot 2023-01-02 at 7.56.12 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.56.12_PM.png)

running command git add

to see the staged changes we have run

![Screenshot 2023-01-02 at 7.57.09 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.57.09_PM.png)

git diff will not show anything

![Screenshot 2023-01-02 at 7.56.43 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-02_at_7.56.43_PM.png)

```bash
# unstaged changes
git diff

# stages changes
git diff --staged

# stages and unstaged changes
git diff --HEAD
```

### Diffing Specific File

![Screenshot from 2023-01-03 19-45-26.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-03_19-45-26.png)

we have two files which have staged changes

```bash
git diff --staged
```

![Screenshot 2023-01-03 at 7.51.08 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-03_at_7.51.08_PM.png)

but we want to see changes of only songFile then

```bash
git diff --staged songFile.txt
```

![Screenshot 2023-01-03 at 7.50.18 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-03_at_7.50.18_PM.png)

you can also see changes of more than one specific file by separating the path by space.

```bash
git diff HEAD songFile.txt podcastFile.txt
```

### Comparing Changes Across Branches

![Screenshot from 2023-01-03 20-01-08.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-03_20-01-08.png)

```bash
git diff master..odd_numbers
```

master will be compared with the odd_number

![Screenshot 2023-01-03 at 8.11.37 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-03_at_8.11.37_PM.png)

master we have -. 1, 2, 3, 4

odd_number have → 1,  3, 5

we can also separate the branches which space.

```bash
git diff master odd_numbers
```

### Comparing Commits

![Screenshot from 2023-01-03 20-17-00.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_from_2023-01-03_20-17-00.png)

comparing the commits

```bash
git log --oneline
```

![Screenshot 2023-01-03 at 8.11.37 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-03_at_8.11.37_PM%201.png)

comparing commits

```bash
git diff cfe6070..95dffa0
```

![Screenshot 2023-01-03 at 8.22.09 PM.png](Section%208%207b262cbeb74b4641a961494482ce4460/Screenshot_2023-01-03_at_8.22.09_PM.png)