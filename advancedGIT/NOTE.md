# Commit, Diff, Log, Amend
```
  1 - Commit, Diff, Log, Amend

Bu dersimizde çok basit bir işlem ile başlıyoruz Commit. Yaptığınız değişiklikleri bir versiyon 
olarak kayıt altına almak istediğinizde, yaptığınız değişiklikleri commit edersiniz. Bu dersimizde 
commit ile ilgili bir çok konuyu ele alıyoruz.

Bu dersimizde aşağıdaki sorulara cevap veriyoruz;

 - Commit listesini nasıl görürüz?
 - 2 commit arasındaki farkları nasıl görürüz? Nasıl yorumlarız?
 - Yaptığımız bir commit işlemini nasıl geri alabiliriz?
 - Yaptığımız bir commit işlemini nasıl silebiliriz?
 - Yaptığımız bir commit işlemini nasıl değiştirebiliriz?
 - Yaptığımız bir commit işleminin mesajını nasıl değiştirebiliriz?
 
ve çok daha fazlası bu derste sizi bekliyor!
```


 - **git branch** --> Var olan branch leri verir


 ![image](https://user-images.githubusercontent.com/39422788/221197624-f5bdd7ab-3078-4051-bd4d-8c586a141a5c.png)
 
 
- **ls -al** --> dosya içeriğini gösterir .git/  gizli olduğu için mavi renkli
- **cd .git/** -->  cd dosyalar arasında geçişi sağlar cd diyerek **.git/** dosyasına ulaşabilir 
-  **ls**  ile dosya içeriğine ulaşa bilirsiniz... 
-  **cd ..** komutu ile bir üst dosyaya geçebiliriz. 	
- **clear** komutu terminli temizler


![image](https://user-images.githubusercontent.com/39422788/221198055-3d3b3ea5-a598-4485-982d-c595427cb7c6.png)



- **git log** --> yapmış olduğum commitleri verir



![image](https://user-images.githubusercontent.com/39422788/221198134-048b08d8-5866-458a-87c1-51f225134903.png)




- **git --amend**   --> eğer komitleme yaptınız ama yeni  bir dosya içinde değişiklik yaptınız bu dosyayı commitlemek istemiyorsunuz.  git --amend komutunu kullanarak bir önceki commitin üzerine yazabilirsiniz commit değişmemiş yenisi oluşmamış fakat değişiklik kayıt edilmiştir.
- **git --amend  -m  "messageChanged"** --> Sadece mesajı güncellemek istersek


![image](https://user-images.githubusercontent.com/39422788/221198187-71933da3-f4ae-40d2-89bb-755bb0deab46.png)


- **git log -n 1** --> Bana yukardan başla bir tane commit getir.
       **git log  -n 2** --> Bana yukarıdan başla commitlerin sadece ikisini getir
       


![image](https://user-images.githubusercontent.com/39422788/221198228-e794ab5f-980a-4a4b-b8d9-e47a09170ced.png)



- **git revert  HeadId**  --> git revert komutu verdiğiniz HeadId göre commiti siler ve sildiğine dairde yeni bir commit oluşturur.
  
  

  ![image](https://user-images.githubusercontent.com/39422788/221198263-9dbfa6bc-a9ad-4f8e-822a-a0af2df299d7.png)
  
  

  revert işlemi yaptık bir önceki commit silindi ve tekrar sildiğimiz commiti de reverst edersek ilk konuma gelmiş oluruz 
  
  
-  **git reset --hard headId** --> bu komut gitmek istediğiniz komutu HEAD olarak kabul eder ve öncekileri siler sakıncalı bir durumdur. Biz bu yöntemi revert yaptıktan sonra oluşan iki commiti silmek için kullandık

 ![image](https://user-images.githubusercontent.com/39422788/221199610-2ba570a2-1d2c-4e67-96fe-56386187c94c.png)

- **git diff headID1..headID2 folderName** --> headID1 den headID2 ye kadar index.md dosyasında yapılan değişiklikleri olan değişiklikeri bana getir.

 ![image](https://user-images.githubusercontent.com/39422788/221200979-e3a781dd-aae1-41bc-923f-d7fe891c7955.png)
 
 
**git diff headID1..headID2**
 eğer dosya adı belirtilmemiş olsa idi o commitde yer alan bütün doyaların değişikliklerini gösterecekti.


# Branch İşlemleri ve Stash Kavramı

```
2 - Branch İşlemleri ve Stash Kavramı
Bir ekip ile beraber çalışıyorsanız sizden beklenen değişiklikleri oluşturacağınız yeni bir branch (dal)
üzerinde yaparsınız. Daha sonrasında bu oluşturduğunuz branch’ i ana branch olan master ile birleştirirsiniz. 
İşte bu ders içerisinde branch işlemlerine dair birçok konuyu ele alıyoruz.


Bazen Commit işlemi yaptıktan sonra yüzlerce satır komut yazarsınız. Sonra birden yazdığınız kodlardan önceki 
versiyon üzerinde değişiklik yapmanız gerekebilir. Bu durumda bu yazdığınız komutları bir yere saklamanız gerekir. 
İşte bu tarz senaryolarda git stash bizi çok önemli bir sorundan kurtarıyor.
```

Size Header oluşturma görevi verildi ne yapacaksınız size branch açılacak proje sonunda master branchde hepsi birleşecek
- **git branch** --> komutu tek başına yeni branch açmaz ama var olan branchleri gösterir
   - **git branch header** dersek örnek olaran kendimizin belirlediği header isimde branch açar ama master da kalmaya devam eder
- **git checkout (branchName)** komutu branchler arası geçişi sağlar
   - **git checkout -b footer** branch oluşturur ve direkt olarak footer branch geçer
   
   ![image](https://user-images.githubusercontent.com/39422788/221291514-55c70dd4-86cb-42d5-9d0e-7caaa5240141.png)
   
   - **git branch -D footer** oluşturduğumuz footer branch siler
   
   ![image](https://user-images.githubusercontent.com/39422788/221291583-39e39582-ab64-4307-a649-be97e96a789e.png)
   
   
   
   header adında bir branch oluşturdum ve header.md dosyasını ekledim commitledim..
   
   
   
   ![image](https://user-images.githubusercontent.com/39422788/221294199-2dcab716-0274-4316-a1ca-785c08218964.png)
      
   Daha sonra master branch geçiş yaptım
   
   
   ![image](https://user-images.githubusercontent.com/39422788/221294409-c1d55032-2958-4191-a50d-ee784979b1f2.png)

  dosya header tarafından takibe alındığı için master branch da gözükmeyecektir.
  ch
![image](https://user-images.githubusercontent.com/39422788/221293321-f1f936fd-334c-45d3-a435-a495373ebc35.png)

**NOT branch oluşturulduğu branch referans alır yani ana dizindeki dosyalar oluşturulan alt brancde de gözükür ama alt branch dosyası referanchbirenchde 
gözükmez**

Şİmdi header branch altında **git checkout -b footer** komutu ile branch oluşturup footer branch ne geçelim footer.md dosyası oluşturalım ekleyip komitleyelim

![image](https://user-images.githubusercontent.com/39422788/221297424-d50294fa-9eae-4edd-9241-bc9dc2564093.png)


![image](https://user-images.githubusercontent.com/39422788/221297469-8ec8f390-ed02-4703-8f7b-acd9058c882b.png)

header branch i içerisinde oluşturduğum için header referans alacaktır onun dosyasıda gözükecektir. Sırası ile branchler arası geçiş yapalım
**git checkout heaader**

![image](https://user-images.githubusercontent.com/39422788/221297833-66b3c8f5-efc8-4ac8-9027-e6e9f7d64946.png)

![image](https://user-images.githubusercontent.com/39422788/221297903-df5472cf-d715-4bb0-8697-de6f4cc73e7f.png)

**git checkout master**

![image](https://user-images.githubusercontent.com/39422788/221298078-cc898378-0363-4e45-b691-213968a21fc8.png)

![image](https://user-images.githubusercontent.com/39422788/221298156-b25e3d36-02ff-4c00-9d98-ef446562c2e2.png)



- **git stash** --> **git stash** komutu enson commite geri döner projenin commitlenmemiş kısmını kaydeder. değişiklikler yapıldıktan sonra en son işlemleri
stash den çağırmak için **git stash pop** komudu kullanılır bu komut son halini ekler stash kaydını siler **git stash apply** komutu son halini ekler stash silmez
**git stash list** stash listesini verir.

![image](https://user-images.githubusercontent.com/39422788/221301057-07476efc-6f2f-461e-b4e3-ceed27316c94.png)
![image](https://user-images.githubusercontent.com/39422788/221301171-47b03f22-c539-4213-9e57-5d7354c4e9a7.png)


# Merge, Rebase, Conflict

header branch de çalışırken değişlikleri committ etmeden ya da silmeden branch değiştirremezsiniz
Günün sonunda masterda dosyaların olması gerekeceği için bu durumda bu durumu merge etmenin bir kaç durumu ortaya çıkıyor.

- **git merge header** komutu ile master ve header branch birleştirmiş olduk. 
  **git log** dersek header ve master branclerin tamamı gösterilir
- **git merge --squash footer** komutunu kullanırsak footer da daha önceki yapılmış commitleri birleştirip son bir commitle hepsini birleştirme
şansı verir yukarıdaki örnekte iki branch kapsamında yapılan commitler gelmişti --squash ile biralt branch komitleri birleşip geldi.

![image](https://user-images.githubusercontent.com/39422788/221314090-24c5c1dc-104b-44d1-ab96-3457c40f7ebf.png)


***Rebase***



**Conflict**
![image](https://user-images.githubusercontent.com/39422788/221319351-4bbbc827-7119-4dc4-b0c7-26a356b8b294.png)
![image](https://user-images.githubusercontent.com/39422788/221319406-3d270625-6ac6-46fa-aa37-495db5f13c28.png)

**git merge --abort** CONFLİCT oluşursa geri alır ilk haline

