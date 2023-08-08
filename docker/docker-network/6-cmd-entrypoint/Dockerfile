FROM ubuntu:18.04

#Enter pointte container run edilirken sleep komutu çalışır ancak sleep komutu arguman bekler çalışmak için
# bu argüman verilmez ise hata atar
ENTRYPOINT [ "sleep" ]

# Eğer sleep arguman gönderilmemiş ise cmd kotu çalışacak yani 2 sn uyuyacak ve kapanacaktır 
CMD ["2"]
# birinci komut yani bu örnekte sleep executable yani çalıştırılabilirolalıdır
#CMD ovveride edilebilen bi komuttur
#CMD ["sleep" , "4"]

# shell formatında yazılabilir
# CMD sleep 4