#ne çalıştırıcaksın baseImages belirtiyoruz
FROM ubuntu:18.04
#çalıştırdığın container içerisindeki komut satırları
RUN apt-get update
RUN apt-get install curl -y
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install nodejs -y
#hedef dizin
WORKDIR /opt/node-app
#hedefte ne alıştıracaksın
COPY . /opt/node-app/
#hedef dosya
ENV channel=tugsef
CMD ["node","index.js"]


#Yukarıdaki bütün komutlar docker içerisinde layer olarak tutulut tekrar kontainer oluşturmakü
#istediğinde ya da örnekte isimlendirme yapmak istersek images listesinde kayıtlıdır otamatik
#cache alırlayır stcructure denir oldu dockerfile build ederken bir peobemle karşılaştın
# hatayı docker engenner o duckorıbulr ve ordandevam eder.