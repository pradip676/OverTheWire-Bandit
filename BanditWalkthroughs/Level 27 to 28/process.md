# OverTheWire Bandit: Level 27 → Level 28 Walkthrough

## 🔐 Password for bandit27:
```
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

---

## 📂 Level Goal

> There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via port `2220`. The password for the user `bandit27-git` is the same as for `bandit27`.
>
> Clone the repository and find the password for the next level.

---

## 🚀 Solution

### ✅ Step 1: Log in to bandit27
```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```
Use the password for bandit27 when prompted.

---

### ✅ Step 2: Navigate to a working directory
```bash
cd /tmp
cd bandit27repo
```

---

### ✅ Step 3: Clone the Git repository
```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
```
Enter the same password used for bandit27 when prompted for `bandit27-git`.

---

### ✅ Step 4: Explore the cloned repository
```bash
cd repo
ls -a
```
You should see a file like `README`.

---

### ✅ Step 5: Read the file
```bash
cat README
```
This reveals the password for the next level:
```bash
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

---

## 🔐 Final Password for Bandit28
```
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

---

