# Shinobi by Shinobi Systems for Docker
#### ShinobiCCTV, ShinobiNVR, ShinobiVMS

Built on MiGoller's Docker image.

## How to Install

1. Just do it.

```
docker run -d \
--name='Shinobi' \
 -e 'APP_BRANCH=dev' \
 -p '8080:8080/tcp' \
 -v "/dev/shm/shinobiStreams":'/dev/shm/streams':'rw' \
 -v "$HOME/shinobiConfig":'/config':'rw' \
 -v "$HOME/shinobiCustomAutoLoad":'/customAutoLoad':'rw' \
 -v "$HOME/shinobiDatabase":'/var/lib/mysql':'rw' \
 -v "$HOME/shinobiVideos":'/shinobi/videos':'rw' \
 'shinobisystems/shinobi:latest-ubuntu'
```

## Docker Command Breakdown

| Command Flag | Value | Description |
|--------------|------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| --name= | Shinobi | Unique container name for the Shinobi docker container. |
| -e | APP_BRANCH=dev | Set Branch to Development Branch (Latest code) |
| -p | 8080:8080/tcp | Port forward from the docker container. Format is as follows <CONTAINER>:<HOST>/<PROTOCOL> |
| -v | "/dev/shm/shinobiStreams":'/dev/shm/streams':'rw' | Volume Map for the temporary data. This is done to allow a larger share for the memory while avoiding any restrictions docker might have upon using the `-m` flag. |
|  | "$HOME/shinobiConfig":'/config':'rw' | Volume Map for custom configuration files. |
| -v | "$HOME/shinobiCustomAutoLoad":'/customAutoLoad':'rw' | Volume Map for Shinobi customAutoLoad modules. |
| -v | "$HOME/shinobiDatabase":'/var/lib/mysql':'rw' | Volume Map for Database information. User, Monitor, Logs, etc. |
| -v | "$HOME/shinobiVideos":'/shinobi/videos':'rw' | Volume Map for Video file storage. |
