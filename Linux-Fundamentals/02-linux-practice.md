# Phase 2 — Linux Fundamentals

# Concept 2: Linux File System Practice & Revision

## Objective

Strengthen your understanding of Linux file system navigation and basic file management commands used daily in penetration testing.

---

# Linux File System Overview

Linux organizes all files and directories under a single root directory:

```text
/
```

Unlike Windows, Linux does not use drive letters such as `C:` or `D:`.

---

# Important Directories

| Directory | Purpose                    |
| --------- | -------------------------- |
| `/`       | Root directory             |
| `/home`   | User home directories      |
| `/root`   | Root user's home directory |
| `/etc`    | System configuration files |
| `/tmp`    | Temporary files            |
| `/var`    | Logs and application data  |
| `/usr`    | Installed programs         |
| `/bin`    | Essential system commands  |

---

# Essential Commands

## Show Current Directory

```bash
pwd
```

Displays your current working directory.

---

## List Files

```bash
ls
```

Useful options:

```bash
ls -l
```

Detailed listing.

```bash
ls -a
```

Show hidden files.

```bash
ls -la
```

Detailed listing including hidden files.

---

## Change Directory

Move into a folder:

```bash
cd Documents
```

Move back one directory:

```bash
cd ..
```

Go to home directory:

```bash
cd ~
```

Go to root directory:

```bash
cd /
```

---

## Create Directory

```bash
mkdir reports
```

Create multiple directories:

```bash
mkdir recon scans reports
```

Create nested directories:

```bash
mkdir -p pentest/web/burp
```

---

## Create File

```bash
touch targets.txt
```

Create multiple files:

```bash
touch file1.txt file2.txt
```

---

## Copy Files

```bash
cp source.txt backup.txt
```

Copy directories:

```bash
cp -r recon backup
```

---

## Move or Rename

Rename:

```bash
mv notes.txt linux-notes.txt
```

Move:

```bash
mv linux-notes.txt Documents/
```

---

## Delete

Delete a file:

```bash
rm file.txt
```

Delete a directory:

```bash
rm -r folder
```

Force delete:

```bash
rm -rf folder
```

Use `rm -rf` carefully because deletion is permanent.

---

# Absolute vs Relative Paths

## Absolute Path

Starts from the root directory.

Example:

```text
/home/kali/Documents/report.txt
```

---

## Relative Path

Starts from your current location.

Example:

```text
Documents/report.txt
```

---

# Practical Exercise

Create this structure:

```text
pentest/
├── recon/
├── scans/
├── reports/
└── targets.txt
```

Commands:

```bash
mkdir pentest
cd pentest
mkdir recon scans reports
touch recon/targets.txt
ls -R
```

---

# VAPT Relevance

These commands are used during:

* Organizing scan results.
* Managing payloads.
* Creating scripts.
* Saving screenshots and reports.
* Handling wordlists.
* Navigating Kali Linux.

---

# Memory Sheet

```text
pwd      → Current directory

ls       → List files

ls -la   → Detailed list + hidden files

cd       → Change directory

cd ..    → Go back one folder

cd ~     → Home directory

cd /     → Root directory

mkdir    → Create folder

touch    → Create file

cp       → Copy

mv       → Move / Rename

rm       → Delete

rm -r    → Delete folder

rm -rf   → Force delete folder
```

---

# Interview Questions

### What does `pwd` do?

Displays the current working directory.

---

### Difference between `cp` and `mv`?

* `cp` creates a copy.
* `mv` moves or renames the original.

---

### Difference between absolute and relative paths?

* Absolute paths begin from `/`.
* Relative paths begin from the current working directory.

---

### Key Takeaways

* Linux uses a single root directory (`/`).
* Learn navigation before learning security tools.
* Master `pwd`, `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, and `rm`.
* These commands are used constantly in Kali Linux during VAPT engagements.
