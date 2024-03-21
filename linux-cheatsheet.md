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
ls -ltr     // List storage in detail but oldes on top, newest on bottom
ls -a       // Lists all files, including hidden files with a dot. a means all.
ls -lh      // Lists all files in human readable form. h means human readable. M for MB, K for KB etc.
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
