# Level 9 to 10

**GOAL:**  
The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters.

---
**Solution:**

- Ran `ls` to see the file `data.txt`:

```bash
  ls
data.txt
```

The `strings` command finds human-readable strings in files. Specifically, it prints sequences of printable characters.

To distinguish human-readable strings in ‘data.txt’. I used the `strings` command.

To filter that output by looking at lines that include more than one equal sign, the `grep` command can be used again. 

The task did not specify the number of equal signs; therefore, I used 3.

I ran the following command to obtain the password :

```bash
strings data.txt | grep ===
```

<img width="2736" height="1724" alt="Level 9 to 10" src="https://github.com/user-attachments/assets/0e4ed5d4-73e2-47b2-b175-609e3bc206d7" />
