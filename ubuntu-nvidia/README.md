# Shinobi with PlateRecognizer

### How to Install

1. Just do it.

```
docker run -d \
--name='ShinobiPR' \
 -e 'APP_BRANCH=dev' \
 -p '8080:8080/tcp' \
 -v "/dev/shm/shinobiPRStreams":'/dev/shm/streams':'rw' \
 -v "$HOME/shinobiPRConfig":'/config':'rw' \
 -v "$HOME/shinobiPRCustomAutoLoad":'/customAutoLoad':'rw' \
 -v "$HOME/shinobiPRDatabase":'/var/lib/mysql':'rw' \
 -v "$HOME/shinobiPRVideos":'/shinobi/videos':'rw' \
 'shinobisystems/shinobi:ubuntu-nvidia'
```
