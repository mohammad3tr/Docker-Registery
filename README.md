## Docker-Registery by using letsencrypt CA



## Server side Config :
```
1- sudo apt-get update
2- sudo apt-get install certbot
3- sudo certbot certonly --standalone -d <your domain address>
4- 
ls  /etc/letsencrypt/live/
ls /etc/letsencrypt/archive/

5- cd Docker-Registery
6- mkdir certs
7- Copy the Fullchain1.pem and Privkey1.Pem files to the certs folder and make sure that the names of the fullchain.pem and PriavateKey.pem   are exactly the same as in the docker-compose file

8- docker-compose up -d

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

