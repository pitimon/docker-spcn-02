# docker-spcn-02 สร้าง container template
## ทบทวนการสร้าง docker node on proxmox
- create Container Template (ubuntu22.04)
- console guest and Login
- check ip
```shell
ip a
```
- vsCode remote to guest
- ssh with key authentication
- vsCode extenstion: docker, github, wakatime

- ปรับ Timezone
```shell
timedatectl set-timezone Asia/Bangkok
```
- update packet repository
```shell
apt update ; apt upgrade -y
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
```
```shell
mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
```shell
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" |  tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```shell
apt-get update
apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

- Verify Docker Engine
```shell
docker --version
```
```shell
docker run hello-world
```
```shell
docker ps -a
```
```shell
docker images
docker system prune -a
init 0
```

- Convert to template
- Clone from template
- Verify service on new guest 
```shell
date
docker --version
docker run hello-world
docker ps -a
docker images
```
## youtube
- [docker-spcn-02](https://youtu.be/UofAy80HEz4)

