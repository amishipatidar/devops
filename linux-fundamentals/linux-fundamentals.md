# Linux Fundamentals

## Task 1: Soft Link & Hard Link

### Soft Link

A soft link (symbolic link) is a file that points to the path of another file or directory. It works similar to a shortcut.

To create a soft link:

```bash
ln -s original.txt softlink.txt
```

To check the link:

```bash
ls -l
```

Example:

```
softlink.txt -> original.txt
```

If the original file is deleted, the soft link becomes a broken link because it points to a path that no longer exists.

To delete a soft link:

```bash
rm softlink.txt
```

### Hard Link

A hard link is another directory entry that points to the same inode and data as the original file.

To create a hard link:

```bash
ln original.txt hardlink.txt
```

To check the inode numbers:

```bash
ls -li
```

The original file and hard link will have the same inode number.

If the original file is deleted, the hard link can still access the data because it points directly to the same inode.

To delete a hard link:

```bash
rm hardlink.txt
```

### Soft Link vs Hard Link

| Feature | Soft Link | Hard Link |
|---|---|---|
| Points to | File path | Inode |
| Inode | Different inode | Same inode |
| Works across file systems | Yes | No |
| Can link directories | Yes | Generally no |
| If original is deleted | Link becomes broken | Data remains accessible |
| Command | `ln -s` | `ln` |

### Interview Question

**Q:** What is the main difference between a soft link and a hard link?

**Answer:** A soft link points to the path of another file, while a hard link points to the same inode and data as the original file. Therefore, deleting the original file breaks a soft link, but a hard link can still access the data.

---

## Task 2: adduser vs useradd

Both `adduser` and `useradd` are used to create users in Linux, but they work differently.

### useradd

`useradd` is a low-level command used to create a user account.

Example:

```bash
sudo useradd testuser
```

Additional options are usually required to configure the home directory, shell, password, and other settings.

### adduser

`adduser` is a higher-level, more user-friendly utility, commonly available on Debian and Ubuntu systems.

Example:

```bash
sudo adduser testuser
```

It provides an interactive process and automatically helps configure the user's home directory, password, and other basic information.

### Difference

| Feature | adduser | useradd |
|---|---|---|
| Type | High-level utility | Low-level command |
| User-friendly | Yes | Less user-friendly |
| Interactive | Usually interactive | Usually non-interactive |
| Configuration | Handles many defaults automatically | Requires more options |
| Ubuntu preference | Generally preferred for manual user creation | Useful for scripts/automation |

### Recommended Command on Ubuntu

For creating a user manually on Ubuntu, `adduser` is generally preferred because it is easier to use and handles common user configuration automatically.

Example:

```bash
sudo adduser testuser
```

The user can be verified with:

```bash
id testuser
```

---

## Task 3: journalctl

`journalctl` is a Linux command used to view and query logs collected by the systemd journal.

It is useful for troubleshooting system problems and checking service activity.

### View All Logs

```bash
journalctl
```

### View Recent Logs

```bash
journalctl -e
```

This opens the logs at the most recent entries.

### View Logs for a Specific Service

```bash
journalctl -u nginx
```

Here, `-u` specifies the systemd service.

For example:

```bash
journalctl -u ssh
```

### Follow Logs in Real Time

```bash
journalctl -f
```

This continuously displays new log entries as they are generated.

### View Logs Since the Current Boot

```bash
journalctl -b
```

### Why journalctl is Useful

`journalctl` is commonly used to:

- Troubleshoot system problems
- Check service failures
- Monitor services
- Investigate system events
- View historical system logs

---

## Task 4: Linux Command Cheat Sheet

The following are important Linux commands and their basic purposes.

| Command | Purpose | Example |
|---|---|---|
| `pwd` | Shows current directory | `pwd` |
| `ls` | Lists files and directories | `ls -l` |
| `cd` | Changes directory | `cd /home` |
| `mkdir` | Creates a directory | `mkdir test` |
| `touch` | Creates an empty file | `touch file.txt` |
| `cp` | Copies files/directories | `cp file.txt backup.txt` |
| `mv` | Moves or renames files | `mv old.txt new.txt` |
| `rm` | Removes files | `rm file.txt` |
| `cat` | Displays file contents | `cat file.txt` |
| `less` | Views file contents page by page | `less file.txt` |
| `head` | Shows beginning of a file | `head file.txt` |
| `tail` | Shows end of a file | `tail file.txt` |
| `grep` | Searches for text | `grep "error" log.txt` |
| `find` | Searches for files/directories | `find . -name "*.txt"` |
| `chmod` | Changes permissions | `chmod 755 script.sh` |
| `chown` | Changes file ownership | `sudo chown user file.txt` |
| `ps` | Shows running processes | `ps aux` |
| `top` | Monitors running processes | `top` |
| `kill` | Terminates a process | `kill 1234` |
| `df` | Shows disk space usage | `df -h` |
| `du` | Shows directory/file size | `du -sh folder` |
| `free` | Shows memory usage | `free -h` |
| `uname` | Shows system information | `uname -a` |
| `whoami` | Shows current user | `whoami` |
| `id` | Shows user and group information | `id` |
| `sudo` | Runs a command with elevated privileges | `sudo apt update` |
| `history` | Shows previously used commands | `history` |
| `man` | Opens command manual | `man ls` |

---

## Conclusion

In this Linux Fundamentals homework, I learned about soft links and hard links, the difference between `adduser` and `useradd`, and how to use `journalctl` for viewing and troubleshooting system logs. I also reviewed important Linux commands used for file management, processes, permissions, system information, and troubleshooting.
