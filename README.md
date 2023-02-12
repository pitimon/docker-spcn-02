# docker-spcn-02
 
## ทบทวนการสร้าง docker node on proxmox
- สร้าง container template
- ปรับ Timexone
```shell
timedatctl set-timezone Asia/bangkok
```
- update packet repository
```shell
apt update ; apt uograde -y
```
- Install docker
[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
```shell
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
- Verify Docker Engine
```shell
docker --version

sudo docker run hello-world
docker ps -a
docker images
docker rmi hello-world
```
- Convert to template
- Clone from template
- re-configure for new node
