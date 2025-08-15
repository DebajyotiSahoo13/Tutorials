# Tutorials
## Basic Shell Commands
### 1. `pwd` - Print Working Directory
```bash
# This command shows your current location
pwd
```

### 2. `ls` - (List)
```bash
# lists all the files and folders in your current directory
ls
```
```bash
- ls /home/user/documents
- ls -l : Long listing format (shows permissions, owner, size, and modification date)
- ls -a : Show all files including hidden files (those starting with .)
- ls -la : Combination of -l and -a (long listing of all files)
```

### 3. `clear` - Clear the Terminal Screen
```bash
# Clears the terminal screen, moving the prompt to the top
clear
```

### 4. `cd` - Change Directory
```bash
# Changes the current working directory to the specified directory
cd                    # Without arguments, cd takes you to your home directory
cd Documents          # Move into Documents directory
cd ..                 # Move up one directory level (move back one directory)
cd ~                  # Move to home directory
cd /usr/local/bin     # Move to absolute path
cd -                  # Switch to previous directory
```

### 5. `touch` - Create Empty File
```bash
# Creates a new empty file
touch new1.py 
touch file.txt README.md
# touch [filename]
```

### 6. `mkdir` - Make Directory
```bash
# Creates a new directory with the specified name
mkdir new_project
mkdir "new project"
mkdir new project # two folders new and project will be created
mkdir -p path/to/new/project  # -p creates parent directories as needed
```

### 7. `rm` - remove
```bash
# Removes files or directories
rm new1.py  # Remove file
rm -r "new project"    # Remove directory recursively
rm -r new project  # Remove two folders

# Recursively operate on the specified directory AND all of its contents and continue this process through all levels of nested subdirectories until it reaches the end of each branch

rm -rf "new project" # -f force
```

### 8. `cp` - Copy
```bash
# Copies files or directories from source to destination
# cp [options] source destination
cp file1.txt file2.txt       # Simple file copy
cp -r dir1 dir2              # Copy directory recursively
cp *.txt text_files/         # Copy all txt files to directory
```

### 9. `mv` - Move/Rename Files/Directories
```bash
# Moves or renames files and directories
# mv [options] source destination or mv oldname newname
mv oldname.txt newname.txt      # Rename file
mv file.txt Documents/          # Move file to directory
mv dir1 dir2                    # Rename or move directory

# used for renaming (when source and destination are in same directory)
# while moving -i to confirm overwrite
```

### 10. Code Running
```bash
python main.py # Runs a Python script directly
code main.py # Opens a specific file in VS Code
code . # Opens the current folder in VS Code
```
### 11. Other Important
- du — folder sizes (-h human, -s summary
```bash
du -sh *        # sizes of items in current dir
```
- df — free disk space
```bash
df -h
```

```bash
ping -c 4 google.com  #check connectivity

# curl — HTTP requests 
curl -I https://example.com # headers

wget — download (if installed)

# ssh / scp — remote login & copy
ssh user@host
scp file.txt user@host:/path/
```