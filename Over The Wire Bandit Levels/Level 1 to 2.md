# Level 1 > 2

**GOAL:**  
The password for the next level is stored in a file called `-` located in the home directory.

---
**Solution:**

1. I first ran `ls` to see the files in the home directory and found a file named `-`.
2. Initially, I tried reading it using `cat -`, but I realised this didn’t work as expected because `-` is interpreted as stdin (standard input).
3. I checked the `man cat` page and learned that using `-` tells `cat` to read from standard input, not from a file literally named `-`.
4. To read the file named `-`, I used `./-`, which treats it as a file in the current directory and avoids confusion with stdin. 
<img width="2736" height="1732" alt="Level 1 to 2" src="https://github.com/user-attachments/assets/0a3d2e17-2f42-4e86-abe6-d5ff86f8054c" />
