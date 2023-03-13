- Örnek Arama
// Kod neyi çözdü : taplodan verileri koşula göre arama yapar.
``` JAVA
	public static String searchQuery(String name , String userName , String statu) {
		String query = "SELECT * FROM users WHERE name ILIKE '%{{name}}%' AND  username ILIKE '%{{username}}%'";
		query =query.replace("{{name}}",name);
		query = query.replace("{{username}}", userName);
		
		if(!statu.isEmpty()) {
			query = query + " type ILIKE '%{{type}}%';";
		}
		System.out.println(query);
		return query;
		
		
		
	}


```
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
