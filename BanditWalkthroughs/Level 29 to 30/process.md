# OverTheWire Bandit: Level 29 → Level 30 Walkthrough

## 🔐 Password for bandit29:
```
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

---

## 📂 Level Goal

> There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via port `2220`.  
> The password for the user `bandit29-git` is the same as for the user `bandit29`.  
> Clone the repository and find the password for the next level.

---

## 🚀 Solution

### ✅ Step 1: Log in to bandit29 and clone the repository
```bash
cd /tmp
cd bandit29repo
cd repo
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
```
Enter the password for `bandit29` when prompted.

---

### ✅ Step 2: Read the password from the README file
```bash
ls -a
cat README.md
```

The file shows:
```
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

---

## 🔐 Final Password for Bandit30
```
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

---

