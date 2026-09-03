# Git Task 1 — git commit -a -m

## Objective

The objective of this task is to practice `git commit -a -m` and understand the difference between `git commit -a -m` and `git commit -m`.

---

## 1. Initial Commit

### Commands

```bash
touch task1.txt
echo "Git Task 1 - Initial content" > task1.txt
git add task1.txt
git commit -m "Add Git Task 1 file"
```

### Output

```
[main 5b92987] Add Git Task 1 file
1 file changed, 1 insertion(+)
create mode 100644 git/task-1/task1.txt
```

### What I Understood

The new file was initially untracked, so I used `git add` to stage it before committing. This shows that a new file must be staged before it can be committed using `git commit -m`.

---

## 2. Testing git commit -m

### Commands

```bash
echo "Testing git commit -m" >> task1.txt
git status
```

### Output

```
Changes not staged for commit:
    modified: task1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

I then staged the modified file and committed it:

```bash
git add task1.txt
git commit -m "Test git commit m"
```

### Output

```
[main 6f8571c] Test git commit m
1 file changed, 1 insertion(+)
```

### What I Understood

`git commit -m` commits changes that are already staged. Therefore, after modifying the tracked file, I had to use `git add task1.txt` before running `git commit -m`.

---

## 3. Testing git commit -a -m

### Commands

```bash
echo "Testing git commit -a -m" >> task1.txt
git status
```

### Output

```
Changes not staged for commit:
    modified: task1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Without using `git add`, I ran:

```bash
git commit -a -m "Test git commit a m"
```

### Output

```
[main 41dc8bc] Test git commit a m
1 file changed, 1 insertion(+)
```

### What I Understood

`git commit -a -m` automatically stages modifications to already tracked files and commits them with the given message. Therefore, I did not need to run `git add` separately.

---

## 4. Viewing the Commit History

### Command

```bash
git log --oneline -3
```

### Output

```
41dc8bc (HEAD -> main) Test git commit a m
6f8571c Test git commit m
5b92987 Add Git Task 1 file
```

### What I Understood

The `git log --oneline -3` command displays the three most recent commits in a compact format. It shows the commit ID and commit message. The `HEAD -> main` indicates that the current HEAD is pointing to the main branch.

---

## 5. Difference Between git commit -m and git commit -a -m

| Command | Description |
|---|---|
| `git commit -m "message"` | Commits changes that have already been staged using `git add`. |
| `git commit -a -m "message"` | Automatically stages modifications to tracked files and commits them. |

### Important Observation

The `-a` option does not automatically add new/untracked files. New files still need to be added using:

```bash
git add filename
```

---

## Conclusion

In this task, I practiced both `git commit -m` and `git commit -a -m`. I observed that `git commit -m` requires changes to be staged separately, while `git commit -a -m` can automatically stage modifications to already tracked files before committing them. I also used `git log --oneline` to verify the commits created during the task.