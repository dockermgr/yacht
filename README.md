# Welcome to dockermgr yacht installer 👋
  
## Web interface for managing __sudo dockercontainers with an emphasis on templating
  
### Requires scripts to be installed

```shell
 sudo bash -c "$(curl -LSs <https://github.com/dockermgr/installer/raw/main/install.sh>)"
 dockermgr --config && dockermgr install scripts  
```

#### Automatic install/update  

```shell
dockermgr install yacht
```


#### Manual install

```shell
git clone https://github.com/dockermgr/yacht "$HOME/.local/share/CasjaysDev/dockermgr/yacht"
bash -c "$HOME/.local/share/CasjaysDev/dockermgr/yacht/install.sh"
```
  
#### Just run it

```shell
mkdir -p "$HOME/.local/share/srv/docker/yacht/"

git clone <https://github.com/dockermgr/yacht> "$HOME/.local/share/CasjaysDev/dockermgr/yacht"

cp -Rfva "$HOME/.local/share/srv/docker/yacht/dataDir/." "$HOME/.local/share/srv/docker/yacht/"

sudo docker run -d \
--name="yacht" \
--hostname "yacht" \
--restart=unless-stopped \
--privileged \
-e TZ="${TZ:-${TIMEZONE:-America/New_York}}" \
-v "$HOME/.local/share/srv/docker/yacht/data":/data \
-v "$HOME/.local/share/srv/docker/yacht/config":/config \
-p 8000:8000 \
selfhostedpro/yacht 1>/dev/null
```

## Author  

👤 **Jason Hempstead**  
