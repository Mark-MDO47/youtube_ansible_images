# ansible_images
The repository contains example how to create docker images for Ansible
- This is a fork (with a tip of the hat) from https://github.com/netdevopsx/youtube_ansible_images
- That was referenced in https://www.youtube.com/watch?v=QrMzzv2olcw

# My Changes
I set it up to use Ubuntu since I am more familiar with that. 20.04 release did not have an ansible yet so I used 18.04.

# Cheat chart

## Build and run docker container in the background
docker-compose up --build -d

## List of existed images
docker images

## List of currently running containers
docker ps

## Attach to existed container
docker exec -it CONTANTER_ID bash
