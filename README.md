# Wireguard server

1. Copy project files to server:
```bash
$ scp -r ./* root@server-ip:/root/wireguard
```

2. Login to server by SSH:
```bash
$ ssh root@server-ip
```

3. Install Docker and Docker-Compose:
```bash
$ apt install docker.io
$ curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose
$ ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

4. Start "wireguard":
```bash
$ cd /root/wireguard
$ docker-compose up -d
```

5. Generate QR-code for peer connection:
```bash
$ docker exec -it wireguard /app/show-peer 1
```

6. Configuration files for desktop clients are located in `/wireguard/config` folder. 

Sources:

- https://igancev.ru/2021-02-21-vpn-wireguard-docker
- https://github.com/linuxserver/docker-wireguard
