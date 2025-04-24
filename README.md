# docker-server
for setup of plex and deluge. targets mac hosts

## additional setup

1. update the paths and claim id in the `.env` file

2. start the docker containers with `sudo docker compose up -d`

## notes

1. use the fstab file to automate mounting. targets debian hosts

## radarr, sonarr, sabnzbd config

1. sabnzbd: after finishing the install wizard, set the temporary download folder (config/folders) and completed download folder values to the mounted volumnes downloads and incomplete-downloads

2. radarr, sonarr: set the root folders (settings/mediamanagement) to the mounted movies and tv volumes respectively

3. radarr, sonarr: add sabnzbd  as a download client using 172.17.0.1 instead of localhost due to how docker containers talk to each other in bridge mode networking
