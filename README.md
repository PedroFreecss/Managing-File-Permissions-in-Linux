# Managing-File-Permissions-in-Linux

````
# 🔐 Managing File Permissions in Linux

Controlling file permissions in Linux is essential for keeping systems secure.  
Each file and directory defines **who can read, write, or execute** it, ensuring sensitive information is only accessible to authorized users.  

This guide covers:  
- Viewing file permissions with `ls -la`  
- Understanding permission strings  
- Modifying permissions with `chmod`  
- Practical examples for real-world security  

---

## 👀 Viewing Permissions with `ls -la`

The command:

```bash
ls -la
````

Displays a detailed list of all files and directories (including hidden ones).

**Example Output:**

```
drwxr-xr-x 2 researcher2 research_team 4096 Jul 11 12:30 drafts
-rw-rw-r-- 1 researcher2 research_team 5238 Jul 11 12:30 project_t.txt
```

---

## 📖 Understanding the Permission String

Each file/directory has a **10-character string**:

```
-rw-rw-r--
```

| Part           | Characters | Meaning                             |
| -------------- | ---------- | ----------------------------------- |
| **File Type**  | 1st        | `d` = directory, `-` = file         |
| **User/Owner** | 2–4        | `rwx` permissions for the owner     |
| **Group**      | 5–7        | `rwx` permissions for group members |
| **Others**     | 8–10       | `rwx` permissions for everyone else |

**Example:** `-rw-rw-r--`

* `-` → Regular file
* `rw-` → User can read/write
* `rw-` → Group can read/write
* `r--` → Others can only read

---

## 🔧 Changing Permissions with `chmod`

The syntax:

```bash
chmod [who][operator][permission] filename
```

* **Who:** `u` (user), `g` (group), `o` (others)
* **Operator:** `+` (add), `-` (remove)
* **Permission:** `r` (read), `w` (write), `x` (execute)

---

## 📝 Practical Examples

### 1️⃣ Removing Write Access

**Goal:** Prevent *others* from writing to `project_k.txt`.

```bash
chmod o-w project_k.txt
```

---

### 2️⃣ Updating a Hidden File

**Goal:** On `.project_x.txt`, remove write from user and group, but allow group to read.

```bash
chmod u-w,g-w,g+r .project_x.txt
```

---

### 3️⃣ Securing a Directory

**Goal:** Only the owner should enter the `drafts` directory.

```bash
chmod g-x drafts
```

---

## 🌀 Quick Visual: Permission Breakdown

```
[ File Type ][ User ][ Group ][ Others ]
      -       rw-     rw-       r--

d = directory
- = regular file
r = read
w = write
x = execute
```

---

## ✅ Summary

To secure files in Linux:

* Use **`ls -la`** to inspect permissions.
* Use **`chmod`** to adjust access for user, group, and others.

🔒 By managing permissions properly, you reduce risks and ensure that **sensitive data stays protected**.

---


```

---

## 📖 References

* [GNU Coreutils Manual: chmod](https://www.gnu.org/software/coreutils/manual/html_node/chmod-invocation.html)
* [Linux man page: ls](https://man7.org/linux/man-pages/man1/ls.1.html)

---

💡 *Permissions are the first line of defense in Linux security.*

```

---

👉 Quer que eu também crie uma **cheat sheet em Markdown (`cheatsheet.md`)** com os comandos `chmod` mais usados (com tabelas e exemplos rápidos), para complementar esse README?
```
