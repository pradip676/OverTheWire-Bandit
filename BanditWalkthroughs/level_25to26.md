# OverTheWire Bandit: Level 25 → Level 26 Walkthrough

## 🌟 Level Goal

> Logging in to `bandit26` from `bandit25` should be fairly easy…
> The shell for user `bandit26` is not `/bin/bash`, but something else. Find out what it is, how it works, and how to break out of it.

---

## 🔍 Problem Summary

- When trying to SSH into `bandit26`, you get instantly logged out.
- This is because `bandit26` doesn't use a normal shell (`/bin/bash`), but a custom script located at `/usr/bin/showtext`.
- That script displays a file using `more` and then exits the session with `exit 0`.

---

## 🧠 Key Insight

- The `more` command becomes interactive **only if** the content it is displaying **cannot fit entirely in the terminal screen**.
- In **interactive mode**, `more` allows you to press `v` to open the content in `vim`.
- `vim` can then be used to read files on the system — including the password file for the next level!

---

## 🪼 Step-by-Step Solution

### 1. **List the contents** of the home directory as `bandit25`

```bash
ls
```

You'll find the private key file:

```
bandit26.sshkey
```

---

### 2. **Download the SSH key to your own machine**

From your **local machine**, use `scp`:

```bash
scp -P 2220 bandit25@bandit.labs.overthewire.org:~/bandit26.sshkey .
```

Enter the password for `bandit25` when prompted.

---

### 3. **Set permissions on the key**

```bash
chmod 600 bandit26.sshkey
```

---

### 4. **Shrink your terminal vertically**  
Before you connect, make your terminal window very short (around **10 lines tall**) so `more` will go into **interactive mode**.

---

### 5. **SSH into bandit26 using the key**

```bash
ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
```

If your terminal is small enough, you will now see:

```
--More--
```

This means you are in `more`’s interactive mode ✅

---

### 6. **Press `v` to open Vim**

This will launch `vim`, allowing you to edit/view the `.bashrc` file.

---

### 7. **Open the password file in Vim**

Inside `vim`, press `:` to enter command mode, then type:

```vim
:e /etc/bandit_pass/bandit26
```

Press **Enter**.  
You will see the password for `bandit26` displayed on screen.

---

### 8. **Copy the password**  
Example:

```
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

---

### 9. **Login to Bandit Level 26**

```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220
```

Paste the password when prompted.

---

## ⚠️ Important Tips & Gotchas

- SSH from inside Bandit (`localhost`) is **blocked**. Always SSH from your **own machine**.
- `bandit26` uses a restricted shell (`/usr/bin/showtext`) that exits quickly — unless `more` enters interactive mode.
- You must **resize your terminal** window to **force interactive mode** in `more`.
- If `v` doesn’t work, or you don't see `--More--`, your terminal is too large.
- You can repeat the login without redownloading the key if you've saved it locally.

---
