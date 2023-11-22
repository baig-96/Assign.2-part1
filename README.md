# Assignment2-Part1
Second Assignment Part 1 Attempt

1. Docker Network Creation
   docker network create my_network
   3da9afec2361e9227d5f14a96992eb86cd2ee5c6ca305b56154bddcd9a9ce318

2. Docker Container Creation using NGINX, Network Connect and tested at localhost:8080
   docker run -itd -p 8080:80 --network=my_network --name nginx_container nginx
14e02e0e17976e94c3326d3058ca4bb46b0512fdbf73bd7808f46a6f460a25f5

3. Docker Container Creation using HTTPD, Network Connect and tested at localhost:8081
docker run -itd -p 8081:80 --network=my_network --name httpd_container httpd
2bf8d278bb3ab16a3bd269371f58597849c75cf515ef299bbda8c48b327d9ae5

4. Docker Network Inspect
   docker network inspect my_network
   [
    {
        "Name": "my_network",
        "Id": "3da9afec2361e9227d5f14a96992eb86cd2ee5c6ca305b56154bddcd9a9ce318",
        "Created": "2023-11-14T06:54:50.223343523Z",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": {},
            "Config": [
                {
                    "Subnet": "172.18.0.0/16",
                    "Gateway": "172.18.0.1"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {
            "14e02e0e17976e94c3326d3058ca4bb46b0512fdbf73bd7808f46a6f460a25f5": {
                "Name": "nginx_container",
                "EndpointID": "229ec5c8f39372849a8c908d2c97b86bdef97b5198acfd9ff7038b0e021ad9cd",
                "MacAddress": "02:42:ac:12:00:02",
                "IPv4Address": "172.18.0.2/16",
                "IPv6Address": ""
            },
            "2bf8d278bb3ab16a3bd269371f58597849c75cf515ef299bbda8c48b327d9ae5": {
                "Name": "httpd_container",
                "EndpointID": "85b4ae007b47ff8cac0af37406048d986dde4510ab0ded71a5f08b8f7d15777e",
                "MacAddress": "02:42:ac:12:00:03",
                "IPv4Address": "172.18.0.3/16",
                "IPv6Address": ""
            }
        },
        "Options": {},
        "Labels": {}
    }
]

5. Docker Stop & Remove
   docker stop nginx_container
nginx_container
docker rm nginx_container
nginx_container

6. Docker Container Creation using NGINX, Network Connect and tested at localhost:8082
   docker run -itd -p 8082:80 --network=my_network --name nginx_container_2 nginx
14e02e0e17976e94c3326d3058ca4bb46b0512fdbf73bd7808f46a6f460a25f5

7. Docker Container List
   docker container ls
   CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS                  NAMES
946aea10a90b   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8082->80/tcp   nginx_container_2
2bf8d278bb3a   httpd     "httpd-foreground"       8 minutes ago        Up 8 minutes        0.0.0.0:8081->80/tcp   httpd_container

8. Docker Network Remove
   docker network rm my_network
my_network

9. README.md file created and codebase repository pushed to GitHub
    
