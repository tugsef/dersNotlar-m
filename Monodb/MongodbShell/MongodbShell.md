# Mongodb Shell


- Hostta var olan veri tabanlarını göstermek için
```SQL
> show dbs
```

- Yeni veri tabanı oluşturuyoruz table:pcat-test-db
```SQL
> use pcat-test-db
```
- pcat-test-db tablosuna eleman ekliyoruz

```SQL
> db.photos.insertOne(
  {title: "Photo 1", description: "Photo description lorem ipsum", qty:20}
)
```

- Oluşturduğumuz dökümanı görebilmek için: use diyerek pcat-test-db tablosunda olmamız gerekli değilsek yapılır

```SQL
> use pcat-test-db
```

use işlemi tablo içerisinde değilsek yapılır.

```SQL
> db.photos.find()

```
- Verileri birden fazla yüklemek istediğimiz zaman

```SQL
> pcat-test-db> db.photos.insertMany([
... {title: "Photo 2" , decription:"Photo 2 decription" , qty:50},
... {titlr: "Photo 3" , decription:"Photo 3 decription" , qty:150}
... ])

```

[Mongodb Dökümantasyon](https://www.mongodb.com/docs/manual/crud/)

- title = "Photo 1" olanı getir

```SQL
> pcat-test-db> db.photos.find(
... {title:"Photo 1"}
... )
[
  {
    _id: ObjectId("645e2017003da94dc05769dc"),
    title: 'Photo 1',
    description: 'Photo description lorem ipsum',
    qty: 20
  }
]

```
- 200 den küçük 'qty' ikiden küçük olanları getir

```SQL
> pcat-test-db> db.photos.find(
... {qt:{$lt:200}}
... )
```

- 200 den küçük ilk 2 elemanı getir


```SQL
> pcat-test-db> db.photos.find(
... {qt:{$lt:200}}.limit(2)
... )
```

- [Mongodb update](https://www.mongodb.com/docs/manual/reference/method/db.collection.replaceOne/#mongodb-method-db.collection.replaceOne) işlemi title:"Photo 1" olanın qty değerini 222 yap

```SQL  
>pcat-test-db> db.photos.updateOne(
... {title:"Photo 1"},
... {$set:{qty:222}}
... )
```

- delete işlemi One olduğu için şarta uyan ilk dökümanı siler