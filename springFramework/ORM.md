# Object Relational Mapping (ORM) Nedir?

  ![image](https://user-images.githubusercontent.com/39422788/226524195-b09da96f-8b02-4ffa-8e11-8823d0873373.png)
  
  Uygulamalarımızda, geliştirdiğimiz projelerde veritabanına bağlanma ihtiyacı duyduğumuzda eskiden genellikle 
  ADO.Net denilen, veritabanına doğrudan uygulama içerisinden bağlandığımız, veritabanı işlemlerini SQL 
  sorgularıyla yaptığımız yöntem kullanılırdı. İlerleyen yazılım teknolojisi, nesne tabanlı programlama tabanlı 
  dillerin de gelişmesi ve yaygınlaşması ile ADO.net’in karmaşıklığını basite indiren ve daha okunaklı kod satırları 
  yazabildiğimiz ORM (Object Relational Mapping) yapıları ortaya çıktı.
  
  ## ORM Nedir?
  
   Ado.net kullanılan projelerde veritabanı ile ilgili yapılan işlemlerde yazılımcı doğrudan sql 
   sorguları yazmak durumundadır. ORM ile kod içerisine yazılan sql satırları ortadan kalkmıştır. 
   Veritabanımız içerisinde yer alan tablolar bir sınıf (class), kolondaki alanlarımızın her biri 
   değişken (property) olarak tanımlanmakta, veritabanındaki kayıtlara da ait olduğu sınıfta bir obje olarak 
   erişebilmekte ve kullanabilmekteyiz.
     
   Programlama dillerinin de kendine ait farklı ORM framework’leri bulunmaktadır
   ** Dillere göre sık kullanılan ORM örnekleri;**

- C#: Entity Framework,  Dapper, ECO, XPO, Norm
- Java: Hibernate, Ebean, Torque, JPA,MyBattis
- Php: CakePHP, Codelgniter, RedBean, Doctrine,Propel, PdoMap
- Python: Django, South,Storm

 ORM’nin sağladığı kolaylık ne diyecek olursak eğer bir örnek üzerinden gidebiliriz.

 Id’sini bildiğimiz bir kullanıcının ismini almak isteyelim. Bunun için ado.net kullanılan bir projede aşağıdaki gibi bir kod sırası izlenmesi gerekmekteydi.
       
 ```C#
string sql = "SELECT FirstName FROM Accounts WHERE Id = 7";
DbCommand cmd = new DbCommand(connection, sql);
Result result = cmd.Execute();
string firstName = result[0]["FirstName"];
```

 ORM tabanlı bir yapıda ise aynı işlemi aşağıdaki gibi yapabiliriz.
```C#
Account kullanici = repository.GetAccount(7);
string isim= kullanici.FirstName;
```

## ORM kullanmanın avantajları
- Nesne tabanlı programlama standartlarına uygun olarak kod yazma imkanı verir.
- Minimum SQL bilgisi ile veritabanı işlemleri yapmak imkanı tanır.
- Veritabanı platformu bağımlılığı yoktur. Oracle kullanıyorken MSSQL geçişini sorunsuzca gerçekleştirebiliriz.
- Ado.net’e karşı daha güvenlidir. Sql Injection gibi bilinen saldırılara karşı güvenlik önlemleri vardır.
- Kod yazma süresini kısaltır.
- Kod okunabilirliğini arttırır.

## ORM kullanmanın dezavantajları
- Ado.net’e kıyasla performans olarak daha yavaştır.
- Veritabanı nesneler üzerinden modellendiğinden nesneler arasında bağ bulunmaktadır. Bilinçsiz yapılan müdahaleler ile bağlantıyı bozma durumu bulunmaktadır.
- İlk kez başlayacak olanlar için yazım kuralları (syntax) farklı gelebilir.

[Yararlanılan Kaynak](https://caylakyazilimci.com/post/object-relational-mapping-orm-nedir)
 
 
