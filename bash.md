# Bash Cheat Sheet

## Table of Contents
1. [Special Characters](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#special-characters)
2. [File Commands](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#file-commands)
    * [Directory Contents](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#directory-contents)
    * [Navigating](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#navigating)
    * [Deleting](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#deleting)
    * [Creating](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#creating)
    * [Reading](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#reading)
    * [Editing](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#editing)
3. [SSH](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#ssh)
4. [Installation](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#installation)
5. [Network](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#network)
6. [System Info](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#system-info)
7. [Searching](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#searching)
8. [Process Management](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#process-management)
9. [File Permissions](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#file-permissions)
10. [Compression](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#compression)
11. [Shortcuts](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#shortcuts)
12. [Variables](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#variables)
13. [Aliases](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#aliases)
14. [Functions](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#functions)
15. [Control Flow](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#control-flow)
    * [If... Else...](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#if-else)
    * [For Loops](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#for-loops)
    * [While Loops](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#while-loops)
[Sources](https://github.com/fredabood/Cheat-Sheets/blob/master/bash.md#sources)
--------------------------------------------------------------------------------
## Special Characters
```bash
- # used to declare flags for functions, "cd -" changes to the previous directory
\ # escapes special characters and allows for line break
# comment # starts a comment
. # the current directory
~ # the home directory
command; # ends the command
$variable # used to call variable
command1 && commad2 # command2 will run if the command1 succeeds
[ conditional ] # evaluates the conditional
command1 | command2 # sends the stdout of command1 to the stdin of command2
command > file # overwrites a file with the output of the command
command >> file # appends the output of the command to the end of the file
```

## File Commands

### Directory Contents
```bash
ls # directory listing
ls -l # formatted directory listing
ls -a # directory listing with hidden files
ls -al # formatted list with hidden files
```

### Navigating
```bash
cd dir # change directory to dir
cd # change to home
pwd # print working directory
```

### Deleting
```bash
rm file # delete file
rm -r dir # delete directory
rm -f file # force remove file
rm -rf dir # force remove directory
```

### Creating
```bash
cp file1 file2 # copy file1 to file2
mv file1 file2 # move file1 to file2
ln -s file link # create symbolic link 'link' to file
touch file # create or update file
mkdir dir # create directory dir
```

### Reading
```bash
cat > file # place standard input into file
more file # output the contents of the file
less file # output the contents of the file
head file # output the first 10 lines of file
tail file # output the last 10 lines of file
tail -f file # output contents of file as it grows
```

### Editing
#### TR
```bash
# Converting a tab delimited file into commas
cat tab_delimited.txt | tr "\\t" "," > comma_delimited.csv

# Command chaining
cat README.md | tr "[:punct:][:space:]" "\n" | tr "[:upper:]" "[:lower:]" > output.txt

# Converting all upper case letters to lower case with regex
cat filename.csv | tr '[A-Z]' '[a-z]'
```
TR Built In Variables

| Variable | Definition |
| :------- | :--------- |
| [:alnum:] | all letters and digits |
| [:alpha:] | all letters |
| [:blank:] | all horizontal whitespace |
| [:cntrl:] | all control characters |
| [:digit:] | all digits |
| [:graph:] | all printable characters, not including space |
| [:lower:] | all lower case letters |
| [:print:] | all printable characters, including space |
| [:punct:] | all punctuation characters |
| [:space:] | all horizontal or vertical whitespace |
| [:upper:] | all upper case letters |
| [:xdigit:] | all hexadecimal digits |

## SSH
```bash
ssh user@host # connect to host as user
ssh -p port user@host # connect using port p
ssh -D port user@host # connect and use bind port
ssh -t user@host "do something" # execute a command on a remote machine
```

## Installation
```bash
./configure
make
make install
```

## Network
```bash
ping host # ping host 'host'
whois domain # get whois for domain
dig domain # get DNS for domain
dig -x host # reverse lookup host
wget file # download file
wget -c file # continue stopped download
wget -r url # recursively download files from url
```

## System Info
```bash
date # show current date/time
cal # show this month's calendar
uptime # show uptime
w # display who is online
whoami # who are you logged in as
uname -a # show kernel config
cat /proc/cpuinfo # cpu info
cat /proc/meminfo # memory info
man command # show manual for command
df # show disk usage
du # show directory space usage
du -sh # human readable size in GB
free # show memory and swap usage
whereis app # show possible locations of app
which app # show which app will be run by default
```

## Searching
```bash
grep patter files # search for parttern in files
grep -r pattern dir # search recursively for pattern in dir
command | grep pattern # search for pattern in the output of command
locate file # fild all instances of file
```

## Process Management
```bash
ps # display currently active process
ps aux # ps with a lot of detail
kill pid # kill process with pid 'pid'
killall proc #  kill all processes named proc
bg # lists stopped/background jobs, resume stopped job in background
fg # bring most recent job to foreground
fg n # brings job n to foreground
```

## File Permissions

Add up the numbers corresponding to all desired permissions for each user/group,
then concat the results.

```bash
chmod octal file # change permissions of file

  4 - read (r)
  2 - write (w)
  1 - execute (x)

  order: owner/group/world

  eg:
  chmod 777 file # everyone has rwx permissions for file
  chmod 755 file # rw for owner, rx for group/world
```

## Compression
```bash
tar cf file.tar files - tar files into file.tar
tar xf file.tar - untar into current directory
tar tf file.tar - show contents of archive
```
### tar flags
| Flag | Use |
| :--- | :-- |
| c | create archive |
| t | table of contents |
| x | extract |
| f | specific filename |
| z | use zip/gzip |
| j | bzip2 compression |
| k | do not overwrite |
| T | files from file |
| w | ask for confirmation |
| v | verbose |

```bash
gzip file # compress file and rename to file.gz
gzip -d file.gz # decompress file.gz
```

## Shortcuts
```bash
ctrl+c # halts current command
ctrl+z # stops current command
fg # resume stopped command in foreground
bg # resume stopped command in background
ctrl+d # log out of current session
ctrl+w # erases one word in current line
ctrl+u # erases whole line
ctrl+r # reverse lookup of previous commands
!! # repeat last command
exit # log out of current session
```

## Variables
```bash
export VARIABLE=value # stores value as variable for this session
```

## Aliases
Think of aliases as nicknames. You might have a command that you perform a lot but want to shorten.
```bash
alias desktop="cd ~/Desktop" # "desktop" will now execute "cd ~/Desktop"
```

## Functions
Functions contains logic. In a function, you might make calls to several different programs. Here's a simple echo function

This function executes a git add/commit/pull/push in sequence upon successful completion of the previous command. Correct usage is `git_push "commit message"`
```bash
function git_push() {
  git add -A; \
  git commit -m "$1"; \
  git pull --rebase && \
  git push;
}
```

## Control Flow

### If... Else...
```bash
if conditional; then
  # do something
elif different_conditional; then
  # do something else
else
  # do something else
fi
```

### For Loops
```bash
for item in iterable; do
  # do something
done
```

### While Loops
```bash
while conditional; do
  # do something
done
```
--------------------------------------------------------------------------------
# Sources
* [Unix Power Tools](https://docstore.mik.ua/orelly/unix2.1/upt/ch08_19.htm)
* [Conquering The Command Line](http://conqueringthecommandline.com/book/basics)
* [Rock the Command Line](https://towardsdatascience.com/rock-the-command-line-52c4b2ea34b7)
* [Command Line Tricks For Data Scientists](https://medium.com/@kadek/command-line-tricks-for-data-scientists-c98e0abe5da)
* [Ten Things I Wish I’d Known About bash](https://zwischenzugs.com/2018/01/06/ten-things-i-wish-id-known-about-bash/)
* [Bash: Argument Parsing](https://medium.com/@Drew_Stokes/bash-argument-parsing-54f3b81a6a8f)
* [How to get arguments with flags in Bash](https://stackoverflow.com/questions/7069682/how-to-get-arguments-with-flags-in-bash/7069755#7069755)
