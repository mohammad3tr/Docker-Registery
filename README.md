# Docker-Registery
```
"This docker registry is a place to bypass Iranian internet filtering and you can have your own docker repository."

1- Touch  /etc/docker/daemon.json
{
    "registry-mirrors": ["http://a.b.com:7000"],
    "log-opts": {
        "max-size": "100m"
    }
}

2- sudo systemctl daemon-reload
3- sudo systemctl restart docker.service
```
