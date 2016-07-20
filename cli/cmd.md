# Commands

* What is shell and bash?
Shell is spec. for sending keyboard inputs to OS. Bash or Bourne Again Shell is
just implementation and exists on most GNU systems.

* Difference between shell, terminal?
Shell and terminal are two separate program. Terminal is just gui for shell and
pass keyboard inputs to shell and render outputs coming from shell.
(eg. gnome-terminal, konsole)

* whats is [me@linuxbox ~]$ command ?
me - current username
linuxbox - hostname of machine
~ - current working directory


# date
show current date and time

# cal
show this months calendar

# df
show free disk space on your drives

# free
show free memory of the machine

# exit
end terminal session

# pwd
print working directory

# cd
change working directory

  * `cd` change current directory to home
  * `cd -` change working directory to previous one
  * `cd ~me` change current directory to me user home directory
  * `.` for current directory
  * `..` for parent directory

> when working with relative path name `./` is always implied.

    cd ./bin => same as below
    cd bin

> Linux does not have file extension but some programs have.



# ls
list directory content

  * `ls /bin` list files under bin directory
  * `ls ~ /bin` list both directory files
  * `ls -l` display in long format
  * `ls -a` display all attributes for files and directories
  * `ls -lt` display listing ordered by last modification time
  * `ls -lah` show human readable format
  * `ls -laS` sort by size
  * `ls -lt -reverse` sort in reverse order
  * `ls -laFh` list all with file/dir distinction with humand readable form

> Unix have tree like hierarchy for file system. Every file whether its new or not
added to this tree. (windows create new tree for new storage device)

    -rw-r--r-- 1 root root   34391 2012-04-03 11:05 logo-Ubuntu.png


* `-rw-r--r--`  access rights to file
* `1`           number of symlinks
* `root`        owner of the file
* `root`        group that owns the file
* `34391`       size in bytes
* `2012-04-03 11:05` last modification time
* `logo-Ubuntu.png` file name


# file
determine the type of the file

    [me@linuxbox ˜]$ file picture.jpg
    picture.jpg: JPEG image data, JFIF standard 1.01


# less

View content of the most text files.

    [me@linuxbox ˜]$ less /etc/passwd

* `b` back for one page
* `SPACE` next page
* `Up/Down Arrow` line down and up
* `G` end of file
* `g` start of file
* `/characters` search for characters

> Designed after `more` which allows forward but not backward browse.

# wildcards for matching

special characters makes matching specific group easier.

* `*` any characters
* `?` any single character
* `[characters]` any character that is member of characters group
* `[!characters]` any character that is not member of char group
* `[[:class:]]` any characters that is member of given class
* `[:alnum:]` any alphanumeric character
* `[:alpha:]` any alphabetic character
* `[:digit:]` any digit character
* `[:upper:]` any uppercase character
* `[:lower:]` any lowercase character

    *         all file
    g*        all file start with g
    b*.txt    all file start with b followed by any char ending with .txt
    Data???   any file start with Data followed by exactly 3 character
    [abc]*    any file start with a,b or c
    [![:digit:]]* any file not starting with digit
    \*[[:lower:]123] file ending with lowercase letter or 1, 2 or 3


# mkdir

create new directory with given name

* `mkdir` dir1 dir2 dir3
* `mkdir` dirx

# cp

copy files or directories

* `cp item1 item2` copy item1 to item2
* `cp -i item1 item2` will ask for confirmation if item2 exist
* `cp -a item1 item2` copy item1 with its attributes
* `cp item1 item2 item3 dir1` copy all items to dir1
* `cp dir1/* dir2` copy dir1 content to dir2, dir2 must exist
* `cp -R dir1 dir2` copy dir1 and its content to dir2, dir2 will be created

# mv

move or rename files

* `mv item1 item2` move item1 as item2 (rename)
* `mv item1 item2 item3 dir1` move item123 to dir1
* `mv -i item1 item2` interactive move if item2 exist as for confirmation
* `mv dir1 dir2` move dir1 and its content to dir2 and delete dir1. create dir2 if not exist
