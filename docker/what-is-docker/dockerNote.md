
# What is docker?
 Images find docker hub[^1]

> **docker pull [The applicaton's image's name]**

> **docker images** (The code show image listed)

`IMAGES IDE` (The docker puts uniqu ide)23182420ff08

> **docker run -it ubuntu** (Ubuntu start)

> **docker run sleep 10** ( Ubuntu start later 10 sn close)

> Open ubuntu later(*cd etc (later) * ls (later) *cat os-realease(ubuntu version) *exit (ubuntu exit)

**NOTE:** Sunucularımız **up**  oldumu veya **ayağa kalktımı** tabirleri application çalıştırıldığı anlamında kullanılır

> **docker ps** (Ayakta olan sunuxcuları gösterir) 

ya da 

> **docker container ls**(Aktif containerların listesi ps ile aynı işi yapar)

> **docker ps -a**(Geçmişe yönelik çalışan containerları gösterir)

 ya da
 
> **docker container ls -a**
 
**NOTE:** her çalıştırmada application aynı olsa bile her seferinde farklı container oluşturur ve names de farklı olur. İstinası sizin kendi containerınızı oluşturmanızdır


> **docker run -it --name bash_ubuntu ubuntu** 
 containerlara yeni ad verdik çalışacak image adı her zaman komut satırın sonunda olur

> **docker start bash_ubuntu** (Yukarıda containerı isilendirmiştik şimdi ise onu çalıştırıyoruz burda ubuntu arkada çalışıyor olacaktır dikkat)

> **docker stop bash_ubuntu** (isimlendirilmiş veya kendi atadığı isme veya container id veya container id iki karakteri göre de kapatabiliriz container kapatır) geçmişte kullanılan ve kendi adlandırdığımıxz images imageleri


  
> **docker start  [container name]** (Kullanılarak çalıştırılabilir)


> **docker rm [(image Id)** veya **(container name)]** tamamen containerı kaldırır. bireden fazla silmek içim 

> **docker rm** (**imageId** veya **containerName** yan yana yazabilirsiniz)

> **docker container rm $(docker container ls -aq)**    Bütün containerlerlı siler

> **docker run redis:6** (bu komut redis in 6 versiyonunu localde arar bulamazsa indirir çalıştırır yano versiyon kıs mı TAG dır TAG göre versiyon farklılaştığı için önemli
redis tamam ama hangi TAG sahip)

> **docker image tag ubuntu my-ubuntu** (bu komut var olan image tag ın adını değiştirmeden aynısını yeni adla gösterir)


> **docker run -d redis** (---detach mode arka planda çalışır containerId ekrana yazar)


> **docker attach [containerId or names]** logarı tekrar gösterir


> **docker run -d gkandemir/counter-app** (gkandemir/counter-app uygulaması saniyede bir loglama yaparak tarihi ve saati basıyor
bu uygulama eğer

> **docker run gkandemir/counter-app** olarak çalışırsa bizi blocklayacak ve ekstra ram vs. yük binecektir onun için -d detach diyerek arka planda çalıştır
mamız daha doğru olacaktır)


> **docker attach 51e10b6f3464** (yukarı örnekte loglama devam ediyor mu veya logları takip etmek isteyeceksiniz o zaman bu kodu kullanmalısın entere bastıktan sonrası logları verir)


* **docker container logs [containerId]** (eğer --detach modda çalıştırdığınız moddaki yukarıdaki örneği şuandan geriye log ları kullanmak için bu komutu kullanmalısınız)


> **docker run gkandemir/interactive-terminal-app** (eğer uygulamanız kullanıcıdan bir giriş bekliyorsa giriş olmaz ise uygulama açılır ve kapanır)


> **docker run -it gkandemir/interactive-terminal-app**(Yukarıdakiuygulamayı kullanmak için -it set etmem,z gerekir)

##   PORT MAPPING

**ÖNEMLİ:** Docker yüklü imageden çalışan uygulama containerlar docker host üzerinde çalışır.
- mongoDb 
- node express
- phpmyadmin
- redis 
bu arkadaşlar b,r port üzerinden serv,**s ed,l,r**
4 tane containerımız olsun ayakta docker host kendine ait network ağı vardır. Bu containerlar aksi belirtilmedikçe **GETWAY** üzerinden aksi belirtilmedikçe
kendi Ip ye aittir 

> **docker run -p DIS_PORT:IC_PORT mongo** Dockerı image sahip örnek olarak mongoDB direk olarak ulamaşsınız bunun yolu docker host üzerinden
mongoDB bağlanmaktır DIS_PORT(Dışarda benim localhostum üzerinde porttan) , IC_PORT(Docker içerisindeki porta) ayağa kaldır. Docker host içerisinde port karşılık
bulmalı port olmayan image çalıştıramaz

> **docker run  -p 3001:3000 -d gkandemir/node-app** (gkandemir/node-app docker içerisindeki portu 3000 dir. Bu kod ile  gkandemir/node-app  localimde 3001 portta 
çalıştır dockerdaki 3000 portunda olan bu uygulamayı -d(detach) arka planda)	

## VOLUME MAPPING 
**NOTE :** Docker Host üzerinde container'lar stateless olarakaçlışırlar -> Bunu anlamı eğersiz b-veri tabsnı işlemleri yapıyor iseniz kayıtlarını tutmayacak 
her başlatma da tekralayacaktır. Bunu için doker  da bunu sağlamak için **"volume"** kullanılır.
Bu durumda host üzerinde kayıt yerini dockera belirtmemiz  gerekir.
container üzerindeki kayıt locasyonunu host üzerinde bir locasyona maplememiz gerekir **(volume mapping)**
> **docker run --name mongetest  -v/opt/data:/data/db -p  27017:27017 mongo** (dosya adı olarak mongetest olsun -v kayıt yeri -p iç dış port)
Yukarıdaki container ı tekrar ayağa kaldırmak için **docker start mongetest (kullanılabilir)
v dosyası docker üzerinde var olan izin verilen bir dosya olmal

> **docker inspect cbaacca1a8d3** (imageId ile container özelliklerini yazar) BİNDS VS bir sürü bilgi var


> **docker run --name msqltest -e MYSQL_ROOT_PASSWORD=test1234 -d mysql**  (e envaiment mysql çalışması için root_Password verdik)
**-- link --**
Çalışan iki container ı bazen birbirine bağlamka gerekir 
En önemlisi ilk olarak bağlanılacak arkadaşı çalıştırmak 

> **docker run --name mysql-server -p 3306:3306 -v /opt/data:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=test123 -d mysql**
(NAMES:mysql-server olsun , -p(dış port=3306 , dockerHubiçport:3306) -v (/opt/data:/etc/mysql/conf.d) kayıt dosyası -e (.env root pasaportu) -d(-d detach mode çalışsın))

Sonra ise bağlanacak container ı bağlamak
> **docker run --name phpmyadmin -p 8000:80 --link mysql-server:db  -d  phpmyadmin/phpmyadmin** 
(NAMES: phpadmin ) -p (dış:8000:80-iç:80) link (önemli bağlanılacak images NAMES ve db:alias yani NAMES verilen images host üzerindeki yere götür demek)

[^1]: [Docker hub](https://hub.docker.com/)