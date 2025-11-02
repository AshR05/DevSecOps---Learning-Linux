# Level 10 to 11

**GOAL:**  
The password for the next level is stored in the file `data.txt`, which contains **base64 encoded** data.

---

**Solution**

- Ran `ls` to confirm the file was there:

```bash
  ls
```

Used `cat` to look at the file contents:

```bash
cat data.txt
```

The `base64` command allows files as input, so I just need to use the command on the file to obtain the password:

```bash
base64 -d data.txt
```

<img width="2726" height="1730" alt="Level 10 to 11" src="https://github.com/user-attachments/assets/f3940653-04e7-4e4a-9a32-bd3ba77b94de" />
