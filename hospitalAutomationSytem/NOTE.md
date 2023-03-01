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
