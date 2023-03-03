# POSTGRE TERMİNAL KOMUTLARI

- ***1.PSQL ile PostgreSQL'e bağlanmak***
```SQL
> psql -U <kullanıcı_adı>
```

- ***2.Kullanıcıya ait şifreyi girdikten sonra varsayılan veritabanı postgres'e bağlanıyor. ***
```SQL
> postgres=#
```

- ***3.Bulunan veritabanlarını listelemek için:***
```SQL
> \l veya \list
```
- ***4.Bizim örneğimizde dvdrental veritabanına bağlanacağız.***
```SQL
> \c dvdrental veya \connect dvdrental
```
- ***5.Bağlanılan dvdrental veritabanında bulunan tabloları listelemek için:***
```SQL
> \dt
```
- ***6.Herhangi bir tablonun sütunlarını ve tablo detaylarını görmek için:***
  ```SQL
  > \d <tablo_adı>
  ```

   - **Örnek Sorgu Senaryoları**
  
        - ***1.film tablosunda bulunan ve uzunluğu 80 ile 120 arasında bulunan ve aynı zamanda rental_rate değeri 0.99 veya 2.99 olan verileri sıralayınız.***
          ```SQL
           SELECT * 
           FROM film
           WHERE (length BETWEEN 80 AND 120) AND (rental_rate IN (0.99, 2.99));
          ````
       - ***2.film tablosunda bulunan ve uzunluğu 80 ile 120 arasında bulunan ve aynı zamanda rental_rate değeri 0.99 veya 2.99 olan verileri sıralayınız.***
          ```SQL
           SELECT * 
           FROM film
           WHERE (length BETWEEN 80 AND 120) AND (rental_rate IN (0.99, 2.99));
          ````


## PSQL terminal ekranından çıkmak için:
```SQL
\q
````
