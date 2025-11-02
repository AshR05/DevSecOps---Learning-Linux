# Level 4 to 5

**Goal:**  
The password for the next level is stored in the only human-readable file in the `inhere` directory.  
*Tip: if your terminal is messed up, try the `reset` command.*

---

**Solution:**

- I ran:
```bash
ls
```
This was to see the 'inhere' directory, followed by changing the directory to inhere and listing the contents of this directory
```bash
  cd inhere/
  ls
```
There are 10 files named `-file00` through `-file09`.

It is possible to concatenate (`cat`) the contents of every file; however, this isn't efficient when dealing with multiple files.

The command `file <filename>` identifies the type of data in the file. 


I remembered from Level 1 to 2 that filenames starting with `-` can confuse commands by being interpreted as options. So when I used the `file` command, I made sure to prefix them with `./`:

```bash
file ./*
```
The `*` is known as a 'wildcard symbol' in which the `*` can stand for any characters. 
This generated:

```bash
./-file07: ASCII text
```

This told me that `-file07` is the only file containing readable text.

I used the `./-file07` to safely `cat` the contents to obtain the password:

```bash
cat ./-file07
```
<img width="2736" height="1726" alt="Level 4 to 5" src="https://github.com/user-attachments/assets/d3ad3500-053e-4265-b932-f7aa065eda2c" />

