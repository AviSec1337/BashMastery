# 🌟 CMD Challenge Solutions

This repository contains solutions to various command-line tasks from the [CMD Challenge](https://cmdchallenge.com/). Each challenge is designed to test and improve your shell scripting and command-line skills. Below is the list of challenges and their solutions with explanation, presented in a structured and easy-to-navigate format.

---

## Challenges and Solutions

---

### 1. **Hello World 🚀**
**Command:**
```bash
echo "hello world"
```
**Explanation:**
- `echo` is a command used to print text to the terminal.
- In this case, it simply prints the string `"hello world"` to the screen.

---

### 2. **Current Working Directory 📂**
**Command:**
```bash
pwd
```
**Explanation:**
- `pwd` stands for "print working directory".
- It displays the full path of the current directory you’re working in.

---

### 3. **List Files 📜**
**Command:**
```bash
ls -1
```
**Explanation:**
- `ls` lists files and directories in the current directory.
- The `-1` option ensures that the output is one file or directory per line.

---

### 4. **Last Lines 📖**
**Command:**
```bash
tail -5 access.log
```
**Explanation:**
- `tail` prints the last few lines of a file.
- The `-5` option specifies that only the last 5 lines of `access.log` should be displayed.

---

### 5. **Find String in a File 🔍**
**Command:**
```bash
grep GET access.log
```
**Explanation:**
- `grep` searches for a specific string or pattern in a file.
- Here, it looks for lines containing the string "GET" in `access.log` and prints those lines.

---

### 6. **Search for Files Containing String 🕵️**
**Command:**
```bash
grep -rl * -e 500
```
**Explanation:**
- `grep -r` searches for the string "500" in all files recursively starting from the current directory.
- The `-l` option lists only the names of files containing the string, not the matching lines.

---

### 7. **Search for Files by Extension 🗂️**
**Command:**
```bash
find . -name "access.log*"
```
**Explanation:**
- `find` searches for files and directories.
- `.` means start the search in the current directory.
- `-name "access.log*"` specifies the name pattern to look for (`access.log` or similar names).

---

### 8. **Search for String in Files Recursively 🔄**
**Command:**
```bash
find . -name "access.log*" | xargs grep -h 500
```
**Explanation:**
- `find . -name "access.log*"` locates files matching `access.log*`.
- `xargs` passes these files to `grep`.
- `grep -h 500` searches for "500" and suppresses file names in the output.

---

### 9. **Extract IP Addresses 🌐**
**Command:**
```bash
find . -name "access.log*" | xargs grep -Eo '^[^ ]+'
```
**Explanation:**
- `grep -Eo '^[^ ]+'` extracts the first word of each line (assumed to be an IP address).
- `^[^ ]+` matches characters from the start of the line until the first space.

---

### 10. **Delete Files ❌**
**Command:**
```bash
find . -delete
```
**Explanation:**
- `find .` finds all files and directories starting from the current directory.
- `-delete` removes them. Use cautiously as it deletes without confirmation.

---

### 11. **Count Files 🔢**
**Command:**
```bash
ls | wc -l
```
**Explanation:**
- `ls` lists files and directories.
- `wc -l` counts the number of lines in the output, which corresponds to the number of items.

---

### 12. **Simple Sort 🔀**
**Command:**
```bash
sort access.log
```
**Explanation:**
- `sort` arranges the lines of the file in ascending order (alphabetical or numerical).

---

### 13. **Count String in Line 🧮**
**Command:**
```bash
grep GET access.log | wc -l
```
**Explanation:**
- `grep GET access.log` finds lines containing "GET".
- `wc -l` counts the number of such lines.

---

### 14. **Split on a Character 🔡**
**Command:**
```bash
cat split-me.txt | sed s/\;/\n/g
```
**Explanation:**
- `sed s/\;/\n/g` replaces each `;` with a newline (`\n`).
- This splits numbers into separate lines.

---

### 15. **Print Number Sequence 📈**
**Command:**
```bash
echo {1..100}
```
**Explanation:**
- `{1..100}` generates a sequence of numbers from 1 to 100.
- `echo` prints them with spaces in between.

---

### 16. **Remove Files with Extension 🧹**
**Command:**
```bash
find . -name "*.doc" -delete
```
**Explanation:**
- `find . -name "*.doc"` locates `.doc` files.
- `-delete` removes them.

---

### 17. **Replace Text in Files ✍️**
**Command:**
```bash
find . -name "*.txt" -exec sed -i 's/challenges are difficult//g' {} +
```
**Explanation:**
- `sed -i` edits files in-place, removing the phrase.
- `{}` represents each file found, and `+` processes them in batches.

---
