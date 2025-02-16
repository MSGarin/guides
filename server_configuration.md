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
To connect to the server via mosh you need to:
1. open terminal;
2. enter the command: ` mosh [username]@[server IP] `.

### errors
The following errors may occur during connection:
#### 1

```
The locale requested by LC_CTYPE=UTF-8 isn't available here.
Running `locale-gen UTF-8' may be necessary.

The locale requested by LC_CTYPE=UTF-8 isn't available here.
Running `locale-gen UTF-8' may be necessary.

mosh-server needs a UTF-8 native locale to run.

Unfortunately, the local environment (LC_CTYPE=UTF-8) specifies
the character set "US-ASCII",

The client-supplied environment (LC_CTYPE=UTF-8) specifies
the character set "US-ASCII".

locale: Cannot set LC_CTYPE to default locale: No such file or directory
locale: Cannot set LC_ALL to default locale: No such file or directory
LANG=
LANGUAGE=
LC_CTYPE=UTF-8
LC_NUMERIC="POSIX"
LC_TIME="POSIX"
LC_COLLATE="POSIX"
LC_MONETARY="POSIX"
LC_MESSAGES="POSIX"
LC_PAPER="POSIX"
LC_NAME="POSIX"
LC_ADDRESS="POSIX"
LC_TELEPHONE="POSIX"
LC_MEASUREMENT="POSIX"
LC_IDENTIFICATION="POSIX"
LC_ALL=
Connection to [server IP] closed.
/usr/local/bin/mosh: Did not find mosh server startup message. (Have you installed mosh on your server?)
```
The first thing to do to solve this is to run the ` locale ` command on the server and on the client, and compare the languages. 

The language specified on the server must match the language on the client.

At each new start of the terminal before connecting via mosh you should enter the following command: ` export LC_ALL=[service_nam] `
## Packages must_have
zsh - It is an alternative to shell.\
tree - Displays the directory structure.\
redis-server - Is an in-memory key-value store. [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-redis-on-debian-10)\
nginx - Is a free and open-source web server used to host websites and applications of all sizes. [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-debian-11)\
libssl-dev - This package is part of the OpenSSL project's implementation of the SSL and TLS cryptographic protocols for secure communication over the Internet.
