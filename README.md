![enter image description here](https://camo.githubusercontent.com/3e9ba499fd311db91f02459bf0ff507620ca04b9/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f353530343239382f313231373733342f61326333643331362d323661652d313165332d396235322d3932373738343765326230642e706e67)

## PlexConnect for unRAID ##
 
**FIRST TIME USERS**

PlexConnect uses port 53, 80 and 443, so you must move the unRAID management interface to a new port.

1. Edit /boot/config/go
2. Replace: /usr/local/sbin/emhttp &
3. With: /usr/local/sbin/emhttp -p XX & (where XX equals the port)
4. Shutdown your array
5. Reboot unRAID

**Usage:**

```docker run -d \
--host="NAME" \
--name="plexconnect" \
-v /path/to/plexconnect:/opt/plexconnect \
-v /etc/localtime:/etc/localtime:ro 
-p 53:53 \
-p 80:80 \
-p 443:443 \
izzno/unraid-plexconnect
```

**Description**

PlexConnect is stored outside the container making sure all changes are saved.

* Plexconnect is pulled each time you start the container securing new updates
* Certificates are auto-generated the first time you run this docker
* All changes are persistant, ink plex login
* For the best experiance, enable **Fanart** in General Appearance Settings

For how to configure you appletv please see:
https://github.com/iBaa/PlexConnect/wiki/Install-Guide-AppleTV-Wifi

**Troubleshooting**:

Before reporting a problem, please reboot your appleTV and/or pull/restart you're image/container.
Report issues: https://github.com/izznogooood/unraid-plexconnect/issues