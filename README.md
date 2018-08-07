# JEFF-MC
JEFF-MC Spigot Launcher

A complete minecraft server launcher! You can deploy as many server instances as you wish, attach to their screens, execute commands, edit their configurations, and much more!

## Example usage
Please see below for installation details (coming soon)

Let's create our first server using Spigot:
```
create testserver
```
You will be aksed to enter a version number. Let's take 1.12.2. JEFF-MC will now run BuildTools to build the specified spigot version and copy it to your server's directory. Please wait a few seconds while JEFF-MC starts the server to generate the server.properties file.
You will now be asked to enter a few configuration details (port, maxplayers, gamemode, ...). To use the default setting, just press Return for each question.

Now we can start our server:
```
start testserver
```

To attach to the server's screen, use `attach testserver`. You can also start the server using `start -a testserver`, so that it will directly attach.
