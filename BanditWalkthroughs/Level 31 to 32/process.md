# OverTheWire Bandit: Level 31 → Level 32 Walkthrough

## 🔐 Password for bandit31:

```
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

---

## 📂 Level Goal

> There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via port `2220`.\
> The password for the user `bandit31-git` is the same as for the user `bandit31`.\
> Clone the repository and find the password for the next level.

---

## 🚀 Solution

### ✅ Step 1: Clone the repository

```bash
cd /tmp
mkdir git_level31
cd git_level31
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
cd repo
```

---

### ✅ Step 2: Check the repository files

```bash
ls -a
```

Output:

```
.git  .gitignore  README.md
```

The `.git` folder contains Git internals.
`.gitignore` tells Git to ignore certain files — useful later.

### ✅ Step 3: View the README.md

```bash
cat README.md
```

Output:

```
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```

---

### ✅ Step 4: Check `.gitignore`

```bash
cat .gitignore
```

Output:

```
*.txt
```

This means any `.txt` file (including `key.txt`) will be ignored by Git. So we must delete `.gitignore` before proceeding.

### ✅ Step 5: Create `key.txt` and delete `.gitignore`

```bash
echo 'May I come in?' > key.txt
rm .gitignore
```

---

### ✅ Step 6: Stage and commit changes

```bash
git add .
git commit -m "Added key.txt and removed .gitignore"
```

---

### ✅ Step 7: Push to the remote repo

```bash
git push origin master
```

Enter the bandit31 password when prompted.

---

### ✅ Step 8: Get the password

Output from push:

```
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

---

## 🔐 Final Password for Bandit32

```
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

---