# Level 8 to 9

**GOAL:**  
The password for the next level is stored in the file `data.txt` and is the only line of text that occurs **only once**.

---

**Solution:**

- The 'uniq' command filters out the repeated lines in a file. Looking at the 'man uniq' and 'man sort' page`uniq -u` prints unique lines but requires **sorted input**, hence why this command is often used with `sort`.

- I ran and obtained the password:

```bash
  sort data.txt | uniq -u
```

<img width="2736" height="1722" alt="Level 8 to 9" src="https://github.com/user-attachments/assets/89d84b41-2514-435c-89cc-75571be0da3d" />
