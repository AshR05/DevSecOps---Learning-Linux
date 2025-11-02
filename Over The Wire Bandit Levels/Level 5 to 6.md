# Level 5 to 6

**GOAL:**  
The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:

- human-readable  
- 1033 bytes in size  
- not executable

---

**Solution:**

- I used the `find` command to search for files of exactly 1033 bytes:

```bash
  find -type f -size 1033c
```

This generated:

```bash
./maybehere07/.file2
```
I read the file contents and obtained the password:

```bash
cat maybehere07/.file2
```
<img width="2730" height="1732" alt="Level 5 to 6" src="https://github.com/user-attachments/assets/d488ab9a-479f-44e9-b3e4-c35550e5d084" />
