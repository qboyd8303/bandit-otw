## Level 0 → 1

### Date Completed: August 21, 2025

### Level Goal
> Find the password for Level 1.

### Level Instructions / Hint
> The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Initial Thoughts
> I need to locate and read the readme file. I will likely need to test commands for listing files and reading them.

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
# Learned that readme is a file, not a directory
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
- Error messages are helpful to determine whether something is a file or directory.

## Level 1 → 2

### Date Completed: August 22, 2025

### Level Goal
> Find the password for level 2.

### Level Instructions / Hint
> The password for the next level is stored in a file called - located in the home directory.

### Initial Thoughts
> I need to locate and read the "-" file.

### Commands Attempted
```bash
cat -
# output: 
# Learned this is interpreted as standard input, not a file

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
- Filenames beginning with - can confuse commands
- Prefixing with ./ ensures the file is interpreted as a filename instead of a flag


## Level 2 → 3

### Date Completed: August 22, 2025

### Level Goal
> Find the password for level 3.

### Level Instructions / Hint
> The password for the next level is stored in a file called --spaces in this filename-- located in the home directory.

### Initial Thoughts
> I need to figure out what is special about spaces in a filename and using commands with them. I then need to locate and read the "--spaces in this filename--" file. I'll review the helpful reading material before beginning.

### Successful Solution
```bash
cat ./"--spaces in this filename--"
# output: [password]
# Successfully read the contents and obtained the Level 3 password
```

### What I Learned
- Filenames with spaces must be enclosed in quotes or escaped with backslashes


## Level 3 → 4

### Date Completed: August 22, 2025

### Level Goal
> Find the password for level 4.

### Level Instructions / Hint 
> The password for the next level is stored in a hidden file in the inhere directory.

### Initial Thoughts
> I need to learn how to show hidden files within a directory, then I can open it with cat.

### Commands Attempted
```bash
cd ~inhere
# output: -bash: cd: ~inhere: No such file or directory
# Learned '~inhere' is invalid

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
- Hidden files in Linux start with a . and don’t show up unless you use ls -a
- Directories (cd) and files (cat) behave differently, and errors help clarify which is which


## Level 4 → 5

### Date Completed: August 22. 2025

### Level Goal
> Find the password for level 5.

### Level Instructions / Hint 
> The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

### Initial Thoughts
> I need to enter the inhere directory and locate a plain text file.

### Commands Attempted
```bash
cd inhere
# output: /inhere$ 
# I am successfully in the inhere directory

ls
# output: -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
# Contents of inhere directory are now shown

cat ./-file09
# output: I   0 V ;C r  A<D t    ` 
# This is not a human readable file

cat ./-file08
# output: 2;  ɸd$7_ n F   9     'uڢ  i
# This is not a human readable file
```

### Successful Solution
```bash
cat ./-file07
# output: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
# Successfully read the contents and obtained the level 5 password
```

### What I Learned
- You can use cat to display contents of a file or file to determine the type of a given file