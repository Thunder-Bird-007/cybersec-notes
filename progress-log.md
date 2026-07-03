# Cybersecurity Progress Log



## Week 1

### Bandit 0 → 1

- Connected via SSH: `ssh bandit0@bandit.labs.overthewire.org -p 2220`

- Used `ls` to list files, `cat readme` to print file contents and find the password

- Learned: after finding the next level's password, you must reconnect using the **new** username (bandit1), not the old one — got "access denied" by forgetting this

### Bandit 1 → 2
- File was named `-` (a single dash)
- `cat -` reads from stdin instead — dash has special meaning to many commands
- Fix: `cat ./-` forces it to be read as a literal filename in the current directory

### Bandit 2 → 3
- File was named `--spaces in this filename--` — contains spaces and starts with dashes
- Unquoted, bash splits the name into separate arguments at each space, and the leading `--` gets read as a flag by cat
- Fix: combine quoting and the ./ prefix — `cat ./'--spaces in this filename--'`
- Quotes stop word-splitting; ./ stops the leading dash being read as an option

### Bandit 3 → 4

The password was stored inside a hidden file located in the inhere directory.

At first, running `ls` showed nothing because hidden files are not displayed by default.

Using:

ls -a

revealed the hidden file. After identifying it, I used `cat` to read its contents and obtained the password for the next level.

Key lesson:
Files whose names begin with `.` are hidden in Linux. When a directory appears empty, `ls -a` should be one of the first commands to try.

### Bandit 4 → 5

The password was hidden among several files inside the inhere directory.

Instead of opening every file one by one, I first identified which file was likely to contain readable text by using the `file` command. After finding the human-readable file, I used `cat` to display its contents and obtain the password.

Key lesson:
The `file` command determines a file's type from its contents instead of relying on its filename or extension. This is useful when filenames give little or no information.

### Bandit 5 → 6

The password was hidden inside one of many files spread across multiple directories.

I first used the `file` command to identify human-readable files, but there were still many candidates. The level description also specified that the target file had an exact size and was not executable.

Instead of manually checking every file, I used:

find . -size 1033c

This immediately narrowed the search to the correct hidden file. After locating it, I used `cat` to read the password.

Key lessons:
- `find` searches files by their properties instead of filtering command output.
- Hidden files are not matched by the `*` wildcard, which explained why my earlier wildcard-based commands missed the correct file.