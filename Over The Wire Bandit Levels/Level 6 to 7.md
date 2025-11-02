# Level 6 to 7

**GOAL:**  
The password for the next level is stored somewhere on the server and has all of the following properties:

- owned by user `bandit7`  
- owned by group `bandit6`  
- 33 bytes in size

---

**Solution:**

- At first, I ran:

```bash
  find / -type f -size 33c -user bandit7 -group bandit6
```
This worked, but showed a lot of Permission denied messages.

To make the output cleaner, I redirected errors to `/dev/null`:

```bash
find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
```

That gave me the correct file:

```bash
/var/lib/dpkg/info/bandit7.password
```

Then I used cat to read its contents to obtain the password:

```bash
cat /var/lib/dpkg/info/bandit7.password
```
<img width="2736" height="1730" alt="Level 6 to 7_2" src="https://github.com/user-attachments/assets/566dca99-bb43-4c77-9de2-055177dc4ff4" />

