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
