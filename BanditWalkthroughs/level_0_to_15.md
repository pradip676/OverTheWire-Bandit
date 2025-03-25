# Bandit Walkthrough: Levels 0 to 15

## **Level 0 → Level 1**
### **Task:**
Log into the Bandit server using SSH.
### **Commands Used:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
ls
cat readme
```
### **Retrieved Password:**
```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

---

## **Level 1 → Level 2**
### **Task:**
Retrieve the password stored in a plaintext file named `readme`.
### **Commands Used:**
```bash
ls
cat ./-
```
### **Retrieved Password:**
```
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

## **Level 2 → Level 3**
### **Task:**
Find the password stored in a file with a confusing name (`-`).
### **Commands Used:**
```bash
ls
cat "spaces in this filename"
```
```bash
you find level password here.
```

---

## **Level 3 → Level 4**
### **Task:**
Find the password in a file with spaces in its filename.
### **Commands Used:**
```bash
ls
cd inhere
ls -a
cat ...Hiding-From-You
```
### **Retrieved Password:**
```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

---

## **Level 4 → Level 5**
### **Task:**
Find the password hidden in a dotfile.
### **Commands Used:**
```bash
ls -a
cd inhere
file ./*
cat ./-file07
```
### **Retrieved Password:**
```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---

## **Level 5 → Level 6**
### **Task:**
Find a human-readable file among multiple files.
### **Commands Used:**
```bash
cd inhere
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```
### **Retrieved Password:**
```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

## **Level 6 → Level 7**
### **Task:**
Find a file based on user, group, and size.
### **Commands Used:**
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
### **Retrieved Password:**
```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

## **Level 7 → Level 8**
### **Task:**
Find a line containing the word `millionth` in a text file.
### **Commands Used:**
```bash
grep millionth data.txt
```
### **Retrieved Password:**
```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

## **Level 8 → Level 9**
### **Task:**
Identify a unique line in a large dataset.
### **Commands Used:**
```bash
sort data.txt | uniq -u
```
### **Retrieved Password:**
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

---

## **Level 9 → Level 10**
### **Task:**
Extract human-readable strings from a binary file.
### **Commands Used:**
```bash
strings data.txt | grep '=== '
```
### **Retrieved Password:**
```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

---

## **Level 10 → Level 11**
### **Task:**
Decode a base64-encoded password.
### **Commands Used:**
```bash
cat data.txt | base64 -d
```
### **Retrieved Password:**
```
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## **Level 11 → Level 12**
### **Task:**
Decrypt a ROT13-encoded password.
### **Commands Used:**
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
### **Retrieved Password:**
```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

---

## **Level 12 → Level 13**
### **Task:**
Extract a password from a compressed and encoded file.
### **Commands Used:**
```bash
mktemp -d
cp data.txt /tmp/
cd /tmp/
xxd -r data.txt > data.bin
file data.bin
mv data.bin data.dz2
gzip -d data.gz
file data.bin
ls
tar -xf data5.bin
ls
bzip2 -d data6.bin
tar -xf data6.bin.out
gzip -d data8.gz
ls
file data8
cat data8
```
### **Retrieved Password:**
```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

---

## **Level 13 → Level 14**
### **Task:**
Use an SSH private key to log in.
### **Commands Used:**
```bash
ls
ssh -i sshkey.private bandit14@localhost -p 2220
cat /etc/bandit_pass/bandit14
```
### **Retrieved Password:**
```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

---

## **Level 14 → Level 15**
### **Task:**
Send a password to an open port using netcat.
### **Commands Used:**
```bash
nc localhost 3000
paste password from previous level(MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS)
```
### **Retrieved Password:**
```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

## **Level 15 → Level 16**
### **Task:**
Use OpenSSL to establish a secure connection and retrieve the password.
### **Commands Used:**
```bash
openssl s_client -connect localhost:30001
paste password from previous level(8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo)
```
### **Retrieved Password:**
```
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

