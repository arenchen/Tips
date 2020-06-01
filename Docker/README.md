# Docker-Tips
## Maintenance
### Remove all images and containers
```shell
# Delete all containers
sudo docker rm $(sudo docker ps -a -q)

# Delete all images
sudo docker rmi $(sudo docker images -q)
```

### Re-Build
```shell
docker-compose rm -f && docker-compose build --no-cache &&  docker-compose up -d --force-recreate
```
