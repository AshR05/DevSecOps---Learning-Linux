# Level 11 to 12

**GOAL:**  
The password for the next level is stored in the file `data.txt`, where all lowercase (`a-z`) and uppercase (`A-Z`) letters have been rotated by 13 positions.

---

**Solution:**

- I ran `ls` to find `data.txt`:

```bash
  ls
data.txt
```

Checked the contents of the file:

```bash
  cat data.txt
```

The content was readable but looked like ROT13 encoded text, as hinted in the task.

Rotating letters by 13 positions is the ROT13 substitution cypher.


The `tr` command, which stands for' translate', was used to decode ROT13 by translating letters, which allowed me to obtain the password:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
<img width="2736" height="1728" alt="Level 11 to 12" src="https://github.com/user-attachments/assets/d040c1d0-3122-4d41-b83c-3ec481b86fc6" />
