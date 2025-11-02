# Level 12 to 13

**GOAL:**  
The password for the next level is stored in the file `data.txt`, which is a **hexdump** of a file that has been **repeatedly compressed**.  
*Tip:* It may be useful to create a directory under `/tmp` in which you can work. Use `mkdir` with a hard-to-guess directory name, or better, use the command `mktemp -d`.

---

**Solution:**

#### Create a directory and move the file
- Created a safe temporary working directory using `mktemp` and changed my directory to the temporary working directory:

  ```bash
  mktemp -d
  cd /tmp/tmp.XXXXXXX
```
Copied `data.txt` to that directory:

```bash
cp ~/data.txt .
```
- I ran `ls` to double-check that this worked

- I renamed `data.txt` to `hexdump_data`
```bash
mv data.txt hexdump_data
```

#### Convert the hexdump data file

- Converted the hexdump back into binary using `xxd -r`:

```bash
xxd -r hexdump_data compressed_data
```
#### Repeatedly decompress

- I ran the `file` command on both 'hexdump_data' and 'compressed_data' to identify the file type to determine the compression format:
```bash
file hexdump_data
file compressed_data
```
-  Renamed the file with the correct extension based on the file output. In this case, it was a gzip archive:
```bash
mv compressed_data compressed_data.gz
```
- However, the data is still not fully decompressed; therefore, we decompress the file with the appropriate tool (repeated multiple times):
```bash
gzip -d compressed_data.gz
bzip -d compressed_data.bz2
tar -xf compressed_data.tar
```
- The command `tar` creates archive files and `xf` extracts an archive file
- After every decompression, I used:

```bash
file <filename>
```
- To check the new file type and continue accordingly.

- Repeated this process through multiple layers until I reached a readable file to obtain the password:
```bash
cat data8
```
<img width="2732" height="1676" alt="Level 12 to 13_1" src="https://github.com/user-attachments/assets/cf3181a1-30a8-4eb0-9889-323f31f40eaf" />
<img width="2728" height="1732" alt="Level 12 to 13_2" src="https://github.com/user-attachments/assets/d3982291-1334-4b21-9fb2-4f7b26ee9311" />
<img width="2736" height="1726" alt="Level 12 to 13_3" src="https://github.com/user-attachments/assets/f6c52459-9c37-4c74-bbc5-936f2c40cb25" />
