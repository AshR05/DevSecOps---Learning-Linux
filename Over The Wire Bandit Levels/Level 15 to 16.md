# Level 15 to 16

**GOAL:**  
The password for the next level can be retrieved by submitting the password of the current level to port **30001** on **localhost** using **SSL/TLS encryption**.

---

**Solution:**
- The task stated that the password can be obtained using the SSL encryption
- Therefore, I connected to the localhost server with the `openssl` command, as this is useful for encrypted connections
- I used the `openssl` command with `s_client` to initiate an SSL connection to port 30001 on localhost:

```bash
  openssl s_client -connect localhost:30001
```

<img width="2736" height="1722" alt="Level 15 to 16_1" src="https://github.com/user-attachments/assets/c664bc5e-6f02-4db6-8503-8c85edcefab7" />

- Once the SSL connection was established, I entered the password for `bandit15`

- The server then sends back the password for the next level:

<img width="2736" height="1732" alt="Level 15 to 16_2" src="https://github.com/user-attachments/assets/b9599efc-fcd0-444c-bbe4-145762765133" />
