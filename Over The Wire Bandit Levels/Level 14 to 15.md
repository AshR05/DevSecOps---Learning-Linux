# Level 14 to 15

**GOAL:**  
The password for the next level can be retrieved by submitting the password of the current level to port **30000** on **localhost**.

---

**Solution:**
- Based on the commands suggested that I may need to solve this level, I found out that `nc` is a command that allows to read and write data over a network connection
- Reading the manual page for `nc` I understood that `nc` can be used to connect to a specific port and send data

- I used the following command to send the password to port 30000:

```bash
  nc localhost 30000
```
- I entered the password for `bandit14` and hit Enter
- The service responded with the password for `bandit15`
<img width="2732" height="1730" alt="Level 14 to 15" src="https://github.com/user-attachments/assets/b98db797-d5b5-4a5b-862a-fbd87201d331" />
