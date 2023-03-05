- **ENUM , auto_increment(postgre için SERIAL) , PRİMARY KEY , NOT NULL**  komutlar cmd den girilmiştir.

```SQL
hospital=# CREATE TYPE person AS ENUM ('patient' , 'doctor' , 'chiefPhysicion');
```

```SQL
 CREATE TABLE users (
                    id SERIAL PRIMARY KEY ,
                    tcno VARCHAR(15) NOT NULL,
                    password VARCHAR(255) NOT NULL,
                    person person DEFAULT 'patient');
```

- **ENUM var olan değerlere ek olrak değer ekleme users person tipinde 'physician' baş hekim olarak eklendi**
```SQL
Alter TYPE person ADD VALUE 'physician';
```
