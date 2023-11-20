# Docker-Registery
```
This Docker registry is a place to ignore Iranian internet filtering
```
1- Touch  /etc/docker/daemon.json
{
    "registry-mirrors": ["http://mohammad-tayebi.ir:7000"],
    "log-opts": {
        "max-size": "100m"
    }
}

2- sudo systemctl daemon-reload
3- sudo systemctl restart docker.service
