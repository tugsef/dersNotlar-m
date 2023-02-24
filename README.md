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

