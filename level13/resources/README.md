# Level13

Only one file is present in home directory of the `level13` user witch is a binary file named `level13`. The **SUID** bit is set and the owner is user `flag13`

When executed, the binary `level11` outputs: `UID 2013 started us but we expect 4242`. This is pretty straightforward. We simply need to copy the file on our machine, create a user with the `uid 4242` and execute the binary `level13`.

```
┌──(kali㉿kali)-[~]
└─$ scp -P 4242 level13@192.168.122.104:/home/user/level13/level13 ./level13
           _____                      _____               _     
          / ____|                    / ____|             | |    
         | (___  _ __   _____      _| |     _ __ __ _ ___| |__  
          \___ \| '_ \ / _ \ \ /\ / / |    | '__/ _` / __| '_ \ 
          ____) | | | | (_) \ V  V /| |____| | | (_| \__ \ | | |
         |_____/|_| |_|\___/ \_/\_/  \_____|_|  \__,_|___/_| |_|
                                                        
  Good luck & Have fun

          
level13@192.168.122.104's password: 
level13
┌──(kali㉿kali)-[~]
└─$ sudo useradd snowcrash -u 4242
┌──(kali㉿kali)-[~]
└─$ sudo passwd snowcrash         
New password: 
Retype new password: 
passwd: password updated successfully
┌──(kali㉿kali)-[~]
└─$ su -c ./level13 snowcrash     
Password: 
your token is 2A31L79asukciNyi8uppkEuSx
```

This is actually not a token like previously encounterd before to log in to the flagXX account, but the flag to access to `level14`.
