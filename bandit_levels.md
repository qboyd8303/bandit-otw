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
- 'cd' only works on directories, not files
- 'cat' displays file contents
- Errors can help identify object types.

## Level 1 → 2

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


## Level 2 → 3

### Date Completed: 2025-08-22

### Level Goal
> Find the password for level 3.

### Level Instructions / Hint
> The password for the next level is stored in a file called --spaces in this filename-- located in the home directory.

### Initial Thoughts
> I need to figure out what is special about spaces in a filename and using commands with them. I then need to locate and read the "--spaces in this filename--" file. I tried one command after learning how to prefix filenames with spaces in them.

### Successful Solution
```bash
cat ./"--spaces in this filename--"
# output: [password]
# Successfully read the contents and obtained the Level 3 password
```

### What I Learned
- Filenames with spaces in them need to be enclosed in quotations to be recognized


## Level 3 → 4

### Date Completed: 2025-08-22

### Level Goal
> Find the password for level 4.

### Level Instructions / Hint 
> The password for the next level is stored in a hidden file in the inhere directory.

### Initial Thoughts
> I need to learn how to show hidden files within a directory, then locate and read the hidden file.

### Commands Attempted
```bash
cd ~inhere
# output: -bash: cd: ~inhere: No such file or directory
# Confirms no such directory exists

cd inhere
# output: ~/inhere$
# I am now operating inside the inhere directory

cat inhere
# output: cat: inhere: No such file or directory
# There is no "inhere" file within the inhere directory to display contents of

ls "hidden files"
# output: ls: cannot access 'hidden files': No such file or directory
# There is no "hidden files" file within the inhere directory to display

cat all
# output: cat: all: No such file or directory
# There is no "cat" file within the inhere directory to display contents of
```

### Successful Solution
```bash
ls -a
# output: .  ..  ...Hiding-From-You
# Successfully located hidden file within inhere directory

cat ...Hiding-From-You
# output: [password]
# Successfully read the contents and obtained the Level 4 password
```

### What I Learned
- The command for locating hidden files is -a
