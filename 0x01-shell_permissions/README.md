# Shell permissions
![header](https://linuxopsys.com/wp-content/uploads/2021/12/linux-file-permissions-featured-image.png)

## Task 0. My name is Betty
[`0-iam_betty`](0-iam_betty)   
Switches the current user to the user `betty`.

Example:
```console
nkosana@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
nkosana@ubuntu:/tmp/h$
```

## Task 1. Who am I
[`1-who_am_i`](1-who_am_i)   
Prints the effective username of the current user.  

Example:
```console
nkosana@ubuntu:/tmp/h$ ./1-who_am_i
nkosana
nkosana@ubuntu:/tmp/h$ 
```

## Task 2. Groups
[`2-groups`](2-groups)  
Prints all the groups the current user is part of.

Example:
```console
nkosana@ubuntu:/tmp/h$ ./2-groups
nkosana adm cdrom sudo dip plugdev lpadmin sambashare
nkosana@ubuntu:/tmp/h$ 
```

## Task 3. New owner
[`3-new_owner`](3-new_owner)  
Changes the owner of the file `hello` to the user `betty`.  

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 nkosana nkosana 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 nkosana nkosana  0 Sep 20 14:18 hello
nkosana@ubuntu:/tmp/h$ sudo ./3-new_owner 
nkosana@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 nkosana nkosana 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  nkosana  0 Sep 20 14:18 hello
nkosana@ubuntu:/tmp/h$
```

## Task 4. Empty!
[`4-empty`](4-empty)  
Creates an empty file called `hello`.

## Task 5. Execute
[`5-execute`](5-execute)   
Adds execute permission to the owner of the file `hello`.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
nkosana@ubuntu:/tmp/h$ ./5-execute 
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 6. Multiple permissions
[`6-multiple_permissions`](6-multiple_permissions)  
Adds execute permission to the owner and the group owner, and read permission to other users, to the file `hello`.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 36 Sep 20 14:31 6-multiple_permissions
-r--r----- 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./6-multiple_permissions 
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 36 Sep 20 14:31 6-multiple_permissions
-r-xr-xr-- 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 7. Everybody!
[`7-everybody`](7-everybody)  
Adds execution permission to the owner, the group owner and the other users, to the file `hello`.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:35 7-everybody
-rw-r----- 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./7-everybody 
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:35 7-everybody
-rwxr-x--x 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 8. James Bond
[`8-James_Bond`](8-James_Bond)  
Sets the permission to the `file` hello as follows:

  - Owner: no permission at all
  - Group: no permission at all
  - Other users: all the permissions

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./8-James_Bond 
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 28 Sep 20 14:40 8-James_Bond
-------rwx 1 nkosana nkosana 23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 9. John Doe
[`9-John_Doe`](9-John_Doe)  
Sets the mode of the file `hello` to this:
```console
-rwxr-x-wx 1 nkosana nkosana 23 Sep 20 14:25 hello
```

## Task 10. Look in the mirror
[`10-mirror_permissions`](10-mirror_permissions)  
Sets the mode of the file `hello` the same as `olleh`’s mode.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 nkosana nkosana 23 Sep 20 14:25 hello
-rw-rw-r-- 1 nkosana nkosana  0 Sep 20 14:43 olleh
nkosana@ubuntu:/tmp/h$ ./10-mirror_permissions 
nkosana@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 nkosana nkosana 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 nkosana nkosana 23 Sep 20 14:25 hello
-rw-rw-r-- 1 nkosana nkosana  0 Sep 20 14:43 olleh
nkosana@ubuntu:/tmp/h$ 
```

## Task 11. Directories
[`11-directories_permissions`](11-directories_permissions)  
Adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 nkosana nkosana   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx------ 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx------ 2 nkosana nkosana 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./11-directories_permissions 
nkosana@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 nkosana nkosana   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 12. More directories
[`12-directory_permissions`](12-directory_permissions)  
Creates a directory called `my_dir` with permissions 751 in the working directory.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 nkosana nkosana   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ ./12-directory_permission s
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir2
drwxr-x--x 2 nkosana nkosana 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 13. Change group
[`13-change_group`](13-change_group)  
Changes the group owner to `school` for the file `hello`.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana   34 Sep 20 15:03 13-change_group
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir2
drwxr-x--x 2 nkosana nkosana 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ sudo ./13-change_group 
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana      34 Sep 20 15:03 13-change_group
drwx--x--x 2 nkosana nkosana    4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana    4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana    4096 Sep 20 14:49 dir2
drwxr-x--x 2 nkosana nkosana    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 nkosana school   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 14. Owner and group
[`100-change_owner_and_group`](100-change_owner_and_group)  
Changes the owner to `vincent` and the group owner to `staff` for all the files and directories in the working directory.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir0
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir1
drwx--x--x 2 nkosana nkosana 4096 Sep 20 14:49 dir2
drwxr-x--x 2 nkosana nkosana 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ sudo ./100-change_owner_and_group 
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 15. Symbolic links
[`101-symbolic_link_permissions`](101-symbolic_link_permissions)  
Changes the owner and the group owner of `_hello` to `vincent` and `staff` respectively.

Example"
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana   44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 nkosana nkosana   23 Sep 20 14:25 hello
lrwxrwxrwx 1 nkosana nkosana    5 Sep 20 15:10 _hello -> hello
nkosana@ubuntu:/tmp/h$ sudo ./101-symbolic_link_permissions 
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana      44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 nkosana nkosana      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 16. If only
[`102-if_only`](102-if_only)  
Changes the owner of the file `hello` to `betty` only if it is owned by the user `guillaume`.

Example:
```console
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana    nkosana      47 Sep 20 15:18 102-if_only 
-rw-rw-r-- 1 guillaume nkosana      23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ sudo ./102-if_only 
nkosana@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 nkosana nkosana      47 Sep 20 15:18 102-if_only 
-rw-rw-r-- 1 betty  nkosana      23 Sep 20 14:25 hello
nkosana@ubuntu:/tmp/h$ 
```

## Task 17. Star Wars
[`103-Star_Wars`](103-Star_Wars)  
Plays the StarWars IV episode in the terminal.
