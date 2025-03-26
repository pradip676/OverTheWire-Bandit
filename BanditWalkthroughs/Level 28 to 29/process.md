# OverTheWire Bandit: Level 28 → Level 29 Walkthrough

## 🔐 Password for bandit28:
```
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

---

## 📂 Level Goal

> There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via port `2220`. 
> The password for the user `bandit28-git` is the same as for the user `bandit28`.
> 
> Clone the repository and find the password for the next level.

---

## 🚀 Solution

### ✅ Step 1: Log in to bandit28
```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```
Use the password for bandit28 when prompted.

---

### ✅ Step 2: Clone the Git repository
```bash
cd /tmp
cd bandit28repo
cd repo
git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
```


---

### ✅ Step 3: Read the password from the repo
```bash
ls -a
cat README.md
```
You will see:
```
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

---

## 🔐 Final Password for Bandit29
```
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

---


