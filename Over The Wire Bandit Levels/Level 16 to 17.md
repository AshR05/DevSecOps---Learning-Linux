# Level 16 to 17

**GOAL:**  
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range **31000 to 32000**.  
First, find out which of these ports have a server listening on them. Then determine which of those use **SSL/TLS**.  
There is only one server that will return the next credentials — others just echo your input.

---

**Solution:**
- Unlike previous levels, this task required scanning for open ports in a specific range and detecting SSL/TLS services
- `nmap` is a network scanner, and I used this command to scan for open ports on localhost in the 31000–32000 range:

  ```bash
  nmap -sV -T4 localhost -p 31000-32000

- The `-sV` flag allows us to do a service/version detection scan
- The `-T4` flag is used to increase the speed of the scan
- Five ports were identified that were open and accepting connections. However, only two ports (31518 and 31790) use SSL
- Interestingly, port 31790 runs an unknown service  


<img width="2734" height="1722" alt="Level 16 to 17_1" src="https://github.com/user-attachments/assets/93fa2846-86e9-43b8-bdcc-f69fe6543cbc" />



- I used OpenSSL again to connect to this port on localhost and send the password:

```bash
openssl s_client -connect localhost:31790
```

<img width="2734" height="1728" alt="Level 16 to 17_2" src="https://github.com/user-attachments/assets/ae06ee8f-dbde-4b63-87b6-1e8dc4bede8a" />



- Once connected, I pasted the current level's password. However, it only returned a single message `KEYUPDATE`, and nothing else
- That felt suspicious because the wargame description stated: "There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it."
So I retried the same command, but this time I added the `-ign_eof` option, which allows you to keep reading input even after the server disconnects:

```bash
openssl s_client -connect localhost:31790 -ign_eof
```


<img width="2736" height="1734" alt="Level 16 to 17_3" src="https://github.com/user-attachments/assets/129c5dda-62d0-4c54-bd2e-3cbacf0a993b" />


- The server responded with an RSA private key


<img width="2716" height="1730" alt="Level 16 to 17_4" src="https://github.com/user-attachments/assets/7591317b-97c4-4b34-9190-3c7f9825a464" />

- I saved the key as `private.key` inside the `/tmp/b17key` directory
- Changed the permission of the file and retried the SSH login, and it worked!:

```bash
mkdir /tmp/b17key
cd /tmp/b17key/
touch private.key
vim private.key
chmod 400 private.key
ssh-i private.key bandit17@bandit.labs.overthewire.org -p 2220
```




