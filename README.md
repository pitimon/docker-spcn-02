# docker-spcn-02
 
## ทบทวนการสร้าง docker node on proxmox
- สร้าง container template
- ปรับ Timezone
```shell
timedatctl set-timezone Asia/Bangkok
```
- update packet repository
```shell
apt update ; apt uograde -y
```
- Install docker
[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
```shell
apt-get update
apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release -y

mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" |  tee /etc/apt/sources.list.d/docker.list > /dev/null

apt-get update
apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

- Verify Docker Engine
```shell
docker --version

sudo docker run hello-world
docker ps -a
docker images
docker system prune -a
```

- Convert to template
- Clone from template
- re-configure for new node
- 
