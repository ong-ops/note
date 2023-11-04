# nfs (Port 2049)

- **Network File System** is a service to share directory and file with over a network
- Using TCP port 2049
- https://docs.oracle.com/cd/E19683-01/816-4882/6mb2ipq7l/index.html
- https://nfs.sourceforge.net/
- https://wiki.archlinux.org/title/NFS

## Enumerate

- Anonymous Login

## Command

Install the NFS package
```
sudo apt install nfs-common
```
- https://packages.ubuntu.com/jammy/nfs-common

Show mount info for an NFS server
```
/usr/sbin/showmount -e <ip>
```

Mount an directory from NFS server
```
sudo mount -t nfs <ip>:<share_dir> <dest_dir> -nolock
```
- `-nolock` Not use NLM locking

### Root Squashing
  - Default Enable Root Squashing -> prevent anyone connect to the NFS share from having root access
  - Remote root users are assigned a user "nfsnobody" when connected (Least local privileges)
  - If disabled then it can allow the creation of SUID bit files, allowing a remote user root access to the connected system
  - SUID
    - file can be run with the permission of the file owner/group
