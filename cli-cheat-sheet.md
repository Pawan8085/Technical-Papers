
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




