<p align="center">
  <a href="https://orbisworlds.org">
    <img alt="Hero" src="https://user-images.githubusercontent.com/73176377/221690244-0a1cbc8a-895c-4d91-82c4-5d6189763ade.png" width="75%" />
  </a>
</p>

## Tavsiye Edilen Sistem Gereksinimleri
- CPU: 2-4 ÇEKİRDEK
- RAM: 16 GB
- SSD: 250 GB
- İşletim Sistemi: Ubuntu 20.04LTS

- Öncelikle ağı Metamask'a aşağıdaki linke tıklayıp ss'de göründüğü gibi butona tıklayarak ekliyoruz.
   - https://docs.shardeum.org/network/endpoints

![1](https://user-images.githubusercontent.com/73176377/221692468-9d6f9cc4-b2d9-46bd-a1c9-dbe4aeb64050.PNG)

- ÖNEMLİ > Buradan itibaren gerçekleştirilen kurulumun sorunsuz yapılabilmesi adına videonun izlenmesi en iyi yoldur.
   - Video > https://youtu.be/GKW0OHt9wJQ

## Yükleme Kodları
 ### Güncelleme
```
sudo apt update && sudo apt upgrade -y && sudo apt-get install curl
```
 ### Docker Kurulumu
```
sudo apt install docker.io -y
``` 
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose
```

 ### Node Kurulumu
```
curl -O https://gitlab.com/shardeum/validator/dashboard/-/raw/main/installer.sh && chmod +x installer.sh && ./installer.sh
```
- Size sorduğu sorularda vereceğiniz cevaplar sıralı şekilde şöyle
   - y
   - y
   - Kendi belirlediğiniz bir şifreyi girin. Mutlaka bir yerde kayıtlı olsun.
   - Kullanıcak olan portu soruyor, en uygunu 8080 girmektir
   - Bir şey yazmadan "enter" a bas
   - Bir şey yazmadan "enter" a bas
   - Bir şey yazmadan "enter" a bas
   - Görselde ki gibi bir ekran geldiğinde sorunsuz kurulum yapılmış demektir.
![11111111](https://user-images.githubusercontent.com/73176377/221731272-2576ce8f-9217-407d-99e0-f1bb7f74fb07.PNG)

```
$HOME/.shardeum/shell.sh
operator-cli gui start
```

### Stake İşlemi
   - Öncelikle https://faucet-sphinx.shardeum.org/ linkten girip tweet atarak faucet istiyorsnuz.
   - Bilgisayarımızın tarayıcısına https://NodeIp:8080 şeklinde yazıp enterlayınca "Bağlantınız gizli değil" uyarısı gelecektir. Bundan sonra en aşağıda ".... sitesine ilerle (güvenli değil)" yazısına tıklanır ve gelen sitede az önce kurulumda yazdığımız şifre ile giriş yapılır.
   - Sırayla ss'de ki işlemleri yaparak stake işlemini gerçekleştirebilirsiniz.
   - Bu bölümle alakalı videoda söylediklerim önemli. Lütfen dinleyin!

### Version Kontrol
   - 1.1 sonucunu vermeli
```
curl <server_ip>:9001/nodeinfo
```
   - Tarayıcıdan şu şekilde girerek de bakılabilir > http://nodeip:9001/nodeinfo

### 0.0.0.0 Hatası
   - Sitede bazen node bu hata yüzünden durabiliyor eğer böyle bir uyarı ile karşılaşırsanız aşağıdaki kodları sırayla girin.
```
cd ~/.shardeum
./shell.sh
```
```
export APP_IP="EXTERNAL_IP"
operator-cli stop
operator-cli start
```
```
curl https://ipinfo.io/ip
```

## 24.03.2023 - 1.1.5 Güncellemesi

- Aşağıdaki adımları sırayla yapıp güncelleme işlemini başarılı bir şekilde gerçekleştirebilirsiniz. Öncesinde Ayarlar > Gelişmiş > Hesabı sıfırla'ya giderek Metamask'larınızı sıfırlamalısınız.

```
exit #eğer root da değilseniz ve container içindeyseniz bunu girin yoksa atlayabilirsiniz
cd
curl -O https://gitlab.com/shardeum/validator/dashboard/-/raw/main/installer.sh && chmod +x installer.sh && ./installer.sh
```
- Bu işlemden sonra [38.](https://github.com/okannako/shardeum/blob/main/README.md#node-kurulumu) satırdan itibaren işlemleri gerçekleştiriyoruz.
