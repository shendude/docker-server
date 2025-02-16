# docker-server
for setup of plex and deluge

## additional setup
1. follow all setup instructions for docker-desktop here: https://docs.docker.com/engine/install/ubuntu/

2. ensure docker desktop is enabled for autorun with 
https://docs.docker.com/engine/install/linux-postinstall/

3. update the paths and claim id in the `.env` file

4. Edit the `etc/fstab` file in accordance to the provided template. Make sure the UUIDs are set correctly to the appropriate ntfs partitions, detected by `lsblk -f`

5. start the docker containers with `sudo docker compose up -d`

6. note: had to install docker and interact with it purely via cli (gui ran into issues with hardware decode setting^)

## troubleshooting
Some drive formats do not work with POSIX permissions. exFat being one of them. In this case, to perserve compatibility with windows, I formatted the external drive to NTFS.

warning: modifying `etc/fstab` to automount drives will cause startup to fail or be slow if these drives are not connecterd at boot time. One will need to enter recovery shell
and delete the additional fstab entries to bypass this issue.

## radarr, sonarr, sabnzbd config

1. sabnzbd: after finishing the install wizard, set the temporary download folder (config/folders) and completed download folder values to the mounted volumnes downloads and incomplete-downloads

2. radarr, sonarr: set the root folders (settings/mediamanagement) to the mounted movies and tv volumes respectively

3. radarr, sonarr: add sabnzbd  as a download client using 172.17.0.1 instead of localhost due to how docker containers talk to each other in bridge mode networking
