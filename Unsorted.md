# Unsorted (unformated) tips and tricks

Tips and tricks yet to be sorted and categorized.

## Updating
...

## Add Directory to Global Path
Add ``/path/to/directory`` to the ``PATH=""`` variable in ``etc/environment`` with a ``:`` separator.

Example: ``PATH="/usr/local/sbin:[...]:/path/to/directory"``

### Also apply for sudo

Run ``sudo visudo``.

Add ``/path/to/directory`` to the ``Defaults        secure_path=""`` variable with a ``:`` separator.





**

sudo apt-cache search <search term> to search for packages related to the search term 

  

.deb packages are downloaded from the Internet: install it with: sudo dpkg -i <name>.deb

  

Package might be installed, but not dependcies, check what dependencies are not installed. Then use

sudo apt-cache search <search term> 

then sudo apt install <dependency>

  

Fixing broken packages: sudo apt --fix-broken install (should not be a problem in the first place)

  
  

Fix CRD 

[https://github.com/BromTeque/CRD_persistent](https://github.com/BromTeque/CRD_persistent)

  

If you see a padlock on a folder/directory it means that it is not owned by me. Ubuntu change folder owner fix:

  

sudo chown -R <username>: <directory path>

  

open terminal in the directory the locked folder is currently in, then type:

example: sudo chown -R daniel: chrome-remote-desktop

here, the “chrome-remote-desktop” is the locked folder

  

(right of “:” it is user group, if blank, it will use the user group of the user selected, here <username>

  
  

If disk does not mount on boot, open Disks > Choose Disk to be mounted > choose partition > press cogs > edit mount options > toggle off user session defaults >  Identity as: /dev/sdb > OK

  

If CRD gives black screen with a white box where you can pick two choices, exit CRD from the connector PC, then use sudo apt update and sudo apt upgrade -y, reboot server PC, apply Bromteque CRD again. Very little likely to happen!

  

TODO

auto reboot PC after power failure (in BIOS)

Fix VPN (protonVPN / private internet access)

Fix password manager Dashlane/Lastpass

qbittorrent

rarbg.to

x265 as the movie codek

  

Plex tips

If there are variations of a series, and Plex cannot separate them (metadata issues): [https://forums.plex.tv/t/the-plex-dance/19706](https://forums.plex.tv/t/the-plex-dance/19706)

  

Naming and organizing movies: [https://support.plex.tv/articles/naming-and-organizing-your-movie-media-files/](https://support.plex.tv/articles/naming-and-organizing-your-movie-media-files/)

  

Naming and organizing TV shows: 

[https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/](https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/)

  

Name them “The Dark Knight Rises (2012) - [RARBG].mp4 to know what scene the movie comes from, for easier internal organization, and finding subtitles. If you want Plex to find the subtitles for you, refer to the scene. 

  

Localhost is the server UI, app.plex.tv is the app to stream the movies from, like Netflix

If app.plex.tv is acting up: go to localhost > wrench > settings > toggle remote access off and on

  

Starting and stopping services

Start service:

systemctl start <service>

Stop service: 

systemctl stop plexmediaserver.service 

systemctl status <service>

  

Future research

Automatic torrent download when e.g. new episodes comes out: Radarr (movies?)/Sonarr (series?). Start qbittorrent on boot up

Scripts to handle OS stuff

  
  

Selfnote:

If Authentication is required to create a color profile/managed device, then:

[https://unix.stackexchange.com/questions/417906/authentication-is-required-to-create-a-color-profile/417922](https://unix.stackexchange.com/questions/417906/authentication-is-required-to-create-a-color-profile/417922)

  

sudo nano /etc/polkit-1/localauthority/50-local.d/color.pkla

Paste the following:

  

[Allow colord for all users]

Identity=unix-user:*

Action=*

ResultAny=yes

ResultInactive=yes

ResultActive=yes

**
