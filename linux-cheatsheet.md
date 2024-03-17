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
**- Find out the hostname**
```
hostname
```
**- Check out which command uses which library in /lib**
```
strace -e open pwd
```
**- Switch user**
```
su -
```
