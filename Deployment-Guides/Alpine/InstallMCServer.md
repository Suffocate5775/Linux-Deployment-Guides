# Installing a new Minecraft Server on Alpine Linux

1. Begin by installing openjdk with the following command:

```sudo apk add openjdk17-jdk``` (Optionally change the JDK version if you are planning on deploying a server for an older version of Minecraft.)

2. Download the latest server.jar from `https://www.minecraft.net/en-us/download/server` and save it to a folder in your home directory.

3. Create a new file called `startServer.sh` and add the following code:

```
#!/bin/bash

java -Xmx1024M -Xms1024M -jar server.jar nogui
```

4. Give the startServer.sh executable permissions by executing `chmod +x startServer.sh` in the terminal.

5. Run `./startServer.sh` via the terminal to start the server.

6. If you followed the above steps correctly, you should be able to connect via the IP address of your server. (If you have a firewall deployed you may need to forward port 25565 to allow external connections.)