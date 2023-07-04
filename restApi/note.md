<details>
  <summary>
    <b>API(Application programming interface)</b>
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
    <b>REST API NEDİR?</b>
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
    <b>REST Prensipleri (Kısıtlamaları) I</b>
  </summary>
<h6>İstemci - Sunucu (Client - Server) Prensibi</h6>
 
İstemci isteği gönderen, sunucu da ilgili cevabı veren durumundadır. Birbirlerinin sorumluluk alanlarına girmezler. Birbirlerinden bağımsız programlama dilleri ve teknolojiler kullanabilirler.
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/ReqRes.png"/>
  <h6>Tek Tip Arayüz (Uniform Interface) Prensibi</h6>
 
  Aynı kaynağa yönelik olan tüm istekler, isteğin nereden geldiğinden bağımsız olarak aynı şekilde görünmelidir. Bu aynı zamanda istemci – sunucu bağımsızlığını da destekler. 4 temel özelliği bulunmaktadır.
  <img src="https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/UniformInterface.jpg"/>
  <b>Durumsuzluk (Statelessness) Prensibi</b>
  <h6>STATE</h6>
  <ul>
    <li>Söz konusu veriyi - durumu belirtir, örneğin bir veritabanı için düşünürsek veritabanında o an için bulunan veridir. Bir React uygulamasını düşünürsek herhangi bir component’ın o an ki durumu. Modal’ın açık veya kapalı olması, kullanıcının giriş, çıkış durumu gibi.</li>
    <li><b>Stateful</b>( Durum bilgisi olan ) vs <b>Stateless</b> ( Durum bilgisi olmayan ) İstemci tafından gerçekleştirilen her istek birbirinden bağımsızdır ve sunucu bu isteklerin her birini bağımsız olarak değerlendirir. Sunucu istemci tarafından kendisine gönderilen bilgileri tutmamalıdır. Örneğin bir isteğimiz kimlik doğrulama (Authentication) işlemi gerektiriyorsa ilgili tüm bilgiler (token vs..) istemci tarafından sunucuya devamlı olarak gönderilmelidir.</li>
    
  </ul>
</details>
