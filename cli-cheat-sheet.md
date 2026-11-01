
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


