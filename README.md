# JEFF-MC
Minecraft/Spigot Server Launcher using Bash

A complete minecraft server launcher! You can deploy as many server instances as you wish, attach to their screens, execute commands, edit their configurations, and much more!

JEFF-MC will setup an environment for the user you want to run your minecraft servers as. It will create a number of scripts in that users ~/bin directory, such as ~/bin/start start to start a server, or ~/bin/status status to view its status. When you include ~/bin in your $PATH, you will be able to run the commands without specifying their full name.

## Prerequisites
JEFF-MC has been tested on Debian 9. You will need to install the following packages:

## Installation
Log in as the user you want to run your servers as and run:
```
git clone https://github.com/JEFF-Media-GbR/JEFF-MC
JEFF-MC/install
```

## Basic usage
Let's create our first Minecraft server using Spigot:
```
create testserver
```
You will be aksed to enter a version number. Let's take 1.12.2. JEFF-MC will now run BuildTools to build the specified Spigot version and copy it to your server's directory. Please wait a few seconds while JEFF-MC starts the server to generate the server.properties file.
You will now be asked to enter a few configuration details (port, maxplayers, gamemode, ...). To use the default setting, just press Return for each question.

Now we can start our server:
```
start testserver
```

To attach to the server's screen, use `attach testserver`. You can also start the server using `start -a testserver`, so that it will directly attach.

## Available Commands
### attach
Attach to a running server console via screen.

Usage: `attach <servername>`

### autostart
Start all servers listed in `~/autostart.list`. Run this at startup to autostart your servers.

Usage: `autostart`

### clone
Clone a server. This will copy all files in the server's directory to a new server.

Usage `clone <source-servername> <destination-servername>`

... this Readme will be updated soon.
