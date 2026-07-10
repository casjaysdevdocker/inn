## 👋 Welcome to inn 🚀  

inn README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update inn
```
  
## Install and run container
  
```shell
dockerHome="/srv/$USER/docker/casjaysdevdocker/inn/inn/latest/rootfs"
mkdir -p "/srv/$USER/docker/inn/rootfs"
git clone "https://github.com/dockermgr/inn" "$HOME/.local/share/CasjaysDev/dockermgr/inn"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/inn/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-inn-latest \
--hostname inn \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/inn:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/inn
    container_name: casjaysdevdocker-inn
    environment:
      - TZ=America/New_York
      - HOSTNAME=inn
    volumes:
      - "/srv/$USER/docker/casjaysdevdocker/inn/inn/latest/rootfs/data:/data:z"
      - "/srv/$USER/docker/casjaysdevdocker/inn/inn/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/inn
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/inn" "$HOME/Projects/github/casjaysdevdocker/inn"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/inn"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
