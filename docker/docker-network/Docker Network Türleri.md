## Network Türleri 

**Bridge Network**
> **docker run mongo** (default olarak kullandığımız network)

**none**
> **docker run mongo --network=none** yazar isek mongoya dışarıdan ya da içerisinden erişemezsiniz. Loglarını sonradan bakmak isteyebilirsiniz


**host**
> **docker run mongo --network=host**
docker host üzerinden bağımsız bir uygulama gibi çalıştırır

**Kullanıcı tanımlı**
> **docker network create --driver bridge -- subnet 182.18.0.0/16 --getaway 182.18.0.1 todo-app-network**


```powershell

PS > docker images
PS > docker rmi imagesId or Names
İmagesId veya images name verilen images siler
```

```powershell
PS > docker network list
PS > docker network ls
```
her ikiside networlwri görüntğler

```powershell
PS > docker network rm my-network (istenilen network ü siler)
``` 

--gkandemir/todo-app örnek proje network--
> **docker network create --driver bridge --subnet 182.18.0.1/24 --gateway 182.18.0.1 custom-network**(bridge network olsun subnet(belirlediğim host  aralığı)
getaway(hangihost üzerinden anlaşsınlar)=
> docker run --name mongo-server  --net custom-network -d  mongo(net(daha önce kullanıcı tarfaından oluşturulan network adresidir) name mongo-server olmalı projemizde bu 
container üzerinden mongodb bağlantı sağlanıyor 
**NOTE:** fark tek fark değil link kullanılacak ise alias mongo-server yazdığım yerde tanımlamam gerekirdi

# --- UBUNTU NODEJS --

> **docker pull ubuntu:18.04** (ubuntunun 18.04 versiyonu yüklendi)

>  **docker run -it ubuntu:18.04** (ubuntu -it ile terminal olarak çalıştırıldı)


``` bash
root@369e4f5415d0:/# app-get uddate (ubuntu güncellemesi varsa)



>root@369e4f5415d0:/# app-get install curl -y(curlüzerinden node indireceğiz curl ubuntu içine kuruldu)
** root@369e4f5415d0:/# curl -sL https://deb.nodesource.com/setup_10.x | bash (node 10.x versiyonu indirildi)
** root@369e4f5415d0:/# apt-get install node.js -y (indirilen nodejs ubuntu üzerine kuruldu)

root@369e4f5415d0:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@369e4f5415d0:/# cd opt
root@369e4f5415d0:/opt# mkdir node-app
root@369e4f5415d0:/opt# cd node-app
root@369e4f5415d0:/opt/node-app# echo 'console.log("node.js from ubuntu");' > ,index.js (index.js dosyası oluşturuldu)
root@369e4f5415d0:/opt/node-app# ls
,index.js
root@369e4f5415d0:/opt/node-app# echo 'console.log("node.js from ubuntu");' > index.js(index .js yoksa oluşturulacak)
root@369e4f5415d0:/opt/node-app# ls
,index.js  index.js
root@369e4f5415d0:/opt/node-app# node index.js (node index.js çalıştırıldı)
node.js from ubuntu
root@369e4f5415d0:/opt/node-app# history (console getmişi görüntülendi)

```
    1  apt-get update
    2  app-get install curl -y
    3  apt-get install curl -y
    4  curl -sL https://deb.nodesource.com/setup_10.x | bash
    5  apt-get install node.js -y
    6  node
    7  no
    8  apt-get install nodejs -y
    9  no
   10  node
   11  no
   12  nodej
   13  nodejs
   14  no
   15  ls
   16  cd opt
   17  mkdir node-app
   18  cd node-app
   19  echo 'console.log("node.js from ubuntu");' > ,index.js
   20  ls
   21  echo 'console.log("node.js from ubuntu");' > index.js
   22  ls
   23  node index.js
   24  history

# -- İMAGES --
> **docker build .** 
> (dosyamda benim dockerfile dosyam var onu build et)

> **docker build . -t simple-node-app** 
 (images sonradan isim verme) 


> **npm init -y** 
package dosyası oluşturur.


> **docker run --link mongo-server:mongo-alias  -p 4000:4000 node-mongo-todo-5** 
(link ile mongodb ayağa kaldıracağız bunun için code da tanımladığımız mongo-alias ' s ulsşmsdı için 
mongo-server adında bir container var git bul  mongo-alias olarak bağlan isim değişikliği olmuş gibi)
containerlar yapacak bir şey aksiyon bulamadığı zaman çıkış yaparlar ör/docker run ubuntu işlem varsa devam eder
server açarsan dinleme yaptığı için server çalışmaya devam eder.Container ayağa kalktığında container çave lışır

> **docker run ubuntu-sleeper sleep 2**
 (CMD override edilebilen bir comuttur) Yani container ismine yazar iseniz 
ve cmd komudu run ederken yazarsanız default cmd yerine yani yazılan cmd ku

						-- 

**FROM ubuntu:18.04**

- **Enter pointte container run edilirken sleep komutu çalışır ancak sleep komutu arguman bekler çalışmak için**
  
-  **bu argüman verilmez ise hata atar
ENTRYPOINT [ "sleep" ]**

- **Eğer sleep arguman gönderilmemiş ise cmd kotu çalışacak yani 2 sn uyuyacak ve kapanacaktır 
CMD ["2"]**

- **birinci komut yani bu örnekte sleep executable yani çalıştırılabilirolalıdır**

- **CMD ovveride edilebilen bi komuttur**

- **CMD ["sleep" , "4"]**

- **shell formatında yazılabilir**
-  **CMD sleep 4**


## Python App

```docker file 

# base images olarak 
FROM python:3.8-slim

# bulunduğun dizine /server dosyası oluştur
WORKDIR /server

# yüklemek istediğin application dependencies.txt oluşturduğun /server dosyasının içine kopyala
COPY dependencies.txt .

# kopyaladığın dependencies.txt bağınmlıklarını yükle çalıştır
RUN pip install -r dependencies.txt

# appşication src/ . içine kopyala
COPY src/ .

# container ayağa kaldır
CMD [ "python" , "./server.py" ]

```

```powershell
PS \7-python-app> docker build . -t 7-python-app
```

- Bütün geçmişi siler  diğer images valume dede purse komutu işe yarayabilir
```powershell 
PS C:\Users\sefad> docker container prune
```
