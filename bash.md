# Bash Cheat Sheet

### File Commands

#### Directory Contents
```bash
ls # directory listing
ls -l # formatted directory listing
ls -a # directory listing with hidden files
ls -al # formatted list with hidden files
```

#### Navigating
```bash
cd dir # change directory to dir
cd # change to home
pwd # print working directory
```

#### Deleting
```bash
rm file # delete file
rm -r dir # delete directory
rm -f file # force remove file
rm -rf dir # force remove directory
```

#### Creating
```bash
cp file1 file2 # copy file1 to file2
mv file1 file2 # move file1 to file2
ln -s file link # create symbolic link 'link' to file
touch file # create or update file
mkdir dir # create directory dir
```

#### Reading
```bash
cat > file # place standard input into file
more file # output the contents of the file
less file # output the contents of the file
head file # output the first 10 lines of file
tail file # output the last 10 lines of file
tail -f file # output contents of file as it grows
```

### SSH
```bash
ssh user@host # connect to host as user
ssh -p port user@host # connect using port p
ssh -D port user@host # connect and use bind port
```

### Installation
```bash
./configure
make
make install
```

### Network
```bash
ping host # ping host 'host'
whois domain # get whois for domain
dig domain # get DNS for domain
dig -x host # reverse lookup host
wget file # download file
wget -c file # continue stopped download
wget -r url # recursively download files from url
```

### System Info
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

### Searching
```bash
grep patter files # search for parttern in files
grep -r pattern dir # search recursively for pattern in dir
command | grep pattern # search for pattern in the output of command
locate file # fild all instances of file
```

### Process Management
```bash
ps # display currently active process
ps aux # ps with a lot of detail
kill pid # kill process with pid 'pid'
killall proc #  kill all processes named proc
bg # lists stopped/background jobs, resume stopped job in background
fg # bring most recent job to foreground
fg n # brings job n to foreground
```

### File Permissions

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

### Compression
```bash
tar cf file.tar files - tar files into file.tar
tar xf file.tar - untar into current directory
tar tf file.tar - show contents of archive
```
#### tar flags
| Flag | Use |
| :-- | :-- |
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

### Shortcuts
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
