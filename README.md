# JEFF-MC
Minecraft/Spigot Server Launcher using bash and screen

*A complete Minecraft server launcher!* You can deploy as many server instances as you wish, attach to their screens, execute commands, edit their configurations, and much more!

JEFF-MC will setup an environment for the user you want to run your minecraft servers as. It will create a number of scripts in that users ~/bin directory, such as ~/bin/start start to start a server, or ~/bin/status status to view its status. When you include ~/bin in your $PATH, you will be able to run the commands without specifying their full name.

## Installation
JEFF-MC requires at least the following packages: `git screen dialog make gcc bash` and a Java Runtime Engine. It has been tested on a minimal installation of Debian 9.

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
When asked if you want to automatically install Spigot, press 2. You will be aksed to enter a version number. Let's take 1.12.2. JEFF-MC will now run BuildTools to build the specified Spigot version and copy it to your server's directory. Please wait a few seconds while JEFF-MC starts the server to generate the server.properties file.
You will now be asked to enter a few configuration details (port, maxplayers, gamemode, ...). To use the default setting, just press Return for each question.

Now we can start our server:
```
start testserver
```

To attach to the server's screen, use `attach testserver`. You can also start the server using `start -a testserver`, so that it will directly attach.

## Configuration
Configuration is mainly split up into two locations: the global jeffmc.conf file located at $HOME, and one jeffmc-server.conf file in each server's directory. The configuration is loaded in three steps:

1. Default values hardcoded into JEFF-MC
2. Global configuration file at $HOME/jeffmc.conf
3. Server-specific configuration file jeffmc-server.conf inside server's directory

The configuration options are explained in the files.

## Available Commands
### attach
Attach to a running server console via screen. If you did not change the default screen configuration, you can detach from the screen by pressing `Ctrl+A` and then hit `d`.

Usage: `attach <servername>`

### autostart
Start all servers listed in `~/autostart.list`. Run this at startup to autostart your servers.

Usage: `autostart`

### clone
Clone a server. This will copy all files in the server's directory to a new server.

Usage `clone <source-servername> <destination-servername>`

### config
Configure a server. You can adjust settings like java arguments, and even in-game options like all entries from server.properties in a dialog interface.

Usage: `config <servername>`

Screenshot:

![Screenshot config](https://static.jeff-media.de/i/config.png "Screenshot config")

### create
Creates a new server. You can automatically install a custom Spigot version, or use your own jar-file. You will be asked a few basic configuration questions, such es port and maxplayers.

Usage: `create <servername>`

Hint: In further versions, create will understand command line arguments to make it useable in scripts. Right now, to batch create servers, you have to create it once and then clone the server as often as you like.

### restart
Restart a running server.

Usage: `restart <servername>`

### rmserver
Remove a server including all its files.

Usage: `rmserver <servername>`

Hint: rmserver requires confirmation. If you want to delete a server non-interactively, use `yes | rmserver <servername>`

### send
Send a command to a running server.

Usage: `send <servername> <command>`

Example: `send myserver time set day`

### start
Start a server. Use the option `-a` to automatically attach to the screen session.

Usage: `send [-a] <servername>`

### status
Show a list of all your servers indicating their status, or get the status of a specific server.

Usage: `status` or `status <servername>`

Screenshot:

![Screenshot status](https://static.jeff-media.de/i/status.png "Screenshot status")

### stop
Attempt to stop a server. If the server does not shutdown within $TIMEOUT seconds (can be defined in jeffmc.conf and jeffmc-server.conf, default 120 seconds), the shutdown is assumed as failed.

Usage: `stop <servername>`

### stopall
Attempts to shutdown all servers. This can take a while, as all servers will be shutdown consecutively.

Usage: `stopall`

Hint: In future versions, there will a be an option to shutdown all servers simultaneously.

### update
Installs the latest version of JEFF-MC. Please note: If you did custom configurations in your jeffmc.conf file, these may be lost. Please backup your config-file before starting the update. The updater will ask whether or not it should replace your jeffmc.conf file. You should always answer yes, in case there is a new config variable in the new version. You can then add your old configuration options to the new file.

Usage: `update`

## Visit us
Visit us at https://www.jeff-media.de
