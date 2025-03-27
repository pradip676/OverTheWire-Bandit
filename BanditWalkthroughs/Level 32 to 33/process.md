# OverTheWire Bandit: Level 32 → Level 33 Walkthrough

## 🔐 Password for bandit32:
```
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

---

## 📂 Level Goal

> After all this git stuff, it’s time for another escape. Good luck!

You are now placed in a restricted environment called the **Uppercase Shell** that blocks typical lowercase Linux commands by automatically converting everything to uppercase.

---

## 🚀 Solution

### ✅ Step 1: Log in to Bandit32
```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```
Password:
```
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

You will see:
```
WELCOME TO THE UPPERCASE SHELL
>>
```

### ✅ Step 2: Attempt normal commands
```bash
>> ls
sh: 1: LS: Permission denied
>> echo Hello
sh: 1: ECHO: Permission denied
```

Since the shell capitalizes all commands, common commands are blocked. Even full paths like `/bin/sh` become `/BIN/SH` and fail.

---

### ✨ Trick: Use `$0` to escape the shell
```bash
>> $0
$ echo $0
sh
```

Typing `$0` spawns a new unrestricted shell because it represents the current shell and bypasses the uppercase transformation.

Now you have a working shell.

---

### ✅ Step 3: Check user identity and access
```bash
$ whoami
bandit33
$ id
uid=11033(bandit33) gid=11032(bandit32) groups=11032(bandit32)
```

Since the shell was a SUID binary owned by `bandit33`, you now have `bandit33`'s privileges.

---

### ✅ Step 4: Read the final password
```bash
$ cat /etc/bandit_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

---

## 🔐 Final Password for Bandit33
```
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

---


