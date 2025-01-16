---

## 🌟 CMD Challenge Solutions

This repository contains solutions to various command-line tasks from the [CMD Challenge](https://cmdchallenge.com/). Each challenge is designed to test and improve your shell scripting and command-line skills. Below is the list of challenges and their solutions, with detailed explanations.

---

### 1. **Hello World 🚀**
**Task:** Print "hello world".  
**Solution:**
```bash
echo "hello world"
```

---

### 2. **Current Working Directory 📂**
**Task:** Print the current working directory.  
**Solution:**
```bash
pwd
```

---

### 3. **List Files 📜**
**Task:** List all of the files in the current directory, one file per line.  
**Solution:**
```bash
ls -1
```

---

### 4. **Last Lines 📖**
**Task:** Print the last 5 lines of `access.log`.  
**Solution:**
```bash
tail -5 access.log
```

---

### 5. **Find String in a File 🔍**
**Task:** Print all lines in `access.log` that contain the string "GET".  
**Solution:**
```bash
grep GET access.log
```

---

### 6. **Search for Files Containing String 🕵️**
**Task:** Print all files, one per line, that contain the string "500".  
**Solution:**
```bash
grep -rl * -e 500
```

---

### 7. **Search for Files by Extension 🗂️**
**Task:** Print the relative file paths for all files that start with `access.log`.  
**Solution:**
```bash
find . -name "access.log*"
```

---

### 8. **Search for String in Files Recursively 🔄**
**Task:** Print all matching lines (without the filename or file path) in files starting with `access.log` and containing the string "500".  
**Solution:**
```bash
find . -name "access.log*" | xargs grep -h 500
```

---

### 9. **Extract IP Addresses 🌐**
**Task:** Extract all IP addresses from files that start with `access.log`, printing one per line.  
**Solution:**
```bash
find . -name "access.log*" | xargs grep -Eo '^[^ ]+'
```

---

### 10. **Delete Files ❌**
**Task:** Delete all files in the current directory, including subdirectories and their contents.  
**Solution:**
```bash
find . -delete
```

---

### 11. **Count Files 🔢**
**Task:** Count the number of files in the current working directory.  
**Solution:**
```bash
ls | wc -l
```

---

### 12. **Simple Sort 🔀**
**Task:** Print the contents of `access.log` sorted.  
**Solution:**
```bash
sort access.log
```

---

### 13. **Count String in Line 🧮**
**Task:** Print the number of lines in `access.log` containing the string "GET".  
**Solution:**
```bash
grep GET access.log | wc -l
```

---

### 14. **Split on a Character 🔡**
**Task:** Split the numbers in `split-me.txt` on the `;` character, printing one per line.  
**Solution:**
```bash
cat split-me.txt | sed 's/;/\n/g'
```

---

### 15. **Print Number Sequence 📈**
**Task:** Print the numbers 1 to 100 separated by spaces.  
**Solution:**
```bash
echo {1..100}
```

---

### 16. **Remove Files with Extension 🧹**
**Task:** Remove all `.doc` files recursively in the current directory.  
**Solution:**
```bash
find . -name "*.doc" -delete
```

---

### 17. **Replace Text in Files ✍️**
**Task:** Delete "challenges are difficult" from all `.txt` files.  
**Solution:**
```bash
find . -name "*.txt" -exec sed -i 's/challenges are difficult//g' {} +
```

---

### 18. **Sum All Numbers ➕**
**Task:** Print the sum of numbers in `sum-me.txt`.  
**Solution:**
```bash
cat sum-me.txt | xargs | sed 's/ /+/g' | bc
```

---

### 19. **Just the Files 📁**
**Task:** Print all files in the current directory recursively without leading paths.  
**Solution:**
```bash
find . -type f -printf "%f\n"
```

---

### 20. **Remove Extensions from Files 🛠️**
**Task:** Remove file extensions recursively.  
**Solution:**
```bash
find `pwd` -type f -exec bash -c 'mv "$1" "${1%.*}"' - '{}' \;
```

---

### 21. **Replace Spaces in Filenames 🌌**
**Task:** Replace spaces in filenames with a `.` character.  
**Solution:**
```bash
find . -type f -name "* *" | while read -r file; do mv "$file" "${file// /_}"; done
```

---

### 22. **Files Starting with a Number 🔢**
**Task:** Print filenames starting with a number.  
**Solution:**
```bash
find . -name '[0-9]*' -type f -printf "%f\n"
```

---

### 23. **Print Nth Line 📜**
**Task:** Print the 25th line of `faces.txt`.  
**Solution:**
```bash
sed '25q;d' faces.txt
```

---

### 24. **Remove Duplicate Lines ♻️**
**Task:** Print `faces.txt` with only the first instance of each duplicate line.  
**Solution:**
```bash
awk '!seen[$0]++' faces.txt
```

---

### 25. **Corrupted Text 🛠️**
**Task:** Remove random `!` marks from `war_and_peace.txt` to restore the original text.  
**Solution:**
```bash
< war_and_peace.txt tr -s '!' | sed 's/!\([a-z]\)/\1/g' | sed 's/!\( [a-z]\)/\1/g' | sed 's/!\.\!/./g' | sed 's/ !/ /g'
```

---

### 26. **Print Hello World (Alternate) 🚀**
**Task:** Print "Hello World" using escaped space.  
**Solution:**
```bash
echo hello\ world
```

---

### 27. **Count Tab Characters 📂**
**Task:** Count lines containing tab characters in `file-with-tabs.txt`.  
**Solution:**
```bash
grep -c $'	' ./file-with-tabs.txt
```

---

### 28. **Remove Files Starting with Dash 🗑️**
**Task:** Remove files starting with a dash in the filename.  
**Solution:**
```bash
find . -name '-*' -delete
```

---

### 29. **Remove Files without Specific Extensions ❌**
**Task:** Remove all files without `.txt` and `.exe` extensions recursively.  
**Solution:**
```bash
find . -type f -not \( -name '*.txt' -or -name '*.exe' \) -delete
```

---

### 30. **Common IPs in Logs 🌐**
**Task:** Print IP addresses common to `access.log.1` and `access.log.2`.  
**Solution:**
```bash
comm -12 <(cut -d' ' -f1 access.log.1 | sort) <(cut -d' ' -f1 access.log.2 | sort)
```

---

### 31. **Reverse Lines 🔄**
**Task:** Print the lines of the file `reverse-me.txt` in reverse order so that the last line appears first.  
**Solution:**
```bash
tac reverse-me.txt
```

---

### 32. **Unique Primes 🔢**
**Task:** Print the number of unique prime numbers in `random-numbers.txt`.  
**Solution:**
```bash
cat random-numbers.txt | sort | uniq | factor | awk 'NF==2' | wc -l
```

---

### 33. **Find Ports in Netstat 🌐**
**Task:** Print all IPv4 listening ports from `netstat.out`, sorted in descending order.  
**Solution:**
```bash
grep '\bLISTEN\b' netstat.out | grep -oP 'tcp\s+.*:\K\d+' | sort -nr
```

---
