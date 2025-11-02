# Level 7 to 8

**GOAL:**  
The password for the next level is stored in the file `data.txt` next to the word **millionth**.

---

**Solution:**

- I first ran `ls` to confirm the presence of `data.txt`.
- The hint suggested that I may need to use the 'grep' command, which searches for a specific pattern in files 
- The password for this level was stored next to the word 'millionth', therefore I used: 

```bash
grep "millionth" data.txt
```

This generated the password for level 8:

```bash
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

<img width="2736" height="1728" alt="Level 7 to 8" src="https://github.com/user-attachments/assets/7b892248-6239-442e-8ca2-337b43df15b3" />
