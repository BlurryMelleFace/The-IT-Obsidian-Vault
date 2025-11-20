## Login
1.  docker login into the siemens package registry 
```shell
docker login cr.siemens.com
```
## Update

1. Pull Network Generation Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/network-generation:latest 
```

1. Pull Connection Generation Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/connection-recognition:latest
```

1. Pull pid-api Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/pid-api:latest 
```

1. Pull pid-bff Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/pid-bff:latest 
```

1. Pull Symbol-Recognition Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/symbol-recognition:latest
```

1. Pull Text-Recognition Code

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/text-recognition
```

1. All Together

```shell
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/network-generation:latest
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/connection-recognition:latest
docker pull cr.siemens.com/ipid-recognition-product/components/pid-api:latest
docker pull cr.siemens.com/ipid-recognition-product/components/pid-bff:latest
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/symbol-recognition:latest
docker pull cr.siemens.com/ipid-recognition-product/components/ai-recognition-models/text-recognition
```
FOR UPDATING (pid-aip example)
dev
```shell
docker build . -t cr.siemens.com/ipid-recognition-product/components/pid-api:latest --build-arg POETRY_HTTP_BASIC_IPID_RECOGNITION_USERNAME=<> --build-arg POETRY_HTTP_BASIC_IPID_RECOGNITION_PASSWORD=<>
```

## Test On Local

2. Execute Docker Compose Build Command in Repository
```shell
docker compose build --build-arg POETRY_HTTP_BASIC_IPID_RECOGNITION_USERNAME=<> iPID --build-arg POETRY_HTTP_BASIC_IPID_RECOGNITION_PASSWORD=<>
```
3. Execute Docker Compose Up
```shell
docker compose up
```

4. Execute Docker Compose Pull
```shell
docker compose pull
```
## Debug

4.  Get all Processes
```shell
docker ps
```
5.  Log Process
```shell
docker logs <id>
```
6.  See Contents in Terminal
```shell
docker exec -it <container_id> /bin/bash
```
1.  Kill the Processes
```shell
pkill -f rancher-desktop
```

## Storage

2. Prune unused Docker images:
   ```shell
   docker images --filter "dangling=true"
   ```

3. Remove unused docker images:
   ```shell
   docker image prune -f
   ```
4. Remove exited containers:
   ```shell
   docker container prune -f
   ```
5. Remove all unused containers and images:
   ```shell
   docker system prune -a -f
   ```
## Login
6.  Rebuild Containers
```shell
docker-compose down -v
```
```shell
docker-compose up --build
```
## JQ
7.  Install JQ for a Pretty Code Formatter / Reader in an Ubutu based Virtual Box
```shell
apt update && apt install -y jq

```
8. Execute the JQ command to read out a File
```shell
jq . text_recognition_results.json
```

## Status
1.  Status of Docker
```shell
dockerstatus.com
```