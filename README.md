---

## 🌟 CMD Challenge Solutions with Detailed Explanations

This repository contains solutions to various command-line tasks from the [CMD Challenge](https://cmdchallenge.com/). Each challenge is designed to test and improve your shell scripting and command-line skills. Below is the list of challenges and their solutions, along with detailed explanations to help beginners understand the concepts.

---

### 1. **Hello World 🚀**
**Task:** Print "hello world".  
**Solution:**
```bash
echo "hello world"
```
**Explanation:**
- `echo` is a command used to display text or strings on the terminal.
- By typing `echo "hello world"`, the shell will output the text `hello world` to the screen.

---

### 2. **Current Working Directory 📂**
**Task:** Print the current working directory.  
**Solution:**
```bash
pwd
```
**Explanation:**
- `pwd` stands for "print working directory."
- This command displays the full path of the directory you are currently in.

---

### 3. **List Files 📜**
**Task:** List all of the files in the current directory, one file per line.  
**Solution:**
```bash
ls -1
```
**Explanation:**
- `ls` lists files and directories in the current directory.
- The `-1` option ensures that each file is displayed on a separate line.

---

### 4. **Last Lines 📖**
**Task:** Print the last 5 lines of `access.log`.  
**Solution:**
```bash
tail -5 access.log
```
**Explanation:**
- `tail` displays the last part of a file.
- The `-5` option tells `tail` to show the last 5 lines of the file `access.log`.

---

### 5. **Find String in a File 🔍**
**Task:** Print all lines in `access.log` that contain the string "GET".  
**Solution:**
```bash
grep GET access.log
```
**Explanation:**
- `grep` searches for a specific pattern in a file.
- Here, it searches for the word `GET` in the file `access.log` and prints all matching lines.

---

### 6. **Search for Files Containing String 🕵️**
**Task:** Print all files, one per line, that contain the string "500".  
**Solution:**
```bash
grep -rl * -e 500
```
**Explanation:**
- `grep` searches files for a given pattern.
- `-r` means recursive, so it searches in the current directory and all subdirectories.
- `-l` means it only prints the names of files containing the match, not the matching lines.
- `*` searches all files in the current directory.
- `-e 500` specifies the string `500` to search for.

---

### 7. **Search for Files by Extension 📂**
**Task:** Print the relative file paths for all files that start with `access.log`.  
**Solution:**
```bash
find . -name "access.log*"
```
**Explanation:**
- `find` searches for files and directories.
- `.` specifies the current directory.
- `-name` tells `find` to look for files matching a specific name pattern.
- `"access.log*"` matches any file name starting with `access.log`.

---

### 8. **Search for String in Files Recursively 🔄**
**Task:** Print all matching lines (without the filename or file path) in files starting with `access.log` and containing the string "500".  
**Solution:**
```bash
find . -name "access.log*" | xargs grep -h 500
```
**Explanation:**
- `find . -name "access.log*"` finds all files starting with `access.log`.
- The `|` symbol pipes the output of `find` into the next command.
- `xargs` passes the file names to `grep`.
- `grep -h` searches for `500` but hides file names from the output.

---

### 9. **Extract IP Addresses 🌐**
**Task:** Extract all IP addresses from files that start with `access.log`, printing one per line.  
**Solution:**
```bash
find . -name "access.log*" | xargs grep -Eo '^[^ ]+'
```
**Explanation:**
- `find . -name "access.log*"` finds files starting with `access.log`.
- `xargs` passes the file names to `grep`.
- `grep -Eo '^[^ ]+'` extracts patterns using regular expressions:
  - `-E` enables extended regular expressions.
  - `-o` prints only the matching part of the line.
  - `'^[^ ]+'` matches the beginning of a line until the first space, which is often the IP address in logs.

---

### 10. **Delete Files ❌**
**Task:** Delete all files in the current directory, including subdirectories and their contents.  
**Solution:**
```bash
find . -delete
```
**Explanation:**
- `find .` searches in the current directory and all subdirectories.
- `-delete` removes the files and directories found by `find`.
**Note:** Be very careful when using this command as it will delete everything in the specified directory!

---

### 11. **Count Files 🔢**
**Task:** Count the number of files in the current working directory.  
**Solution:**
```bash
ls | wc -l
```
**Explanation:**
- `ls` lists files in the current directory.
- The `|` passes the output of `ls` to `wc` (word count).
- `wc -l` counts the number of lines, which equals the number of files.

---

### 12. **Simple Sort 🔀**
**Task:** Print the contents of `access.log` sorted.  
**Solution:**
```bash
sort access.log
```
**Explanation:**
- `sort` arranges the lines of a file in alphabetical or numerical order by default.
- Here, it sorts the lines in `access.log`.

---

### 13. **Count String in Line 🧴**
**Task:** Print the number of lines in `access.log` containing the string "GET".  
**Solution:**
```bash
grep GET access.log | wc -l
```
**Explanation:**
- `grep GET access.log` finds all lines containing `GET`.
- The `|` passes these lines to `wc -l`.
- `wc -l` counts the number of matching lines.

---

### 14. **Split on a Character 🛁**
**Task:** Split the numbers in `split-me.txt` on the `;` character, printing one per line.  
**Solution:**
```bash
cat split-me.txt | sed 's/;/
/g'
```
**Explanation:**
- `cat split-me.txt` outputs the content of the file `split-me.txt`.
- `|` pipes the output to `sed`.
- `sed 's/;/
/g'` replaces each semicolon (`;`) with a newline character (`
`), printing each number on a new line.

---

### 15. **Print Number Sequence 📈**
**Task:** Print the numbers 1 to 100 separated by spaces.  
**Solution:**
```bash
echo {1..100}
```
**Explanation:**
- `echo` outputs text to the terminal.
- `{1..100}` is a sequence expression that generates numbers from 1 to 100.
- This prints all numbers in a single line, separated by spaces.

---

### 16. **Remove Files with Extension 🧹**
**Task:** Remove all `.doc` files recursively in the current directory.  
**Solution:**
```bash
find . -name "*.doc" -delete
```
**Explanation:**
- `find . -name "*.doc"` searches for files ending with `.doc`.
- `-delete` removes these files.

---

### 17. **Replace Text in Files ✍️**
**Task:** Delete "challenges are difficult" from all `.txt` files.  
**Solution:**
```bash
find . -name "*.txt" -exec sed -i 's/challenges are difficult//g' {} +
```
**Explanation:**
- `find . -name "*.txt"` locates all `.txt` files.
- `-exec` runs a command on each file found.
- `sed -i 's/challenges are difficult//g'` removes the text "challenges are difficult" from each file in place (`-i`).

---

### 18. **Sum All Numbers ➕**
**Task:** Print the sum of numbers in `sum-me.txt`.  
**Solution:**
```bash
cat sum-me.txt | xargs | sed 's/ /+/g' | bc
```
**Explanation:**
- `cat sum-me.txt` outputs the file's content.
- `xargs` joins all numbers into a single line.
- `sed 's/ /+/g'` replaces spaces between numbers with `+` signs to form a mathematical expression.
- `bc` evaluates the expression and prints the result.

---

### 19. **Just the Files 📁**
**Task:** Print all files in the current directory recursively without leading paths.  
**Solution:**
```bash
find . -type f -printf "%f\n"
```
**Explanation:**
- `find .` searches the current directory and subdirectories.
- `-type f` restricts the search to files (not directories).
- `-printf "%f\n"` prints only the filenames without their paths.

---

### 20. **Remove Extensions from Files 🛠️**
**Task:** Remove file extensions recursively.  
**Solution:**
```bash
find . -type f -exec bash -c 'mv "$1" "${1%.*}"' - '{}' \;
```
**Explanation:**
- `find . -type f` finds all files in the current directory and subdirectories.
- `-exec bash -c` runs a custom bash command for each file.
- `mv "$1" "${1%.*}"` renames the file by removing everything after the last `.` (dot), which is the file extension.

---

### 21. **Replace Spaces in Filenames 🌌**
**Task:** Replace spaces in filenames with a `.` character.  
**Solution:**
```bash
find . -type f -name "* *" | while read -r file; do mv "$file" "${file// /_}"; done
```
**Explanation:**
- `find . -type f -name "* *"` finds files with spaces in their names.
- The `|` pipes the list of filenames to a `while` loop.
- `mv "$file" "${file// /_}"` renames each file by replacing spaces with underscores (`_`).

---

### 22. **Files Starting with a Number 🔢**
**Task:** Print filenames starting with a number.  
**Solution:**
```bash
find . -name '[0-9]*' -type f -printf "%f\n"
```
**Explanation:**
- `find . -name '[0-9]*'` searches for files whose names start with a digit.
- `-type f` ensures only files are included.
- `-printf "%f\n"` prints only the filenames.

---

### 23. **Print Nth Line 📜**
**Task:** Print the 25th line of `faces.txt`.  
**Solution:**
```bash
sed '25q;d' faces.txt
```
**Explanation:**
- `sed` is used to process and transform text in a file.
- `'25q;d'` tells `sed` to quit (`q`) after reading 25 lines, and delete (`d`) all but the 25th line.

---

### 24. **Remove Duplicate Lines ♻️**
**Task:** Print `faces.txt` with only the first instance of each duplicate line.  
**Solution:**
```bash
awk '!seen[$0]++' faces.txt
```
**Explanation:**
- `awk` processes text line by line.
- `!seen[$0]++` ensures each line is printed only the first time it is encountered.

---

### 25. **Corrupted Text 🛠️**
**Task:** Remove random `!` marks from `war_and_peace.txt` to restore the original text.  
**Solution:**
```bash
< war_and_peace.txt tr -s '!' | sed 's/!//g'
```
**Explanation:**
- `tr -s '!'` squeezes multiple `!` into a single one.
- `sed 's/!//g'` removes all remaining `!` characters.

---

### 26. **Print Hello World (Alternate) 🚀**
**Task:** Print "Hello World" using escaped space.  
**Solution:**
```bash
echo hello\ world
```
**Explanation:**
- `hello\ world` escapes the space with a `\`, ensuring the two words are treated as part of the same string.

---

### 27. **Count Tab Characters 📂**
**Task:** Count lines containing tab characters in `file-with-tabs.txt`.  
**Solution:**
```bash
grep -c $'\t' file-with-tabs.txt
```
**Explanation:**
- `grep -c` counts the number of matching lines.
- `$'\t'` matches tab characters.

---

### 28. **Remove Files Starting with Dash 🗑️**
**Task:** Remove files starting with a dash in the filename.  
**Solution:**
```bash
find . -name '-*' -delete
```
**Explanation:**
- `find . -name '-*'` searches for files starting with a dash (`-`).
- `-delete` removes those files.

---

### 29. **Remove Files without Specific Extensions ❌**
**Task:** Remove all files without `.txt` and `.exe` extensions recursively.  
**Solution:**
```bash
find . -type f -not \( -name '*.txt' -or -name '*.exe' \) -delete
```
**Explanation:**
- `find . -type f` finds all files.
- `-not \( -name '*.txt' -or -name '*.exe' \)` excludes `.txt` and `.exe` files.
- `-delete` removes all other files.

---

### 30. **Common IPs in Logs 🌐**
**Task:** Print IP addresses common to `access.log.1` and `access.log.2`.  
**Solution:**
```bash
comm -12 <(cut -d' ' -f1 access.log.1 | sort) <(cut -d' ' -f1 access.log.2 | sort)
```
**Explanation:**
- `cut -d' ' -f1` extracts the first column (IP addresses) from each file.
- `sort` arranges the IPs in order.
- `comm -12` finds common lines between the two sorted files.

---

### 31. **Reverse Lines 🔄**
**Task:** Print the lines of the file `reverse-me.txt` in reverse order so that the last line appears first.  
**Solution:**
```bash
tac reverse-me.txt
```
**Explanation:**
- `tac` prints a file line by line in reverse order.

---

### 32. **Unique Primes 🔢**
**Task:** Print the number of unique prime numbers in `random-numbers.txt`.  
**Solution:**
```bash
cat random-numbers.txt | sort | uniq | factor | awk 'NF==2' | wc -l
```
**Explanation:**
- `sort | uniq` eliminates duplicate numbers.
- `factor` breaks numbers into their prime factors.
- `awk 'NF==2'` filters lines with exactly two fields (prime numbers only).
- `wc -l` counts the number of unique primes.

---

### 33. **Find Ports in Netstat 🌐**
**Task:** Print all IPv4 listening ports from `netstat.out`, sorted in descending order.  
**Solution:**
```bash
grep '\bLISTEN\b' netstat.out | grep -oP 'tcp\s+.*:\K\d+' | sort -nr
```
**Explanation:**
- `grep '\bLISTEN\b'` filters lines containing `LISTEN`.
- `grep -oP 'tcp\s+.*:\K\d+'` extracts port numbers using Perl-compatible regular expressions.
- `sort -nr` sorts the port numbers in descending numerical order.

---

### 34. **Monitor File Changes 📋**
**Task:** Watch for any changes in the `logs` directory and display them in real-time.  
**Solution:**
```bash
inotifywait -m logs
```
**Explanation:**
- `inotifywait` is a tool for monitoring file system events.
- `-m` enables monitoring mode to keep the command running.
- `logs` specifies the directory to monitor. It displays events like file modifications, deletions, and creations.

---

### 35. **Detect Failed SSH Login Attempts 🚨**
**Task:** Count the number of failed SSH login attempts in `/var/log/auth.log`.  
**Solution:**
```bash
grep "Failed password" /var/log/auth.log | wc -l
```
**Explanation:**
- `grep "Failed password"` searches for failed login attempts in the log file.
- `wc -l` counts the number of matching lines.

---

### 36. **List Open Network Connections 🌐**
**Task:** Display all open network connections and their statuses.  
**Solution:**
```bash
netstat -tuln
```
**Explanation:**
- `netstat` displays network statistics.
- `-tuln` shows TCP/UDP connections (`t`/`u`), listening ports (`l`), and numeric addresses (`n`).

---

### 37. **Search for SUID Files 🛡️**
**Task:** Find all files with the SUID bit set on the system.  
**Solution:**
```bash
find / -perm -4000 2>/dev/null
```
**Explanation:**
- `find /` searches the entire filesystem.
- `-perm -4000` matches files with the SUID bit set.
- `2>/dev/null` suppresses permission-denied errors.

---

### 38. **Analyze Disk Usage 📊**
**Task:** Find the top 5 largest directories in the `/var` directory.  
**Solution:**
```bash
du -h /var | sort -rh | head -n 5
```
**Explanation:**
- `du -h /var` calculates the size of each directory in human-readable format.
- `sort -rh` sorts by size in reverse order.
- `head -n 5` displays the top 5 results.

---

### 39. **Check for Active Users 👤**
**Task:** List all currently logged-in users.  
**Solution:**
```bash
who
```
**Explanation:**
- `who` displays information about users currently logged into the system.

---

### 40. **Identify Open Files by Process 🔍**
**Task:** List all open files by the `nginx` process.  
**Solution:**
```bash
lsof -c nginx
```
**Explanation:**
- `lsof` lists open files.
- `-c nginx` filters for files opened by processes named `nginx`.

---

### 41. **Verify File Integrity 🔒**
**Task:** Generate a SHA256 checksum for the file `backup.tar.gz`.  
**Solution:**
```bash
sha256sum backup.tar.gz
```
**Explanation:**
- `sha256sum` calculates the SHA256 hash of a file to verify its integrity.

---

### 42. **Securely Delete Files 🧹**
**Task:** Permanently delete `sensitive.txt` without recovery.  
**Solution:**
```bash
shred -u sensitive.txt
```
**Explanation:**
- `shred` overwrites the file multiple times before deleting it.
- `-u` ensures the file is deleted after shredding.

---

### 43. **Monitor Memory Usage 📈**
**Task:** Display real-time memory usage.  
**Solution:**
```bash
watch -n 1 free -h
```
**Explanation:**
- `watch -n 1` runs a command every second.
- `free -h` displays memory usage in human-readable format.

---

### 44. **Find Suspicious Processes 🕵️‍♂️**
**Task:** Identify processes using high CPU usage.  
**Solution:**
```bash
ps aux --sort=-%cpu | head -n 10
```
**Explanation:**
- `ps aux` lists all running processes.
- `--sort=-%cpu` sorts them by CPU usage in descending order.
- `head -n 10` shows the top 10 results.

---

### 45. **Extract Subdomain from URL 🌐**
**Task:** Extract the subdomain from a list of URLs in `websites.txt`.  
**Solution:**
```bash
awk -F[/:] '{print $4}' websites.txt
```
**Explanation:**
- `awk` processes text line by line.
- `-F[/:]` uses `/` and `:` as field separators.
- `{print $4}` extracts the fourth field, which is the subdomain or domain.

---

### 46. **List Recently Modified Files 📆**
**Task:** Find files modified in the last 24 hours.  
**Solution:**
```bash
find . -type f -mtime -1
```
**Explanation:**
- `find . -type f` locates all files.
- `-mtime -1` matches files modified within the last day.

---

### 47. **Check Open Ports 🔓**
**Task:** Display all open ports on the system.  
**Solution:**
```bash
ss -tuln
```
**Explanation:**
- `ss` displays socket statistics.
- `-tuln` shows TCP/UDP connections, listening ports, and numeric addresses.

---

### 48. **Kill Processes by Name 🛑**
**Task:** Terminate all processes named `apache2`.  
**Solution:**
```bash
pkill apache2
```
**Explanation:**
- `pkill` sends signals to processes by name.
- `apache2` is the name of the processes to terminate.

---

### 49. **Detect Hidden Files 📁**
**Task:** Find all hidden files in the current directory.  
**Solution:**
```bash
find . -type f -name ".*"
```
**Explanation:**
- `find . -type f` locates all files.
- `-name ".*"` matches hidden files (names starting with `.`).

---

### 50. **Track System Uptime ⏳**
**Task:** Display how long the system has been running.  
**Solution:**
```bash
uptime
```
**Explanation:**
- `uptime` shows the current time, uptime duration, and load averages.

---

