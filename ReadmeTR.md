![image](https://github.com/user-attachments/assets/b46a99e1-9972-4052-90cf-0a41105fe694)

| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 2++ |
| **RAM**          | 5++ GB ( 20++ )                    |
| **Disk**      | 50 TB+ NVME GB SDD                   |
| **Ağ Hızı**      | 100 Mbps (1 Gbps+ recommended) |


| Server         | Link              | Features |
|------------------|----------------------------|----------------------------|
| **Contabo**          | [Link](https://www.dpbolvw.net/click-101330552-12454592)                     | Cheap / Paypal  |
| **PQ**      | [Link](https://pq.hosting/?from=627713)                  | Cheap / Crypto Payment |
| **NetCup**          | [Link](https://www.netcup.com/en/?ref=261820) | Cheap / Paypal |

## Proje Sosyal Medyaları : 
- Twitter : https://x.com/BlockcastNet

## 1. Server Güncelleme : 

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Paketleri İndirelim:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file unzip lz4 -y
```

## 3. Docker ; 

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
docker version
```

## 4. Docker Compose : 

```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -L "https://github.com/docker/compose/releases/download/$VER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## 5. Docker Kullanıcı İzinleri Veriyoruz

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```
## Dosyaları İndirelim : 

```bash
git clone https://github.com/Blockcast/beacon-docker-compose.git
cd beacon-docker-compose
```

- 8080 Portu dolu Olanlar için 8089 ; 

```bash
curl -o $HOME/beacon-docker-compose/docker-compose.yml https://raw.githubusercontent.com/FurkanL0/Blockcast/refs/heads/main/docker-compose.yml
```

- Sunucu yeni 8080 Portu Boş Diyenler İçin ; 

```bash
curl -o $HOME/beacon-docker-compose/docker-compose.yml https://raw.githubusercontent.com/FurkanL0/Blockcast/refs/heads/main/mainport/docker-compose.yml
```

## Başlatalım ; 
```bash
docker compose up -d
```

## Node ID Oluşturalım ; 

```bash
docker compose exec blockcastd blockcastd init
```
