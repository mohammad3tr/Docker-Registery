## Docker-Registery by using letsencrypt CA



## Server side Config :
```
sudo apt-get update
sudo apt-get install certbot
sudo certbot certonly --standalone -d <your domain address>
ls  /etc/letsencrypt/live/
ls /etc/letsencrypt/archive/

cd Docker-Registery
mkdir certs
cp fullchain.pem  privkey.pem in certs directory
docker-compose up -d

```


## client side config :
```

1- Touch  /etc/docker/daemon.json
2- vim  /etc/docker/daemon.json

{
    "registry-mirrors": ["https://<your repository URL>"],
    "log-opts": {
        "max-size": "100m"
    }
}

2- sudo systemctl daemon-reload
3- sudo systemctl restart docker.service

```

