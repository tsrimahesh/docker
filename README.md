# docker
docker rm -v $(docker ps  -a -q  -f status=exited)

docker rmi $(docker images -f "dangling=true" -q)

docker volume rm $()

docker images | grep "pattern" | awk '{print $1}' | xargs docker rmi

docker volume ls -f dangling=true

docker volume rm $(docker volume ls -f dangling=true -q)
Remove all untagged images
docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
