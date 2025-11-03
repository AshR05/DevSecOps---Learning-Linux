# Level 13 to 14

**GOAL:**  
The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user **bandit14**.  
For this level, you don’t get the next password directly, but you receive a **private SSH key** that can be used to log into the next level.  
*Note:* `localhost` refers to the machine you are working on.

---

**Solution:**

- Listed the contents of the home directory:

```bash
  ls
```

- Found the private key file in the home directory:

```bash
  sshkey.private
```

- Knowing the location of the file, I can transfer it to my machine

- The `scp` command which uses the SSH to transfer data over the network. I used the `scp` to connect to the remote machine and obtain the ssh key

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```
- I tried to login with the private ssh key however, I did not have the appropriate permission (not shown) 
- Therefore, I changed the permission so that I could have permission to use the file:

  ```bash
  chmod 700 sshkey.private
  ```

Used the SSH key to log in as `bandit14` on port `2220`:

```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Once logged in as `bandit14`, I read the file where the password was stored to obtain the password for level 14:
```bash
cat /etc/bandit_pass/bandit14
```
<img width="2736" height="1720" alt="Level 13 to 14_1" src="https://github.com/user-attachments/assets/4a8eee09-c230-40a5-b9a4-446814662d9d" />
<img width="2734" height="1726" alt="Level 13 to 14_2" src="https://github.com/user-attachments/assets/6f3f9912-95b9-4688-89a2-1d9a57eb750d" />
