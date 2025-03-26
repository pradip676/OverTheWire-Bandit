# OverTheWire Bandit: Level 26 → Level 27 Walkthrough

## 🔐 Password for bandit26:
```
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

---

## 📂 Level Goal

> Good job getting a shell! Now hurry and grab the password for bandit27!

---

## 🚀 Solution

### ✅ Step 1: Log in as bandit26 (from your local terminal)
Make sure your terminal window is small vertically so that the `more` command enters interactive mode:

```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220
```
Enter the password for bandit26 when prompted.

### ✅ Step 2: Press `v` when you see the `--More--` prompt
This opens `.bashrc` in `vim`.

### ✅ Step 3: Inside vim, get a bash shell:

Press `:` to enter command mode, then type:
```vim
:set shell=/bin/bash
```
Then:
```vim
:shell
```

You are now in a real bash shell as `bandit26`!

---

### ✅ Step 4: Look for files in the home directory
```bash
ls -l
```
You will see:
```bash
-rwsr-x--- 1 bandit27 bandit26 7296 May  7  2020 bandit27-do
-rw-r----- 1 bandit26 bandit26  258 May  7  2020 text.txt
```

### 🔐 About `bandit27-do`:
- It is a binary owned by `bandit27`
- It has the **SUID** bit set, meaning when run, it executes with `bandit27`'s privileges

---

### ✅ Step 5: Use `bandit27-do` to read the password file
```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

You will see:
```bash
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

This is the **password for bandit27**!

---

## 🔐 Final Password
```
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

---