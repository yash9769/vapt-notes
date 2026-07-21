# Phase 2 — Linux Fundamentals

# Concept 3: Linux File Permissions

## Why File Permissions Matter

Linux is a multi-user operating system. Many users can use the same machine, so Linux must control:

* Who can read a file.
* Who can modify a file.
* Who can execute a file.

This is done using **file permissions**.

For a penetration tester, weak permissions often lead to **Privilege Escalation**.

---

# Three Types of Users

Every file has permissions for three categories:

```text
Owner (u)

Group (g)

Others (o)
```

Example:

```text
-rwxr-xr--
```

Break it into:

```text
- rwx | r-x | r--
  ↑      ↑      ↑
Owner  Group Others
```

---

# Three Permission Types

## Read (r)

Value:

```text
4
```

Allows:

* Open a file.
* Read its contents.

---

## Write (w)

Value:

```text
2
```

Allows:

* Modify a file.
* Delete a file (if directory permissions allow).

---

## Execute (x)

Value:

```text
1
```

Allows:

* Run a program.
* Execute a script.

---

# Permission Values

| Permission | Value |
| ---------- | ----: |
| Read       |     4 |
| Write      |     2 |
| Execute    |     1 |

Total permission = Sum of values.

Examples:

| Number | Permission |
| ------ | ---------- |
| 7      | rwx        |
| 6      | rw-        |
| 5      | r-x        |
| 4      | r--        |
| 3      | -wx        |
| 2      | -w-        |
| 1      | --x        |
| 0      | ---        |

---

# Understanding chmod Numbers

Example:

```bash
chmod 755 script.sh
```

Means:

```text
Owner  → 7 → rwx

Group  → 5 → r-x

Others → 5 → r-x
```

---

Another example:

```bash
chmod 644 notes.txt
```

Meaning:

```text
Owner  → rw-

Group  → r--

Others → r--
```

---

# Common chmod Commands

Give full permissions:

```bash
chmod 777 file.txt
```

⚠️ Never use this on production systems.

---

Owner only:

```bash
chmod 700 secret.txt
```

---

Typical executable:

```bash
chmod 755 script.sh
```

---

Typical text file:

```bash
chmod 644 report.txt
```

---

# Symbolic chmod

Instead of numbers:

Add execute permission:

```bash
chmod +x script.sh
```

Remove execute permission:

```bash
chmod -x script.sh
```

Add write permission to owner:

```bash
chmod u+w file.txt
```

Remove write permission from others:

```bash
chmod o-w file.txt
```

---

# Viewing Permissions

Command:

```bash
ls -l
```

Example:

```text
-rwxr-xr-- script.sh
```

Interpretation:

| User   | Permission |
| ------ | ---------- |
| Owner  | rwx        |
| Group  | r-x        |
| Others | r--        |

---

# chown

Change file ownership.

Example:

```bash
sudo chown kali report.txt
```

Change owner and group:

```bash
sudo chown kali:kali report.txt
```

---

# sudo

Some commands require administrator privileges.

Example:

```bash
sudo apt update
```

Without `sudo`, Linux may return:

```text
Permission denied
```

---

# VAPT Perspective

Common privilege escalation findings:

* World-writable files (`777`)
* Sensitive files readable by everyone
* Executable scripts owned by the wrong user
* Misconfigured SUID binaries (covered later)

Checking permissions:

```bash
ls -la
```

is one of the first commands during an internal assessment.

---

# Memory Tricks

```text
r = Read

w = Write

x = Execute
```

```text
4 = Read

2 = Write

1 = Execute
```

Remember:

```text
7 = 4+2+1 = rwx

6 = 4+2 = rw-

5 = 4+1 = r-x

4 = Read only
```

---

# Interview Questions

### What does `chmod 755` mean?

Owner has read, write, and execute permissions. Group and others have read and execute permissions.

---

### Difference between `chmod` and `chown`?

* `chmod` changes permissions.
* `chown` changes ownership.

---

### Why is `chmod 777` dangerous?

Because every user can read, modify, and execute the file, making it a serious security risk.

---

# Key Takeaways

* Linux permissions are based on **Owner**, **Group**, and **Others**.
* The three permissions are **Read**, **Write**, and **Execute**.
* `chmod` changes permissions.
* `chown` changes ownership.
* `sudo` executes commands with administrative privileges.
* Misconfigured permissions are a common privilege escalation vector in penetration testing.
