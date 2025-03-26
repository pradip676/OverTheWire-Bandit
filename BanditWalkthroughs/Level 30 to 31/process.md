# OverTheWire Bandit: Level 30 → Level 31 Walkthrough

## 🔐 Password for bandit30:

```
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

---

## 📂 Level Goal

> There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via port `2220`.\
> The password for the user `bandit30-git` is the same as for the user `bandit30`.\
> Clone the repository and find the password for the next level.

---

## 🚀 Solution

### ✅ Step 1: Clone the repository

```bash
cd /tmp
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
cd repo
```

---

### ✅ Step 2: Inspect the contents

```bash
cat README.md
```

Output:

```
just an epmty file... muahaha
```

Nothing useful in the file.

---

### ✅ Step 3: Check for branches

```bash
git branch -a
```

Output:

```
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

No extra branches either.

---

### ✅ Step 4: Check for tags

```bash
git tag
```

Output:

```
secret
```

---

### ✅ Step 5: View the tag contents

```bash
git show secret
```

Output:

```
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

That’s the password for the next level!

---

## 🔐 Final Password for Bandit31

```
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

---

## 🔓 Log in to Bandit31

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```

Paste the password when prompted.

Nice work using Git tags to uncover the secret! 🚀

