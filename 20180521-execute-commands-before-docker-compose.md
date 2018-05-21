# Execute commands before docker compose
Simple solution, create a shell script and run your commands there (duh).

Example, ensure an external docker network is created before we build and start our containers.

```
#!/bin/bash
PROJECT="cool-project-1"
NETWORK_NAME="proxy-network"

echo "Starting project $PROJECT"

echo "Checking network $NETWORK_NAME exists"

# create the njc network if it doesnt exist
if [ ! "$(docker network ls -q -f name=$NETWORK_NAME)" ]; then
   # create the network
   echo "Network $NETWORK_NAME does not exist, creating"
   docker network create "$NETWORK_NAME"
fi

# start and build the containers
docker-compose up --build
```
