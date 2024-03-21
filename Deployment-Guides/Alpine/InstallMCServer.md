# Installing a new Minecraft Server on Alpine Linux (forked, adjusted, and working March 2024, thank you to the original author ThatOneCodeDev ) 

1. Begin by installing openjdk with the following command:

```doas apk add openjdk17-jdk``` (Optionally change the JDK version if you are planning on deploying a server for an older version of Minecraft.)

2. Download the latest server.jar from `https://www.minecraft.net/en-us/download/server` and save it to a folder in your home directory, such as Minecrat.

3. Create a new file in ~/Minecraft called `startServer.sh` and add the following code:

```
#!/bin/bash

java -Xmx1024M -Xms1024M -jar server.jar nogui
```

4. Give the startServer.sh executable permissions by executing `chmod +x startServer.sh` in the terminal.

5. Run `ash -x startServer.sh` via the terminal or ssh to start the server.

6. If you followed the above steps correctly, you should be able to connect via the IP address of your server. (If you have a firewall deployed you may need to forward port 25565 to allow external connections.)

7. first run will fail, you will be directed to edit the newly created file `eula.txt` after adjusting this file the second run should work. or you can create this file ahead of time with the following text. 

```
#By changing the setting below to TRUE you are indicating your agreement to our EULA (https://aka.ms/MinecraftEULA).
#Thu Mar 21 00:47:04 CDT 2024
eula=TRUE
```
 
