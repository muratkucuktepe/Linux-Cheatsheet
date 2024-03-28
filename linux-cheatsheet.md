**- Find IP address of Linux machine**
```
ifconfig
// or
ip addr
// Then check INET under enp0s3 interface. 
```
---
**- Access Linux via Windows command**
```
ssh -l <username> <ipaddress>
```
---
**- Find out the current username**
```
whoami
```
---
**- Find out the hostname**
```
hostname
```
---
**- Check out which command uses which library in /lib**
```
strace -e open pwd
```
---
**- Switch user**
```
su -
```
---
**- Change password**
```
passwd userid
passwd          // If you are already logged in with your account und want to change this account.
```
---
**- Listing files**
```
ls          // List storage
ls -l       // List storage long with more information
ll          // Equivalent of ls -l. It is an alias
ls -ltr     // List storage in detail but oldest on top, newest on bottom
ls -a       // Lists all files, including hidden files with a dot. a means all.
ls -lh      // Lists all files in human readable form. h means human readable. M for MB, K for KB etc.
ls -li      // i means inode. inode is a pointer or number of file on the hard disk.
ls -ltri    // This just sorts the files
```
---
**- Creating files**
```
touch <file-name>                 // Creates new file on current directory
touch <file-name1> <file-name2>   // Creates multiple files 

vi <file-name>                    // Creates a new file, opens up an editor. Make your changes, save it after :wq!
```
---
**- Creating directories**
```
mkdir <directory-name>   // make directory
```
---
**- Removing files or directories.**
```
rm -f <file-name>        // Remove a file. f means file
rm -r <directory-namt>   // Remove a directory. r means recursive
```
---
**- Copying files**
```
cp <source-file-name> <target-file-name>   // Copies source file and creates a target file
```
---
**- Copying directories**
```
cp -R <source-file-name> <target-file-name>   // Copies source file and creates a target file. R means recursive
```
---
**- Finding files or directories**
```
// Find command iterates over files and directories. It is slower but more accurate comparing to locate command
find . -name "file-name"                              // Finds the files relative to current directory where you are
find \ -name "file-name"                              // Finds the files with exact path to the root directory
find \aDirectory\anotherDirectory -name "file-name"   // Finds the files with exact path to the defined directory
// Uses prebuilt database which should be regularly updated. Faster but not accurate
locate "file-name"                                    // To update the database use updatedb command   
```
---
**- Wildcards**
```
* - One or more characters
? - Single charater
[] - A range of character (either or)
\ - Escape character
^ - The beginning of the line
$ - The end of the line
```
```
// EXAMPLES:
rm abc*                // Remove everything starting with abc
touch abcd{1..9}-xyz   // Creates 9 files like abcd1-xyz abcd2-xyz etc.
ls -l abc*             // List all the files starting with abc.
ls -l ?bcd*            // Gives all files with one char at the beginning and many at the end.
ls -l *[cd]*           // Every file including either c or d
```
---
**- Hard and soft links**
```
// Navigate to the directory where you want to create soft link
ln -s /<directory>/<directory>/<soft-link-name>   // s means soft link. Creates a softlink-name here in directory /<directory>/<directory>
ls /<directory>/<directory>/<hard-link-name>      // Creates a hardlink-name here in directory /<directory>/<directory>
```
```
// Notes: 
// If you remove original file, the file in hard link stays untouched. On the other hand soft link file will be gone.
// Hard links only work withing the same partition.
// You cannot create soft or hard link within the same directory with the same name.
```
---
**- Listing commands**
```
man -ls   // Lists all commands. man means manual
// If you press space you will see other pages.
```
---
**- List of all packages on the machine**
```
// 1. Way
dnf list installed                         // dnf is package manager. dnf means dandified YUM
dnf list installed | grep <package-name>   // Search for a specific package name. Ex: dnf list installed | grep podman

// 2. Way
rpm -qa                         // rpm is package manager. qa means query all. rpm means Red Hat Package Manager.
rpm -qa | grep <package-name>   // Search for a specific package name. Ex: rpm -qa | grep podman
```
---
**- Update all packages on the machine**
```
sudo dnf update
```
---
**- Installing podman**
```
sudo dnf install podman   // Install Podman
```
