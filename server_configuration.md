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
