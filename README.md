**FORK NOTICE**

I'm attempting to use this with different ports, so in unraid I can forward the networking through the other delugevpn container


**Application**

[Deluge](http://deluge-torrent.org/)

**Description**

Deluge is a full-featured ​BitTorrent client for Linux, OS X, Unix and Windows. It uses ​libtorrent in its backend and features multiple user-interfaces including: GTK+, web and console. It has been designed using the client server model with a daemon process that handles all the bittorrent activity. The Deluge daemon is able to run on headless machines with the user-interfaces being able to connect remotely from any platform.

**Build notes**

Latest stable Deluge release from Arch Linux repo.

**Usage**
```
docker run -d \
    -p 8113:8113 \
    -p 58847:58847 \
    -p 58947:58947 \
    --name=<container name> \
    -v <path for data files>:/data \
    -v <path for config files>:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e DELUGE_DAEMON_LOG_LEVEL=<critical|error|warning|info|debug> \
    -e DELUGE_WEB_LOG_LEVEL=<critical|error|warning|info|debug> \
    -e UMASK=<umask for created files> \
    -e PUID=<uid for user> \
    -e PGID=<gid for user> \
    joeydoesthings/arch-deluge
```

Please replace all user variables in the above command defined by <> with the correct values.

**Access application**<br>

`http://<host ip>:8112`

**Example**
```
docker run -d \
    -p 8113:8113 \
    -p 58847:58847 \
    -p 58947:58947 \
    --name=deluge \
    -v /apps/docker/deluge/data:/data \
    -v /apps/docker/deluge/config:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e DELUGE_DAEMON_LOG_LEVEL=info \
    -e DELUGE_WEB_LOG_LEVEL=info \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    joeydoesthings/arch-deluge
```

**MY Example**

```
docker run -d \
    -p 8113:8113 \
    -p 58847:58847 \
    -p 58947:58947 \
    --name=deluge2 \
    -v /mnt/user/appdata/deluge2/data:/data \
    -v /mnt/user/appdata/deluge2/config:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e DELUGE_DAEMON_LOG_LEVEL=info \
    -e DELUGE_WEB_LOG_LEVEL=info \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    joeydoesthings/arch-deluge
```

**Notes**<br>

User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:-

```
id <username>
```

Default password for the webui is "deluge"
___
If you appreciate ~~my~~ binhex's work, then please consider buying ~~me~~ binhex a beer  :D

[![PayPal donation](https://www.paypal.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MM5E27UX6AUU4)

[Documentation](https://github.com/binhex/documentation) | [Support forum](http://lime-technology.com/forum/index.php?topic=45820.0)
