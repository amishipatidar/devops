# Git Task 2 – Cherry-Pick

## Objective

The objective of this task is to understand Git branches and the `git cherry-pick` command. I created commits on the main branch, created a separate branch, made additional commits, and then cherry-picked one specific commit into the main branch.

---

## Step 1: Commits on Main Branch

First, I created the Git Task 2 file and made two commits on the `main` branch.

### Commands

```bash
touch task2.txt
echo "Git Task 2 - Cherry Pick" > task2.txt
git add task2.txt
git commit -m "Add Git Task 2 file"
```

Second commit:

```bash
echo "This is the second commit on main" >> task2.txt
git add task2.txt
git commit -m "Update Git Task 2 on main"
```

### Git Log

```
fc64f22 Update Git Task 2 on main
29fc380 Add Git Task 2 file
```

### What I Understood

These commits were created directly on the `main` branch.

---

## Step 2: Create a New Branch

I created a new branch called `cherry-pick-branch`.

### Command

```bash
git checkout -b cherry-pick-branch
```

The new branch was created from the current state of `main`.

---

## Step 3: Make Commits on the New Branch

I made two commits on `cherry-pick-branch`.

### First Commit

```bash
echo "Change made on cherry-pick branch - commit 1" >> task2.txt
git add task2.txt
git commit -m "Add change on cherry-pick branch"
```

Commit ID:

```
ca72a58
```

### Second Commit

```bash
echo "Another change on cherry-pick branch - commit 2" >> task2.txt
git add task2.txt
git commit -m "Add second change on cherry-pick branch"
```

Commit ID:

```
92c5380
```

### Git Log

```
92c5380 Add second change on cherry-pick branch
ca72a58 Add change on cherry-pick branch
fc64f22 Update Git Task 2 on main
29fc380 Add Git Task 2 file
```

---

## Step 4: Switch Back to Main

I switched back to the `main` branch.

```bash
git checkout main
```

Before cherry-picking, the branch history did not contain the commits from `cherry-pick-branch`.

---

## Step 5: Cherry-Pick a Specific Commit

I selected commit `ca72a58` from the `cherry-pick-branch`.

### Command

```bash
git cherry-pick ca72a58
```

### Output

```
[main 806247f] Add change on cherry-pick branch
1 file changed, 1 insertion(+)
```

Git created a new commit on `main` containing the changes from the selected commit.

---

## Step 6: Verify the Cherry-Pick

I used `git log` to verify the change.

```bash
git log --oneline -5
```

### Output

```
806247f Add change on cherry-pick branch
fc64f22 Update Git Task 2 on main
29fc380 Add Git Task 2 file
dde648f Add Git Task 1 documentation
7f54d24 Test git commit a m
```

The cherry-picked commit is now present on `main`. The second commit from the branch (`92c5380`) was not cherry-picked.

---

## Step 7: Verify the File

### Command

```bash
cat task2.txt
```

### Expected Output

```
Git Task 2 - Cherry Pick
This is the second commit on main
Change made on cherry-pick branch - commit 1
```

This confirms that the selected change was successfully brought into `main`.

### What I Understood

`git cherry-pick` allows a specific commit from another branch to be applied to the current branch. In this task, I selected commit `ca72a58` from `cherry-pick-branch` and applied it to `main`. The original branch still contains both of its commits, while `main` received only the selected change.

---

## Conclusion

I successfully created multiple commits on `main`, created a separate branch with additional commits, identified a specific commit using `git log`, and cherry-picked that commit into `main`. This demonstrated how Git cherry-pick can be used to selectively bring a particular change from one branch into another.
