# Shell basics
![Read the fucking manual](https://github.com/Nkosana-263/alx-system_engineering-devops/assets/60256844/6e5d551d-4bae-4bd2-bbb7-195186e028e8)

## Task 0. Where am I?
[`0-current_working_directory`](0-current_working_directory)  
Prints the absolute path name of the current working directory.

Example:
```console
$ ./0-current_working_directory
/root/alx-system_engineering-devops/0x00-shell_basics
$
```

## Task 1. What’s in there?
[`1-listit`](1-listit)  
Displays the contents list of your current directory.

Example:
```console
$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
```

## Task 2. There is no place like home
[`2-bring_me_home`](2-bring_me_home)  
Changes the working directory to the user’s home directory.

Example:
```console
nkosana@ubuntu:/tmp$ pwd
/tmp
nkosana@ubuntu:/tmp$ echo $HOME
/home/nkosana
nkosana@ubuntu:/tmp$ source ./2-bring_me_home
nkosana@ubuntu:~$ pwd
/home/nkosana
nkosana@ubuntu:~$ 
```

## Task 3. The long format
[`3-listfiles`](3-listfiles)  
Displays current directory contents in a long format.

Example:
```console
$ ./3-listfiles
total 32
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
$
```

## Task 4. Hidden files
[`4-listmorefiles`](4-listmorefiles)  
Displays current directory contents, including hidden files (starting with `.`).

Example:
```console
$ ./4-listmorefiles
total 32
drwxr-xr-x@ 6 sylvain staff 204 Jan 25 00:29 .
drwxr-xr-x@ 43 sylvain staff 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:41 4-listmorefiles
$
```

## Task 5. I love numbers
[`5-listfilesdigitonly`](5-listfilesdigitonly)  
Displays current directory contents.
  - Long format
  - with user and group IDs displayed numerically
  - And hidden files (starting with `.`)
    
Example:
```console
$ ./5-listfilesdigitonly
total 32
drwxr-xr-x@ 6 501 20 204 Jan 25 00:29 .
drwxr-xr-x@ 43 501 20 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:23 1-listfiles
-rwxr-xr-x@ 1 501 20 19 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 501 20 20 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:43 5-listfilesdigitonly
$
```

## Task 6. Welcome
[`6-firstdirectory`](6-firstdirectory)  
Creates a directory named `my_first_directory` in the `/tmp/ directory`.

Example:
```console
$ ./6-firstdirectory
$ file /tmp/my_first_directory/
/tmp/my_first_directory/: directory
$
```

## Task 7. Betty in my first directory
[`7-movethatfile`](7-movethatfile)  
Moves the file `betty` from `/tmp/` to `/tmp/my_first_directory`.

Example:
```console
$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
```

## Task 8. Bye bye Betty
[`8-firstdelete`](8-firstdelete)  
Deletes the file betty.
  - The file `betty` is in `/tmp/my_first_directory`

Example:
```console
$ ./8-firstdelete
$ ls /tmp/my_first_directory/
$
```

## Task 9. Bye bye My first directory
[`9-firstdirdeletion`](9-firstdirdeletion)  
Deletes the directory `my_first_directory` that is in the `/tmp` directory.

Example:
```console
$ ./9-firstdirdeletion
$ file /tmp/my_first_directory
/tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or directory)
$
```

## Task 10. Back to the future
[`10-back`](10-back)  
Changes the working directory to the previous one.

Example:
```console
nkosana@ubuntu:/tmp$ pwd
/tmp
nkosana@ubuntu:/tmp$ cd /var
nkosana@ubuntu:/var$ pwd
/var
nkosanaa@ubuntu:/var$ source ./10-back
/tmp
nkosana@ubuntu:/tmp$ pwd
/tmp
```

## Task 11. Lists
[`11-lists`](11-lists)  
Lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the `/boot` directory (in this order), in long format.


## Task 12.  File type
[`12-file_type`](12-file_type)   
Prints the type of the file named `iamafile`.

Example:
```console
ubuntu@ip-172-31-63-244:~$ ./12-file_type
/tmp/iamafile: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.24, BuildID[sha1]=bd39c07194a778ccc066fc963ca152bdfaa3f971, stripped
```

## Task 13. We are symbols, and inhabit symbols
[`13-symbolic_link`](13-symbolic_link)  
Creates a symbolic link to `/bin/ls`, named `__ls__`.

Example:
```console
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
ubuntu@ip-172-31-63-244:/tmp/sym$./13-symbolic_link
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
```

## Task 14. Copy HTML files
[`14-copy_html`](14-copy_html)  
Copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.


## Task 15.  Let’s move
[`100-lets_move`](100-lets_move)  
Moves all files beginning with an uppercase letter to the directory `/tmp/u`

Example:
```console
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 My_file
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 Elif_ym
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
ubuntu@ip-172-31-63-244:/tmp/sym$ ./100-lets_move
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 My_file
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 Elif_ym
```

## Task 16. Clean Emacs
[`101-clean_emacs`](101-clean_emacs)  
Deletes all files in the current working directory that end with the character `~`.

Example:
```console
ubuntu@ip-172-31-63-244:/tmp/sym$ ls
main.c  main.c~  Makefile~
ubuntu@ip-172-31-63-244:/tmp/sym$ ./101-clean_emacs
ubuntu@ip-172-31-63-244:/tmp/emacs$ ls
main.c
ubuntu@ip-172-31-63-244:/tmp/emacs$
```

## Task 17.  Tree
[`102-tree`](102-tree)  
Creates the directories `welcome/`, `welcome/to/` and `welcome/to/school` in the current directory.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 nkosana nkosana 44 Sep 20 12:09 102-tree
nkosana@ubuntu:/tmp/h$ wc -l 102-tree 
2 102-tree
nkosana@ubuntu:/tmp/h$ head -1 102-tree 
#!/bin/bash
nkosana@ubuntu:/tmp/h$ tr -cd ' ' < 102-tree | wc -c # you do not have to understand this yet, but the result should be 2, 1 or 0
2
nkosana@ubuntu:/tmp/h$ ./102-tree 
nkosana@ubuntu:/tmp/h$ ls
102-tree  welcome
nkosana@ubuntu:/tmp/h$ ls welcome/
to
nkosana@ubuntu:/tmp/h$ ls -l welcome/to
total 4
drwxrwxr-x 2 nkosana nkosana 4096 Sep 20 12:11 school
nkosana@ubuntu:/tmp/h$
```

## Task 18. Life is a series of commas, not periods
[`103-commas`](103-commas)  
 Lists all the files and directories of the current directory, separated by commas (`,`).

Example:
```console
ubuntu@ubuntu:~/$ ls -a

.  ..  0-commas  0-commas-checks  1-empty_casks  2-gifs  3-directories  4-zeros  5-rot13  6-odd  7-sort_rot13  Makefile  quote  .test  test_dir  test.var

ubuntu@ubuntu:~/$ ./103-commas

./, ../, 0-commas, 0-commas-checks/, 1-empty_casks, 2-gifs, 3-directories, 4-zeros, 5-rot13, 6-odd, 7-sort_rot13, Makefile, quote, .test, test_dir/, test.var

ubuntu@ubuntu:~/$
```

## Task 19. File type: School
[`school.mgc`](school.mgc)  
Creates a magic file `school.mgc` that can be used with the command `file` to detect `School` data files. `School` data files always contain the string `SCHOOL` at offset 0.

Example:
```console
ubuntu@ip-172-31-63-244:/tmp/magic$ cp /bin/ls .
ubuntu@ip-172-31-63-244:/tmp/magic$ ls -la
total 268
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 02:44 .
drwxrwxrwt 11 root   root   139264 Sep 20 02:44 ..
-rw-r--r--  1 ubuntu ubuntu    496 Sep 20 02:42 school.mgc
-rwxr-xr-x  1 ubuntu ubuntu 110080 Sep 20 02:43 ls
-rw-rw-r--  1 ubuntu ubuntu     50 Sep 20 02:06 thisisaschoolfile
-rw-rw-r--  1 ubuntu ubuntu     30 Sep 20 02:16 thisisatextfile
ubuntu@ip-172-31-63-244:/tmp/magic$ file --mime-type -m school.mgc *
school.mgc:         application/octet-stream
ls:                    application/octet-stream
thisisaschoolfile: School
thisisatextfile:       text/plain
ubuntu@ip-172-31-63-244:/tmp/magic$ file -m school.mgc *
school.mgc:         data
ls:                    data
thisisaschoolfile: School data
thisisatextfile:       ASCII text
ubuntu@ip-172-31-63-244:/tmp/magic$
```
