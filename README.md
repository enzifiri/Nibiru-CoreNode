<h1 align="center"> ÖDÜLLÜ Nibiru Node kurulum ve Görevler </h1>
<div align="center">


![nibiru](https://user-images.githubusercontent.com/76253089/222176097-583a0546-8108-47b9-a0b6-93c09e557676.jpg)


Herhangi bir sorunla karşılaşırsanız Telegram Sohbet Grubumuza bekleriz [Core Node Chat](https://t.me/corenodechat)

  
</div>

### Sunucuyu Güncelleyerek Başlayalım
```
sudo apt update 
```
```
sudo apt upgrade -y
```

### Gerekli Portları kuralım.
```
sudo apt install -y ufw
sudo ufw default allow outgoing
sudo ufw default deny incoming
sudo ufw allow ssh
sudo ufw allow 9100
sudo ufw allow 26656
sudo ufw allow 26657 
sudo ufw enable
```

### Otomatik Yükleme ile Nibiruyu kuralım
```
source <(curl -s https://raw.githubusercontent.com/enzifiri/core-node/main/cosmos-scripts/kurulum.sh)
```
------------
## Kurulum bittikten sonra Cüzdan Import Etme / Oluşturma

Import 
```
nibid keys add wallet --recover
```
Cüzdan Olusturma (Seedlerini bi yere not edin)
```
nibid keys add wallet
```
------------
### Nodeumuzun güncel bloğa erişmesini bekleyelim. Logları kontrol etmek isterseniz
```
sudo journalctl -u nibid -f --no-hostname -o cat
```
### Eğer Peer konusunda sıkıntı yaşarsanız alttaki komutları uygulayıp nodeu sıfırlayın ve ardından tekrar logları kontrol edin.
```
PEERS="a1b96d1437fb82d3d77823ecbd565c6268f06e34@nibiru-testnet.nodejumper.io:27656,ac163da500a9a1654f5bf74179e273e2fb212a75@65.108.238.147:27656,abab2c6f45fa865dc61b2757e21c5d2244e5bacb@213.202.218.55:26656,fe17db7c9a5f8478a2d6a39dbf77c4dc2d6d7232@5.75.189.135:26656,7e75b2249d088a4dfc3b33f386c316cb47366d2b@195.3.221.48:11656,6db03cd0732b5120c291065694bafaf9c76baf4c@213.202.247.87:26656,4f1780cd0fbcd7fc0211eab1917860d69e049d06@65.109.130.180:28656,c1b40d056e4260a9fa9d1142af1adbeec5039599@142.132.202.50:46656,ea44a000ee4df9d722a90fdf41b3990e738bdda0@65.109.235.95:26656,2dce4b0844754b467ae40c9d6360ac51836fadca@135.181.221.186:29656,e08089921baf39382920a4028db9e5eebd82f3d7@142.132.199.236:21656,88f6634eecc60b8ea89b44ebbcefe3d891ca6bb9@65.108.251.231:26656,bab9f78f1c0ccd5b4d9db13a112dcf45c60e4df1@130.193.68.154:26656,d327bb6b997a32aaa7dae5673e9a9cbad487ad09@104.156.250.70:26656,4f1af4f62f76c095d844384a3dfa1ad76ad5c078@65.108.206.118:60656,9d901d286eda108828250c0a9e65fef72ee293cd@129.146.80.192:26656,ee76ff1711d63ab37efa77cb669e21643b0f2609@65.109.39.103:26656,f2e99f5a68adfb08c139944a193e2e3a4864b038@167.235.132.74:26656,c8907a13b012e7a937cfe7d624b0fbe7ef3508b2@194.163.160.155:26656,53db2490d7f6601a55aa59e98e4d6cfd5d8a929c@51.159.187.67:36656,30e14f66fc44a55a51f36693afd754283c668953@65.108.200.60:11656,fa5c730d842aff05c3761d9c1b06107340ac7651@65.108.232.238:11656,f01ad3a75b255226499df9183ac2ebc0a40a9e05@46.4.53.207:33656,81a8383eefae628ae4bc400d52d49adfb11cb76a@65.108.108.52:11656,1c548375968f0abfac3733cae9f592468c988bf9@46.4.53.209:33656,cd44f2d2fc1ded3a63c64f46ed67f783c2d93d57@144.76.223.24:36656,b03d1ce3e97984a8b8a63a7a6ec6c5d196d81436@46.4.53.208:33656,e74f1204d65d0264547e2c2d917c23c39fcff774@95.217.107.96:36656,b88642986618adc6d47ed32db1a5f2e086da18b8@132.145.209.220:26656,79e2bfc202e39ba2a168becc4c75cb6a56803e38@135.181.57.104:11656,22d5b4919850ad71ad0a1bf7979c7dba53960689@192.9.134.157:27656,3fbc70ee59230284f834931cc8edf1e16f9659e3@65.108.43.58:27667,a3a344c1732c507f40931778225f919004392e94@52.204.188.236:26656,d3e7948a5ba3f55264f1260c1d102924616b6711@5.180.186.27:26656,98032241ea61ca6ac066b8fa508baace6678a7a3@190.2.155.67:31656,5f3394bae3791bcb71364df80f99f22bd33cc2c0@95.216.7.169:60556,f1243fd7e7f655b64d49f24b3202aab6db1341c4@167.235.21.54:29656,a08e5b25443d038b08230177456ee23196509dd5@65.109.92.79:12656,10382838df100f7817eb9c86c5da67160eefe4fc@95.216.100.241:30656,62d93ddd046e8092c3717117484ed680cbacbf0d@139.59.239.43:26656,f29c808ff578c7f3a3746b9b0b3e0504b3ee2315@65.108.216.139:26656,8ebed484e09f93b12be00b9f6faa55ea9b13b372@45.84.138.66:39656,4f1c8f3de055988bf15f21b666369287fb5230de@31.220.73.148:26656,c2c2af737665fafa38b52110e591687558fe788a@31.220.78.187:26656,aad0d897a82880e36bb909091c5878607446ab41@138.201.204.5:35656,8c1e4bd5d50f33f2d4073318fb9cf8ebaac2ceb4@185.244.183.157:26656"
sed -i 's|^persistent_peers *=.*|persistent_peers = "'$PEERS'"|' $HOME/.nibid/config/config.toml
```
```
curl -s https://snapshots2-testnet.nodejumper.io/nibiru-testnet/addrbook.json > $HOME/.nibid/config/addrbook.json
```
```
sudo systemctl restart nibid
```
```
sudo journalctl -u nibid -f --no-hostname -o cat
```
### Çıktınız Aşağıdaki Gibi ise Nodeunuz başarılı şekilde kurulmuştur. Eşleştikten Sorna Görevleri Yapmaya başlayabilirsiniz. Güncel bloğa aşağıdaki explorerden bakın.
![image](https://user-images.githubusercontent.com/76253089/222171711-5a372302-75c9-44f6-8179-0ba54036e7f2.png)
[Explorer](https://nibiru.explorers.guru/)

# Görevler (NODEUNUZ EŞLEŞİP GÜNCEL BLOĞA ERİŞMEDEN GÖREVLERE BAŞLAMAYIN HATA ALIRSINIZ)

## 1-A Delegate ve Redelegate Görevi (100 Puan)
Alttaki komutu girdikten sonra 1 Nibi Stake etmiş olacaksınız. (DEĞİŞİKLİK YAPMAYIN)
```
nibid tx staking delegate nibivaloper10gm4kys9yyrlqpvj05vqvjwvje87gln86t4u6q 1000000unibi --from wallet --chain-id nibiru-itn-1 --fees 100unibi -y -s 8
```
Sonrasında Undelege yapmamız gerekiyor. 1 Nibimizi geri alalım. (DEĞİŞİKLİK YAPMAYIN)
```
nibid tx staking unbond nibivaloper1wznwkv8m309d25n8k2lu9ayzeyq7ln9f69u3jc 1000000unibi --from wallet --chain-id nibiru-itn-1 --fees 100unibi -y -s 8
```
## 1-B Oraclea Delege Etme ve Sonrasında Ödülleri Claimleme (Üsttekinin devamı o yüzden aynı puan)
