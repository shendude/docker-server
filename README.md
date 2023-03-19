# docker-server
for setup of plex and deluge

## additional setup
1. follow all setup instructions for docker-desktop here: https://docs.docker.com/engine/install/ubuntu/

2. ensure docker desktop is enabled for autorun with 
https://docs.docker.com/engine/install/linux-postinstall/

3. update the paths and claim id in the `.env` file

4. start the docker containers with `docker compose up -d`

## troubleshooting
Some drive formats do not work with POSIX permissions. exFat being one of them. In this case, to perserve compatibility with windows, I formatted the external drive to NTFS.