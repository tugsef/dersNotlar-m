#Docker Compose

- Bir .json , .xml ne ise yml de öyle düşünülebilir bir platformdan diğer pilatforma bilgi aktarılırken kullanılır data transferi için bir ortam sağlar(yml) 
> dockerfile.yml
- yml dosyalarında çıkıntı **(indent)** önemli

```yml
# key:value
key: value

#array ise alt alta kullanılabilir
key: 
    -  
    -
    -

# çıkıntı (inden önemli)
```

```yml
# version dockerın güncellemesinde oluşacak hatayı önler  docker engineer bu versiyona göre işlemi tanımlar 
versiyon : "3.4"

#sizin birbirine bağlayacağınız servisleri yazarsını birbirleri ile bağlantı kuracağımız
services:
  node-server:
    container_name: my-server
    build: .
    ports:
      - 3001:3000
```

- docker-compose dosyasını build eder aynı dizine dikkat

`docker-compose build`: build eder
`docker-compose up`: docker compose dosyasısnı çalıştırır
`docker-compose down` : tek tek kapatmakyerine kullanmaılsın


