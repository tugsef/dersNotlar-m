<details>
  <summary>
    <h3>API(Application programming interface)</h3>
  </summary>
<p>
  API(Uygulama ve peogramlama arayüzü)
  <br/>
  Genel olarak iki yazılımın birbiriyle iletişime geçmesidir. Bir yazılımın gerçekleştirebildiği işlemlere belirli koşullar dahilinde dışarıdan erişilip bu işlemlerin kullanılmasını sağlayan arayüzdür.
  <b>API Örnekleri
   <ul>
     <li>OOP Public Methods</li>
     <li>Node.js FS Modülü, Go(lang) FMT Paketi</li>
     <li>GitHub API (https://docs.github.com/en/rest )</li>     
   </ul> 
    API NEDİR?
    <br/>
    Özetle, bir uygulamada gerçekleştirmek istediğimiz ek bir işlemi, o işlemi sağlayan başka bir uygulamadan API kullanarak gerçekleştirebiliriz.
     <ul>
     <li>API kullanımı bizi ilgili işlemin gerektireceği iş yükünden kurtarır. “API hayatı kolaylaştırır”.</li>
     <li>API lar özel kullanıcı kitlelerine yönelik hazırlanırlar ve ilgili verileri hızlı bir şekilde oluşturmamızı sağlarlar. ( IMDB API, GitHub API ..)</li>
     <li>Platform bağımsız çalışırlar.</li>  
     <li>Güncelleme durumunda bizim yapmamız gereken işlemler sınırlıdır.</li>     
      
   </ul> 
</p>
</details>

<details>
  <summary>
    <h3>REST API NEDİR?</h3>
  </summary>
  Representational state transfer; İlgili isteğe karşılık gelen verinin JSON / XML gibi dosya formatlarında gönderilmesidir. REST API, REST mimarisinin prensiplerine taşıyan API’lardır. Tüm prensiplerin karşılanması durumunda RESTful API olarak da adlandırılır.
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-api-nedir/figures/RestApi.png"/>  
  Özetle, bir uygulamada gerçekleştirmek istediğimiz ek bir işlemi, o işlemi sağlayan başka bir uygulamadan API kullanarak gerçekleştirebiliriz.
  <ul>
    <li>İstemci – Sunucu: (Client – Server)</li>
    <li>Tek Tip Arayüz: (Uniform Interface)</li>
    <li>Durumsuzluk: (Statelessness)</li>
    <li>Önbelleklenebilir: (Cacheable)</li>
    <li>Katmanlı Sistem: (Layered System)</li>
    <li>İsteğe Bağlı Kod: (Code On Demand - Optional)</li>
  </ul>
</details>

<details>
  <summary>
    <h3>REST Prensipleri (Kısıtlamaları) I</h3>
  </summary>
<h6>İstemci - Sunucu (Client - Server) Prensibi</h6>
 
İstemci isteği gönderen, sunucu da ilgili cevabı veren durumundadır. Birbirlerinin sorumluluk alanlarına girmezler. Birbirlerinden bağımsız programlama dilleri ve teknolojiler kullanabilirler.

 <p>
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/ReqRes.png"/>
 </p>
  
  <h6>Tek Tip Arayüz (Uniform Interface) Prensibi</h6>
 
  Aynı kaynağa yönelik olan tüm istekler, isteğin nereden geldiğinden bağımsız olarak aynı şekilde görünmelidir. Bu aynı zamanda istemci – sunucu bağımsızlığını da destekler. 4 temel özelliği bulunmaktadır.
  <br/>
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/UniformInterface.jpg"/>
 <br/>
  <b>Durumsuzluk (Statelessness) Prensibi</b>
  <h6>STATE</h6>
  <ul>
    <li>Söz konusu veriyi - durumu belirtir, örneğin bir veritabanı için düşünürsek veritabanında o an için bulunan veridir. Bir React uygulamasını düşünürsek herhangi bir component’ın o an ki durumu. Modal’ın açık veya kapalı olması, kullanıcının giriş, çıkış durumu gibi.</li>
    <li><b>Stateful</b>( Durum bilgisi olan ) vs <b>Stateless</b> ( Durum bilgisi olmayan ) İstemci tafından gerçekleştirilen her istek birbirinden bağımsızdır ve sunucu bu isteklerin her birini bağımsız olarak değerlendirir. Sunucu istemci tarafından kendisine gönderilen bilgileri tutmamalıdır. Örneğin bir isteğimiz kimlik doğrulama (Authentication) işlemi gerektiriyorsa ilgili tüm bilgiler (token vs..) istemci tarafından sunucuya devamlı olarak gönderilmelidir.</li>
    
  </ul>
</details>

<details>
  <summary>
    <h3>
    REST Prensipleri (Kısıtlamaları) II
    </h3>
  </summary>
  
  <h3>Önbelleklenebilir ( Cacheable ) Prensibi</h3>

                                                
  Sunucu gelen isteklere verilen cevapların önbelleklenebilir olup olmadığını belirtmelidir. Örneğin “Cache-Control”, “Expires” gibi HTTP başlıkları önbellek ile ilgili bilgiler taşır
  <p>
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Cacheable.jpg">
 </p>
    <h4>Katmanlı Sistem ( Layered System ) Prensibi</h4>

  İstemci – sunucu arasındaki ilişki katmanlara ayrılabilir, ve bileşenler sadece ilişkili oldukları katmanlara karşı sorumlu olurlar.
  <p>
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Layered.jpeg">
  </p>
    <h4>İsteğe Bağlı Kod ( Code On Demand - Optional ) Prensibi</h4>
  Sunucu, istemci tarafına istemcinin işlevini genişletecek ek kodlar gönderebilir. Bu özellik istemci tarafında yapılması gereken işlemleri hafifletir.

Örneğin sunucu, istemci tarafına döneceği HTML dökümanın içerisine JavaScript kodları ekleyebilir.
</details>

<details>
  <summary>
    <h3>
    HTTP nedir?
     </h3>
  </summary>
  Hyper Text Transfer Protocol ifadesinin kısaltmasıdır. İstemci ile sunucu arasındaki veri akışının kurallarını belirleyen protokoldür. İstek – Cevap (request, response) modeline göre çalışır.

<p><img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/HTTP.jpeg"/></p>
<h4>REST Mimarisinde HTTP'nin Rolü</h4>
REST mimarisinin prensiplerinden ilki istemci - sunucu çalışma modelidir. Biz bir istekte bulunuruz ve sunucu isteğimize karşılık olan durumu (state) bize bir sunum (presentation) olarak gönderir. HTTP protokolü burada bu sunum transferi için kurulan iletişimin kurallarını belirler. REST mimarisine uygun API'ların neredeyse tamamında HTTP protokolü kullanılır.
<h4>HTTP Request</h4>
İstek (Request) yapısını belirtir. 4 bölümden oluşur.
<p>
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Request.png"/>
</p>
Yapılan isteğin detayları belirtilir.
<h4>HTTP Response</h4>
Cevap (Response) yapısını belirtir. 4 bölümden oluşur.
<p><img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Response.png"/></p>
Alınan cevabın detayları belirtilir.
</details>

<details>
  <summary>
    <h3>
    HTTP Durum Kodları (Status Codes)
   </h3>
  </summary>
  <br/>
  Sunucu tarafından ilgili isteğin sonucunu belirten, 3 rakamdan oluşan sayısal ifadelerdir.
  <h4>Informational responses (Bidirimsel cevaplar) (100–199tarafında o an ne olup bittiğini belirtirler) : Sunucu </h4>
  <ul>
    <li>100 Continue: İsteğin şimdiye kadar başarılı bir şekilde istendiğini , eğer devam göndermek istek istiyorsak bunu göndermemizi 
veya isteğin tamamı gönderilmiş ise yok saylmaıgerektiğini belirtir
  </li>
    <li>102 Processing:İsteğin başarılı birşekilde alındığını ancak halen bir cevap dönülmediğini belirtrir.   </li>
  </ul>

  <h4>Successful responses (Başarılı cevaplar) (200–299)</h4>
  <ul>
    <li>200 OK : Gönderilen isteğe karşı başarılı bir yanıt verildiğini brlirtir. Gelen cevabın işlenebileceği anlamına gelir.</li>
    <li>201 Created : Sunucu tarafında yeni birkaynak oluştrulduğunu belirtir yeni bir kullanıcı veya ürün ekleme vb.</li>
    <li>204 No Content : Gönderilen cevabın bir body olmaz. Delete işlemi örnek verilebilir</li>
  </ul>

  <h4>Redirections (Yönlendirme cevapları) (300–399) : İstediğin tam olarak yerine getirilebilmesi için kalıcı ya da geçici yönlendirmeler yapılmalıdır.</h4>
  <ul>
    <li>300 Multiple Choice : Çok seçmeli bir duruma karşılık gelir bir video istediğinde bulunduğumuzu varsayalım bu videonun farklı farklı uzantıları olabilir.farklı uzantılar için 300 döner.</li>
    <li>301 Moved Permanently :Kaynak adresinin kalıcı olarak değiştirildiğini belirtir.Yeni adreste ise bize gönderilen cevapta bulunmaktadır</li>
    <li>304 Not Modified : Değişiklik yok anlamına gelir genelde değişiklik yok anlamına gelir.</li>    
  </ul>

  <h4>Client errors (İstemci Hataları) (400–499)</h4>
  <ul>
    <li>400 Bad Request : Eksik istek bilgisi gönderildiğinde</li>
    <li>401 Unauthorized :İstemci bu istekte bulunurken gerekli kimlik doğrulamasını yapmamıştır. </li>
    <li>403 Forbidden : Yetkimi olmayan bir işlemi yapmak istiyoruz demektir.</li>
    <li>404 Not Found : O an için bulunmayan kaynağa istekte bulunduğumuzzaman</li>
    <li>405 Method Not Allowed :sadece GET request izin verilen bir kaynağa POST isteği yapmaya çalıştığımız zaman </li>    
  </ul>

  <h4>Server errors (Sunucu Hataları) (500–599)</h4>
  <ul>
    <li>500 Internal Server Error: İstemci taraından istek başarılı bir şekilde gönderilmiştir ancak sunucu tarafında belki yazımsal bir hatadan dolayı istenilen cevap verilememektedir</li>
    <li>503 Service Unavailable :Suncu tarafında herhangi bir bakım çalışması bulunduğunda  </li>  
  </ul>
  <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses">HTTP Status Codes - MDN</a>
</details>

<details>
  <summary>
    <h3>HTTP Metotları</h3>
  </summary>
  <ul>
    <li>Verileri almak - listelemek için kullanılan istek metodudur.</li>
    <li>http://api.example.com/users</li>
    <li>http://api.example.com/users/1</li>
  </ul>

  <h4>POST</h4>
  <ul>
    <li>Belirli bir kaynağa veri göndermek için kullanılır.</li>
    <li>http://api.example.com/users</li>
  </ul>

  <h4>PUT</h4>
  <ul>
    <li>Belirli bir kaynaktaki verinin tamamının değiştirilmesi için kullanılan metodtur.</li>
    <li>http://api.example.com/users/1</li>
    <li>{ “name": "Gurcan", "age": 40}</li>   
  </ul>

  <h4>PATCH</h4>
  <ul>
    <li>Belirli bir kaynaktaki verilerin bir kısmının değiştirilmesi için kullanılan metodtur.</li>
    <li>http://api.example.com/users/1</li>
    <li>{ "name": "Gurcan"}</li>   
  </ul>

  <h4>DELETE</h4>
  <ul>
    <li>Belirli bir kaynaktaki verilerin silinmesi için kullanılan metodtur.</li>
    <li>http://api.example.com/users/1</li>
  </ul>

  <h4>CONNECT - TRACE - OPTIONS - HEAD</h4>
  <h4>SAFE Metotlar</h4>
  GET – HEAD – OPTIONS : Sunucu “state” tarafında değişiklik oluşturmazlar. “Read-only(Yalnızca verileri okumak için)” yapısındadırlar.
  <h4>IDEMPOTENT(Etkisiz) Metotlar</h4>
  GET – HEAD - OPTIONS – DELETE – PUT – TRACE : Tekrar durumunda sunucu state yapısında herhangi bir yan etki bırakmazlar. Safe metodlar, idempotent'tır.
  <h4>Endpoint (Sorgu Adresi)</h4>
REST API kullanımında gönderilen istek ile verilen cevap için belirlenen buluşma noktasıdır.

Root(Base) /Path yapısından oluşur, isimler kullanılır, fiil ilgili HTTP metodu ile belirtilir. Dökümantasyon tarafından belirtilir.

<ul>
  <li>https://jsonplaceholder.typicode.com /posts</li>
  Değişen değer için genelde (:) kullanılır.
  <li>https://jsonplaceholder.typicode.com/posts/1 => /posts/:id veya /posts/{{id}}</li>
  <li>https://jsonplaceholder.typicode.com/posts/1/comments</li>
  Sorgu parametreleri için (?) kullanılır.
  <li>Aslında sorgu parametreleri REST yapısının bir parçası değildir ancak sorgu adreslerinde sıkça rastlarız.</li>
  <li>http://example.com/articles?sort=author&date=published</li>
</ul>
  
 <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods">HTTP Methods - MDN</a>
</details>

<details>
  <summary>
    <h3>JSON Nedir?</h3>
  </summary>
  <p>JavaScript Object Notation ifadesinin kısaltmasıdır. Veri depolamak veya veri iletmek için kullanılan metin tabanlı bir söz dizimi yapısıdır. Genellikle bir sunucu ve istemci arasında veri alışverişi için veya yazılımların genel ayarları için kullanılan bir formattır.</p>
  <ul>
    <li>Drupal/config.json</li>
    <li>Node.js/package.json</li>
    <li>https://jsonplaceholder.typicode.com/users</li>
  </ul>
  <h3>JSON Veri Tipleri</h3>
  <ul>
    <li>String: "Sample String", "test1234", "A"</li>
    <li>Number: 7, 3.2, -97.238</li>
    <li>Boolean: true, false</li>
    <li>Null: null</li>
    <li>Array: [2,3,5,7] , ["İstanbul", "Ankara", "İzmir"] Array içerisinde kullanılan değerler sıralı olarak listelenebilir.</li>
    <li>Object { "name": "Gürcan", "age":40 } JSON nesneleri verileri key-value çiftleri olarak tanımlar.</li>    
  </ul>
  <p>
    Yukarıda görmüş olduğunuz veri tiplerinin tamamı tekil olarak uygun bir JSON formatı işlevini görür. Ancak tek bir 3, string veya true gibi ifadeler için ayrı bir .json uzantılı dosya oluşturmak mantıklı değildir. Bu nedenle JSON doayaları bir array, nesne ve/veya bunların içiçe geçmiş formlarından oluşur.
  </p>

<h3>Örnek :</h3>
movie.json
<code>
  {
    "id":1,
    "title": "Matrix",
    "actors": ["Keanu Reeves",  "Carrie Anne Moss"],
    "published_year": 1999,
    "genre": {
      "id": 6,
      "name": "Action"
    },
    "rating": 7.9
} 
</code>
  JSON dosyasının uygun formatta olup olmadığını kontrol etmek için JSONLINT ( https://jsonlint.com/ ) gibi çevrimiçi araçlar kullanabiliriz.
  Daha Fazlası İçin

  <a href="https://www.json.org/json-en.html">JSON.ORG<a>
</details>

<details>
  <summary>
    <h3>JSON - JavaScript - XML</h3>
  </summary>
  <h3>JSON vs JavaScript</h3>
  JavaScript web uygulamalarında sıklıkla kullanılan dinamik bir programlama dilidir. JSON ise bir söz dizim olarak JavaScript'in bir alt kümesi olarak düşünülebilir. Bu nedenle uygun JSON formatındaki bir içerik JavaScript ifadesine (expression) denk gelir.
  <code>
    {
    "id":1,
    "title": "Matrix",
    "actors": ["Keanu Reeves", "Carrie Anne Moss"],
    "published_year": 1999,
    "genre": {
      "id": 6,
      "name": "Action"
    },
    "rating": 7.9
} 
  </code>
  şeklindeki JSON söz dizimini bir JavaScript değişkenine atadığımızda, değişken değer olarak bir JavaScript nesnesini almış olur. JSON formatında key ifadelerin çift tırnak içerisine alınması zorunludur. Her ne kadar JSON söz dizimi olarak kendisine JavaScript'i örnek aldıysa da kullanımı bir çok programlama dili tarafında yaygındır.
<h3>JSON vs XML</h3>

<h3>XML</h3>
eXtensible Markup Language ifadesinin kısaltmasıdır. Veri depolamak ve iletmek için kullanılan bir script dilidir. 1998 yılında W3C tarafından standartlaştırılmıştır.
<code>
  <breakfast_menu><food><name>Belgian Waffles</name><price>$5.95</price><description>
        Two of our famous Belgian Waffles with plenty of real maple syrup
     </description><calories>650</calories></food>
</breakfast_menu>
</code>
Genel olarak ağaç yapısına (tree structure) sahiptir. Veriler açılış ve kapanış etiketlerinin içerisinde bulunur. Dıştaki etiket, içtekinin "parent"ı, içteki etiket ise dıştakinin "child"ı şeklinde düşünülür.
JSON formatının XML formatına göre en büyük avantajı, doğalında bir nesne modeline sahip olmasıdır. Bu özellik sayesinde birçok programlama dili JSON verileri daha kolay bir şekilde işleyebilir.
</details>
