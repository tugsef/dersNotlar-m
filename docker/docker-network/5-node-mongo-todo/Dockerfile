FROM node:14-slim

#Çalışma Dizinim oluşturur
WORKDIR /opt/node-todo-app

#şuan benim bulunduğu localder images içerisindeki workdir içerisine aktar
COPY . .
ENV PORT=4000
EXPOSE 4000
RUN npm install
CMD [ "node" , "app.js" ]