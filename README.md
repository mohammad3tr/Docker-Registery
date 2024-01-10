## Docker-Registery

"This docker registry is a place to bypass Iranian internet filtering and you can have your own docker repository."

## Server side Config :
```
sudo apt-get update
sudo apt-get install certbot
sudo certbot certonly --standalone -d <your domain address>
ls  /etc/letsencrypt/live/
ls /etc/letsencrypt/archive/

cd Docker-Registery
mkdir certs
cp fullchain.pem and privkey.pem certs
docker-compose up -d

```


## client side config :
```
<<<<<<< HEAD
"This docker registry is a place to bypass Iranian internet filtering and you can have your own docker repository."

Server side Config :
---------------------------
1- cd Docker-Registery
2- docker-compose up -d

client side config :
----------------------------
1- Touch  /etc/docker/daemon.json
2- vim  /etc/docker/daemon.json
{
    "registry-mirrors": ["http://<your repository server address>:7000"],
=======
1- Touch  /etc/docker/daemon.json
2- vim  /etc/docker/daemon.json

{
    "registry-mirrors": ["http://<your repository URL>"],
>>>>>>> bf82b21 (update)
    "log-opts": {
        "max-size": "100m"
    }
}

2- sudo systemctl daemon-reload
3- sudo systemctl restart docker.service

```

