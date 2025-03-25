# Bandit Walkthrough: Levels 16 to 21

## **Bandit Level 16 → Level 17**

### **Task:**
Find an open port in the range 31000-32000 and submit the Bandit16 password to retrieve the next password.

### **Commands Used:**
1. **Scan for open ports:**
   ```bash
   nmap -p 31000-32000 localhost
   ```
2. **Check if the port supports SSL/TLS:**
   ```bash
   openssl s_client -connect localhost:<PORT>
   ```
3. **Send the password to the correct port:**
   ```bash
   echo "<BANDIT16_PASSWORD>" | nc localhost <PORT>
   ```

### **Password for Level 17:**
```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```

---

## **Bandit Level 17 → Level 18**

### **Task:**
Compare the contents of `passwords.old` and `passwords.new` to identify the modified line.

### **Commands Used:**
1. **Find differences between the files:**
   ```bash
   diff passwords.old passwords.new
   ```

### **Password for Level 18:**
```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

---

## **Bandit Level 18 → Level 19**

### **Task:**
Read the password stored in `/etc/bandit_pass/bandit19`.

### **Commands Used:**
1. **Read the password file:**
   ```bash
   cat /etc/bandit_pass/bandit19
   ```

### **Password for Level 19:**
```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

---

## **Bandit Level 19 → Level 20**

### **Task:**
Use the `bandit20-do` SetUID binary to execute a command as Bandit20 and access the password file.

### **Commands Used:**
1. **Run the binary to read the password:**
   ```bash
   ./bandit20-do cat /etc/bandit_pass/bandit20
   ```

### **Password for Level 20:**
```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

---

## **Bandit Level 20 → Level 21**

### **Task:**
Use the `suconnect` binary to establish a connection to localhost, send the Bandit20 password, and receive the next password.

### **Commands Used:**
1. **Start a listener on a specified port:**
   ```bash
   nc -lvp 12345
   ```
2. **Run the binary to connect to the port:**
   ```bash
   ./suconnect 12345
   ```
3. **Enter the Bandit20 password:**
   ```bash
   0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
   ```

### **Password for Level 21:**
```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

---

