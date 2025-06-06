![image](https://github.com/user-attachments/assets/b46a99e1-9972-4052-90cf-0a41105fe694)

| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 2++ |
| **RAM**          | 5++ GB ( 20++ )                    |
| **Disk**      | 50 GB+ NVME GB SDD                   |
| **Ağ Hızı**      | 100 Mbps (1 Gbps+ recommended) |


| Server         | Link              | Features |
|------------------|----------------------------|----------------------------|
| **Contabo**          | [Link](https://www.dpbolvw.net/click-101330552-12454592)                     | Cheap / Paypal  |
| **PQ**      | [Link](https://pq.hosting/?from=627713)                  | Cheap / Crypto Payment |
| **NetCup**          | [Link](https://www.netcup.com/en/?ref=261820) | Cheap / Paypal |

## Proje Sosyal Medyaları : 
- Twitter : https://x.com/BlockcastNet

# BlockCast Kayıt ; 

- Link : https://app.blockcast.network?referral-code=MddGFc
- Sağ Üstten profile tıklayın.

- ![image](https://github.com/user-attachments/assets/4b302806-3bb5-48dd-9fa0-d1bc72e578c5)

- Solana cüzdan adresinizi bağlayın. - X ve DC Bağlayın.
- ![image](https://github.com/user-attachments/assets/99603680-81a8-409b-863f-8609d288566c)


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

![image](https://github.com/user-attachments/assets/847e5bda-bf80-4e6a-90b9-c10d211954fc)

- Bitmesini bekliyoruz.

![image](https://github.com/user-attachments/assets/6027dddf-f47c-4c25-9914-12cd9910bc4d)


## Node ID Oluşturalım ; 

```bash
docker compose exec blockcastd blockcastd init
```

#### Bize Bazı Bilgiler Verecek ; 

- Bilgileri kaydedin.

- Hardware ID: xxxxxxxxxxxxxxxxxxx
- Challenge Key: xxxxxxxxxxxxxxxxxxx
- Register URL : https://app.blockcast.network/register?hwid=

![image](https://github.com/user-attachments/assets/d8f147d2-d755-4a83-a8d7-a9fb00854f3c)

- Linki Blockcast  kayıt olduğunuz tarayıcıda açın.

![image](https://github.com/user-attachments/assets/a47c7757-a084-470d-80d8-84a2123cd413)

- Sunucu Lokasyon Bilgilerinizi girin.

#### Lokasyon Bilgisi 
```bash
curl http://ip-api.com/json/
```
![image](https://github.com/user-attachments/assets/395280ed-5e71-4dbf-ac4b-efc944d1dd86)

- Ayarlayıp Register Node'a tıklayın.

## Node Kontrol : 

- Link : https://app.blockcast.network/manage-nodes

![image](https://github.com/user-attachments/assets/3126ba10-0ea8-41ee-8096-a5261b2ce1c1)


## Node Güncelleme : 

```bash
cd beacon-docker-compose
git pull origin main
docker compose down
docker compose up -d
```

## Private Key Kaydetme : 

- ~/.blockcast/certs/gw_challenge.key  Private Key Dosyası burada

- SFTP ile dosyayı kendi cihazınıza yedek almayı unutmayın

![image](https://github.com/user-attachments/assets/2d5e77ab-3b76-4a48-8a91-2133dd235cc5)


## Durdurma : 

```bash
cd $HOME
cd beacon-docker-compose
```
```bash
docker compose down
```
