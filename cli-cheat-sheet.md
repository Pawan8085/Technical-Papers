
## 📍 Navigation



### 📂 Print Working Directory

```bash
# Display the current directory path
pwd
```

### 📋 List Directory Contents

```bash
# List files and directories
ls

# Display detailed information
ls -l

# Include hidden files
ls -a

# Detailed listing including hidden files
ls -la

# Display human-readable file sizes
ls -lh

# List contents of a specific directory
ls /home/pawan/Desktop
```

### 🔄 Change Directory

```bash
# Move into a directory
cd Desktop

# Move to the parent directory
cd ..

# Move to the previous directory
cd -

# Move to the home directory
cd ~

# Move to the root directory
cd /

# Navigate using an absolute path
cd /home/pawan/Desktop

# Navigate using a relative path
cd Desktop/projects
```

### 🌳 Display Directory Structure

```bash
# Display directory structure
tree

# Display structure up to 2 levels
tree -L 2

# Display directories only
tree -d

# Include hidden files
tree -a
```


### 📋 Useful Commands

| Command | Description |
|---|---|
| `pwd` | Displays the current directory |
| `ls` | Lists files and directories |
| `ls -l` | Displays detailed listing |
| `ls -a` | Includes hidden files |
| `ls -la` | Displays detailed listing including hidden files |
| `ls -lh` | Displays human-readable file sizes |
| `cd directory` | Moves into a directory |
| `cd ..` | Moves to the parent directory |
| `cd -` | Moves to the previous directory |
| `cd ~` | Moves to the home directory |
| `cd /` | Moves to the root directory |
| `tree` | Displays directory structure |
| `tree -L 2` | Displays structure up to 2 levels |

---


## 📁 File and Folder Operations


### 📄 Create Files

```bash
# Create an empty file
touch file.txt

# Create multiple files
touch file1.txt file2.txt file3.txt
```

### 📂 Create Directories

```bash
# Create a directory
mkdir projects

# Create multiple directories
mkdir dir1 dir2 dir3

# Create nested directories
mkdir -p projects/java/backend
```

### 📋 Copy Files and Directories

```bash
# Copy a file
cp file.txt backup.txt

# Copy a file into a directory
cp file.txt backup/

# Copy multiple files into a directory
cp file1.txt file2.txt backup/

# Copy a directory recursively
cp -r projects backup/
```

### 🚚 Move and Rename Files

```bash
# Move a file into a directory
mv file.txt backup/

# Rename a file
mv old.txt new.txt

# Move and rename a file
mv file.txt backup/new-file.txt

# Move a directory
mv projects backup/
```

### 🗑️ Delete Files and Directories

```bash
# Delete a file
rm file.txt

# Delete multiple files
rm file1.txt file2.txt

# Delete an empty directory
rmdir projects

# Delete a directory and its contents
rm -r projects

# Force delete without confirmation
rm -rf projects
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `touch file.txt` | Creates an empty file |
| `mkdir directory` | Creates a directory |
| `mkdir -p path` | Creates nested directories |
| `cp source destination` | Copies a file |
| `cp -r source destination` | Copies a directory recursively |
| `mv source destination` | Moves or renames files and directories |
| `rm file.txt` | Deletes a file |
| `rmdir directory` | Deletes an empty directory |
| `rm -r directory` | Deletes a directory and its contents |
| `rm -rf directory` | Forcefully deletes a directory and its contents |


## 📄 File Content

### 📃 Display File Contents

```bash
# Display complete file contents
cat file.txt

# Display contents of multiple files
cat file1.txt file2.txt

# Display contents with line numbers
cat -n file.txt
```

### 👀 View File Content Page by Page

```bash
# Open a file using less
less file.txt

# Open a file using more
more file.txt
```

**Useful navigation inside `less`:**
- `Space` – Next page
- `b` – Previous page
- `/keyword` – Search forward
- `?keyword` – Search backward
- `n` – Next search match
- `N` – Previous search match
- `q` – Quit

### 🔝 Display First Lines

```bash
# Display first 10 lines
head file.txt

# Display first 5 lines
head -n 5 file.txt
```

### 🔽 Display Last Lines

```bash
# Display last 10 lines
tail file.txt

# Display last 5 lines
tail -n 5 file.txt

```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `cat file.txt` | Displays complete file contents |
| `cat -n file.txt` | Displays contents with line numbers |
| `less file.txt` | Views file content page by page |
| `more file.txt` | Views file content one page at a time |
| `head file.txt` | Displays the first 10 lines |
| `head -n 5 file.txt` | Displays the first 5 lines |
| `tail file.txt` | Displays the last 10 lines |
| `tail -n 5 file.txt` | Displays the last 5 lines |
| `tail -f file.log` | Continuously monitors new content |
| `tail -F file.log` | Follows a file even if it is recreated after rotation |

---


## ↪️ Redirection


### 📤 Output Redirection

```bash
# Redirect output to a file (overwrites existing content)
echo "Hello World" > output.txt

# Append output to a file
echo "New Line" >> output.txt

# Redirect command output to a file
ls -l > files.txt

# Append command output to a file
date >> output.txt
```

### 📥 Input Redirection

```bash
# Read input from a file
cat < input.txt

# Pass file content as input to a command
sort < names.txt
```

### ⚠️ Error Redirection

```bash
# Redirect error messages to a file
ls /invalid-path 2> errors.txt

# Append error messages to a file
ls /invalid-path 2>> errors.txt

# Redirect standard output and errors to the same file
command > output.txt 2>&1

```

### 🔢 Standard Streams

| Stream | File Descriptor | Description |
|---|---:|---|
| Standard Input (stdin) | `0` | Receives input |
| Standard Output (stdout) | `1` | Displays normal output |
| Standard Error (stderr) | `2` | Displays error messages |

### 📋 Useful Operators

| Operator | Description |
|---|---|
| `>` | Redirects output and overwrites the file |
| `>>` | Redirects output and appends to the file |
| `<` | Takes input from a file |
| `2>` | Redirects error output |
| `2>>` | Appends error output |
| `2>&1` | Redirects stderr to the current stdout destination |
| `&>` | Redirects stdout and stderr |
| `/dev/null` | Discards output |

---


## 🔍 Pipes and Text Processing

Pipes allow you to pass the output of one command as input to another command. 

### 🔗 Pipes (`|`)

```bash
# Pass output of one command to another
ls -l | less

# Search files containing a keyword
ls | grep ".txt"

# Count files in the current directory
ls | wc -l

# Display running processes containing a keyword
ps aux | grep java
```

### 🔎 grep – Search Text

```bash
# Search for a word in a file
grep "error" application.log

# Case-insensitive search
grep -i "error" application.log

# Display matching line numbers
grep -n "error" application.log

# Search recursively inside directories
grep -r "TODO" .

# Display lines that do not match
grep -v "INFO" application.log

# Count matching lines
grep -c "ERROR" application.log

# Match a complete word
grep -w "failed" application.log

# Search using extended regular expressions
grep -E "ERROR|WARN" application.log
```

### 🔤 sort – Sort Lines

```bash
# Sort lines alphabetically
sort names.txt

# Sort in reverse order
sort -r names.txt

# Sort numerically
sort -n numbers.txt

# Sort and ignore case
sort -f names.txt

# Sort and remove duplicate lines
sort -u names.txt
```

### 🔁 uniq – Handle Duplicate Lines

```bash
# Remove consecutive duplicate lines
uniq names.txt

# Display duplicate lines with their counts
uniq -c names.txt

# Display only duplicate lines
uniq -d names.txt

# Display only unique lines
uniq -u names.txt
```

### 📋 Useful Commands

| Command | Description |
|---|---|
| `command1 \| command2` | Passes output of the first command to the second |
| `grep "word" file` | Searches for a word |
| `grep -i "word" file` | Searches without case sensitivity |
| `grep -n "word" file` | Displays matching line numbers |
| `grep -r "word" directory` | Searches recursively |
| `grep -v "word" file` | Displays non-matching lines |
| `grep -c "word" file` | Counts matching lines |
| `sort file` | Sorts lines alphabetically |
| `sort -r file` | Sorts in reverse order |
| `sort -n file` | Sorts numerically |
| `sort -u file` | Sorts and removes duplicates |
| `uniq file` | Removes consecutive duplicate lines |
| `uniq -c file` | Counts consecutive duplicate lines |

---


## 🔢 Word and Line Counting (`wc`)

### 📊 wc – Count Lines, Words, and Characters

```bash
# Display lines, words, and bytes
wc application.log

# Count lines
wc -l application.log

# Count words
wc -w application.log

# Count bytes
wc -c application.log

# Count characters
wc -m application.log

# Display the length of the longest line
wc -L application.log
```

### 🔗 wc with Pipes

```bash
# Count lines containing ERROR
grep "ERROR" application.log | wc -l

# Count files in the current directory
ls -1 | wc -l

# Count all files recursively
find . -type f | wc -l
```

### 📋 Quick Revision

| Command | Description |
|---|---|
| `wc file` | Counts lines, words, and bytes |
| `wc -l file` | Counts lines |
| `wc -w file` | Counts words |
| `wc -c file` | Counts bytes |
| `wc -m file` | Counts characters |
| `wc -L file` | Finds the longest line length |
| `command \| wc -l` | Counts lines from command output |



## 🔎 Finding Files (`find` and `locate`)

### 🔍 find – Search Files and Directories

```bash
# Find a file by name in the current directory and subdirectories
find . -name "application.log"

# Find files with a particular extension
find . -name "*.log"

# Find directories by name
find . -type d -name "backend"

# Find files only
find . -type f -name "*.py"

# Search without case sensitivity
find . -iname "application.log"

# Find files modified in the last 7 days
find . -type f -mtime -7

# Find files larger than 10 MB
find . -type f -size +10M

# Find and delete files (use carefully)
find . -type f -name "*.tmp" -delete
```

### 📍 locate – Search by File Path

```bash
# Search for a file
locate application.log

# Search for Python files
locate "*.py"

# Search without case sensitivity
locate -i application.log

# Update the locate database
sudo updatedb
```

**Note:**
- `find` searches the filesystem directly and reflects current changes.
- `locate` searches an indexed database, so newly created files might not appear until its database is updated.
- Install `locate` on Ubuntu if needed:

```bash
sudo apt install plocate
```

### 📋 Quick Revision

| Command | Description |
|---|---|
| `find . -name "file"` | Finds a file by name |
| `find . -iname "file"` | Finds a file ignoring case |
| `find . -type f` | Finds files only |
| `find . -type d` | Finds directories only |
| `find . -name "*.log"` | Finds files by extension |
| `find . -mtime -7` | Finds files modified within 7 days |
| `find . -size +10M` | Finds files larger than 10 MB |
| `locate file` | Searches indexed file paths |
| `sudo updatedb` | Updates the locate database |



## 🔎 Finding Files (`find`)

### 🔍 find – Search Files and Directories

```bash
# Find a file by name in the current directory and subdirectories
find . -name "application.log"

# Find files with a particular extension
find . -name "*.log"

# Find directories by name
find . -type d -name "backend"

# Find files only
find . -type f -name "*.py"

# Search without case sensitivity
find . -iname "application.log"

# Find files modified in the last 7 days
find . -type f -mtime -7

# Find files larger than 10 MB
find . -type f -size +10M

# Find and delete files (use carefully)
find . -type f -name "*.tmp" -delete
```

### 📋 Quick Revision

| Command | Description |
|---|---|
| `find . -name "file"` | Finds a file by name |
| `find . -iname "file"` | Finds a file ignoring case |
| `find . -type f` | Finds files only |
| `find . -type d` | Finds directories only |
| `find . -name "*.log"` | Finds files by extension |
| `find . -mtime -7` | Finds files modified within 7 days |
| `find . -size +10M` | Finds files larger than 10 MB |



## 🔐 File Permissions


### 👀 Understanding Permissions

```bash
# View file permissions
ls -l
```

Example output:

```text
-rwxr-xr-- 1 pawan pawan 1200 Nov 1 10:00 script.sh
```

Permission structure:

```text
-   rwx   r-x   r--
|    |     |     |
|  Owner  Group Others
|
File type
```

| Symbol | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `x` | Execute |
| `-` | Permission not granted |

### 🔑 chmod – Change Permissions

**1. Numeric Method**

| Number | Permission |
|---:|---|
| 0 | `---` |
| 1 | `--x` |
| 2 | `-w-` |
| 3 | `-wx` |
| 4 | `r--` |
| 5 | `r-x` |
| 6 | `rw-` |
| 7 | `rwx` |

```bash
# Owner: rwx, Group: r-x, Others: r--
chmod 754 script.sh

# Give everyone read and write permissions
chmod 666 file.txt

# Give owner full permissions only
chmod 700 script.sh

# Remove all permissions from everyone
chmod 000 file.txt
```

**2. Symbolic Method**

```bash
# Give owner execute permission
chmod u+x script.sh

# Remove write permission from group
chmod g-w file.txt

# Give others read permission
chmod o+r file.txt

# Give everyone read permission
chmod a+r file.txt

# Give owner read/write, group read, and others no permissions
chmod u=rw,g=r,o= file.txt
```

Permission categories:

| Symbol | Meaning |
|---|---|
| `u` | User (Owner) |
| `g` | Group |
| `o` | Others |
| `a` | All |

### 👤 chown – Change Ownership

```bash
# Change file owner
sudo chown pawan file.txt

# Change owner and group
sudo chown pawan:pawan file.txt

# Change ownership recursively
sudo chown -R pawan:pawan mydir
```

### 👥 chgrp – Change Group

```bash
# Change file group
sudo chgrp developers file.txt

# Change group recursively
sudo chgrp -R developers mydir
```

### 📋 Quick Revision

| Command | Description |
|---|---|
| `ls -l` | View file permissions |
| `chmod 755 file` | Change permissions numerically |
| `chmod u+x file` | Add execute permission for owner |
| `chmod g-w file` | Remove group write permission |
| `chown user file` | Change file owner |
| `chown user:group file` | Change owner and group |
| `chgrp group file` | Change file group |

---


## ⚙️ Process Management

### 🔍 ps – View Running Processes

```bash
# Display processes running in the current terminal
ps

# Display all running processes
ps aux

# Display processes in detailed format
ps -ef

# Search for a specific process
ps aux | grep java

# Display a process using its PID
ps -p 1234
```

### 📊 top – Monitor Processes in Real Time

```bash
# Display running processes and system resource usage
top
```

Useful keyboard shortcuts inside `top`:

| Key | Description |
|---|---|
| `q` | Quit |
| `k` | Kill a process |
| `P` | Sort by CPU usage |
| `M` | Sort by memory usage |

### 🛑 kill – Terminate a Process

```bash
# Terminate a process using PID
kill 1234

# Forcefully terminate a process
kill -9 1234

# Send a specific signal
kill -SIGTERM 1234

# Display available signals
kill -l
```

Common signals:

| Signal | Number | Description |
|---|---:|---|
| `SIGTERM` | 15 | Request graceful termination |
| `SIGKILL` | 9 | Forcefully terminate a process |
| `SIGSTOP` | 19 | Pause a process |
| `SIGCONT` | 18 | Resume a stopped process |

### 🔎 pgrep – Find Process IDs

```bash
# Find process IDs by name
pgrep java

# Search with full command line
pgrep -af java

# Search for processes belonging to a user
pgrep -u pawan
```


### 📋 Quick Revision

| Command | Description |
|---|---|
| `ps` | View current terminal processes |
| `ps aux` | View all processes |
| `ps -ef` | View processes in full format |
| `top` | Monitor processes in real time |
| `kill PID` | Gracefully terminate a process |
| `kill -9 PID` | Forcefully terminate a process |
| `pgrep java` | Find process IDs by name |

---



