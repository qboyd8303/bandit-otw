## Level 0 → 1

### Date Completed: 2025-08-21

### Level Goal
> Find the password for Level 1.

### Level Instructions / Hint
> The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Initial Thoughts
> I need to locate and read the `readme` file. I tried several commands to find it and understand its type before successfully reading its contents.

### Commands Attempted
```bash
find file readme
# output: find: ‘file’: No such file or directory
readme
# Learned that 'find file' is not a valid command

find readme
# output: readme
# Successfully located the readme file

ls readme
# output: readme
# Confirms that the readme file exists in the current directory

cd readme
# output: -bash: cd: readme: Not a directory
# Learned that readme is a file, not a folder
```

### Successful Solution
```bash
cat readme
# output: The password you are looking for is: [password]
# Successfully read the contents and obtained the Level 1 password
```

### What I Learned
- 'cd' only works on directories, not files.
- 'cat' displays file contents.
- Errors can help identify object types.


## Level 1 -> 2

### Date Completed: 2025-08-22

### Level Goal
> Find the password for level 2.

### Level Instructions / Hint
> The password for the next level is stored in a file called - located in the home directory.

### Initial Thoughts
> I need to locate and read the "-" file. I tried some commands to find it and understand its type before successfully reading its contents.

### Commands Attempted
```bash
cat -
# output: 
# Learned that 'cat -' is an incomplete command

ls - 
# output: -
# Confirms that the - file exists in the current directory
```

### Successful Solution
```bash
cat ./-
# output: [password]
# Successfully read the contents and obtained the Level 2 password
```

### What I Learned
- When using a command with a dashed filename, prefix the filename with ./