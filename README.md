<h1 align="center"> Celestia-Light-Node </h1>


## 💻 Sistem Gereksinimleri

| Bileşenler | Minimum Gereksinimler | 
| ------------ | ------------ |
| CPU |	2+|
| RAM	| 4+ GB |
| Storage	| 20 GB SSD |
| Ubuntu 22 |

 ## ✅ Sistem güncellemeyle başlayalım
```shell
sudo apt update && sudo apt upgrade -y
sudo apt install curl git jq build-essential gcc unzip wget lz4 -y
```

 ## ✅ Screen yükleyelim
```shell
sudo apt install screen
```

 ## ✅ Docker yüklemelerine izin verelim
```shell
sudo apt-get install docker-ce docker-ce-cli http://containerd.io
sudo docker run hello-world
```

 ## ✅ Celestia adında screen açalım
```shell
screen -S celestia
```

 ## ✅ Light Node dosyalarını yükleyelim
```shell
export NETWORK=celestia
export NODE_TYPE=light
export RPC_URL=http://public-celestia-consensus.numia.xyz
docker run -e NODE_TYPE=$NODE_TYPE -e P2P_NETWORK=$NETWORK \
    ghcr.io/celestiaorg/celestia-node:v0.13.7 \
    celestia $NODE_TYPE start --core.ip $RPC_URL --p2p.network $NETWORK
 ```

 
