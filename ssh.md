# SSH
In this guide describes the algorithm for creating and obtaining SSH.

## macOS

### Creation

To create SSH you need to:
1. open terminal;
2. enter the command: ` ssh-keygen `

As a result system will generate a default path to store ssh. 
```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/[username]/.ssh/id_rsa): 
```
3. Next, press ` Enter `.

As a result, the system will prompt you to enter a passphrase. 
```
Enter passphrase (empty for no passphrase): 
```
It is acceptable not to enter the passphrase.

If you enter a passphrase, you will have to provide it every time you use this key.


4. Next, press ` Enter `.

As a result, the system will prompt you to re-enter the passphrase.
```
Enter same passphrase again: 
```

5. Next, press ` Enter `.

Finally, your system will generate an SSH key pair.
```
Your identification has been saved in /Users/[username]/.ssh/id_rsa
Your public key has been saved in /Users/[username]/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:LxGYg0dw2Lu2WuN5vTQQ2bA7OUSsuGl5SmOJ4OSYwzY [username]@[PCname].local
The key's randomart image is:
+----[RSA 256]----+
|    .+o.o        |
|    .+.+.=       |
|    ..=o* .      |
|..  ..oo =       |
|*o . = .S        |
|+E. X +  *       |
|...+ =o...+      |
|    .o.o.o..     |
|    ..o.  ..     |
+----[SHA256]-----+
[username]@[PCname] ~ % 
```
### Obtaining

In order to obtain a public key, it is necessary to:
1. open terminal;
2. enter the command: ` cat ~/.ssh/[ssh file name].pub `

As a result, the system will reflect the public key.
```
ssh-rsa AAAAC3NzaC1lZDI1NTE5AAAAIIeNuPJf8b0Wfb6BP/AHFdNz5ycapxDpUPc6VySdZOMx [username]@[PCname].local
```
### Storage

When SSH is created, the system defaults to saving it to:
```
/Users/[username]/.ssh/)
```
The `.ssh` folder is a hidden folder. To reflect hidden folders, use the keyboard shortcut ` shift ` + ` command ` + ` . ` .
