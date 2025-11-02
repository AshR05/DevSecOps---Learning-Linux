# Level 2 to 3  
**GOAL:** Find the password for the next level stored in a file called `spaces in this filename`.

**Solution**  
I started by running `ls` to list the files in the home directory and saw a file named `spaces in this filename`.
- I knew that spaces in filenames can cause issues if not handled properly in the shell. 
To solve this, I used quotes to treat the entire filename as a single argument:

```bash
cat "spaces in this filename"
```
Alternatively, escaping the spaces with backslashes also works:

```bash
cat spaces\ in\ this\ filename
```
<img width="722" height="456" alt="Level 2 to 3" src="https://github.com/user-attachments/assets/8632a649-98d4-4fc4-979b-702f851be9e0" />
