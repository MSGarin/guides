# Server Configuration
In this guide describes the first steps after creating a server with the Debian operating system.
## Connecting to the server
To connect to the server you need to:
1. open terminal;
2. enter the command: ` ssh [username]@[server IP] `.
## Repository update
To update repositories you need to:
1. connect to the server;
2. enter the command: ` sudo apt-get update `.
## Installing a basic set of packages.
To install basic set of packages you need to:
1. connect to the server;
2. enter the command: ` sudo apt-get install -y vim mosh tmux htop git curl wget unzip zip gcc build-essential make `.
## Configure SSH:
To Configure SSH you need to:
1. connect to the server;
2. enter the command: ` sudo vim /etc/ssh/sshd_config `;  _(the command will open the ‘sshd_config’ file)_

3. edit the file _(change parameter values or add new parameters and values)_ so that as a result the file contains such parameters and values:

```
AllowUsers [username]
PermitRootLogin no
PasswordAuthentication no
```
4. save changes; _(to do this, press ` esc ` then type ` :wq ` and press ` Enter `)_
5. restart ssh service; _(to do this, enter the command: ` sudo service ssh restart `)_
6. disconnect from the server. _(to do this, enter the command: ` exit `)_
## Connection to the server via mosh


