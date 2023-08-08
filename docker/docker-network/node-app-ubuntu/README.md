1 apt-get update
3 apt-get install curl -y
4 curl -sL https://deb.nodesource.com/setup_10.x | bash
8 apt-get install nodejs -y
16 cd opt
17 mkdir node-app 
18 cd node-app
21 echo 'console.log("node.js from ubuntu");' > index.js
23 node index.js
