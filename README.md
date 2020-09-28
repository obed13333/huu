#glitch
1 //borra todo en server.js y copia esto y pegalo

//ESTE CODIGO NO AFECTARA SU BOT, SCRIPT DE ARRANQUE

const http = require('http');
const express = require('express');
const app = express();

app.use(express.static('public'));

app.get("/", function (request, response) {
  response.sendFile(__dirname + '/views/index.html');
});

app.get("/", (request, response) => {
  response.sendStatus(200);
});

app.listen(process.env.PORT);

setInterval(() => {
  http.get(`http://${process.env.PROJECT_DOMAIN}.glitch.me/`); 
}, 280000);


//DESDE AQUI EMPIEZA A ESCRIBIR EL CODIGO PARA SU BOT
//DESDE AQUI EMPIEZA A ESCRIBIR EL CODIGO PARA SU BOT

const Discord = require('discord.js');
const client = new Discord.Client();

client.on('ready', () => {
  console.log('estoy listo!');
  client.user.setPresence({
       status: "online",
       activity: {
           name: "-help | prueba bot en glitch",
           type: "PLAYING"
       }
   });

});

client.on('message', message => {

  if (message.content.startsWith("ping")) {
   let ping = Math.floor(message.client.ws.ping);
   message.channel.send(':ping_pong: `'+ping+' ms.` desde glitch.'); 

  }
  
});

client.login('tu token aqui');

2 //despues agrega una carpeta llamada watch.json y copea esto y pegalo

{
"install": {
  "include": [
    "^package\\.json$",
    "^\\.env$"
  ]
},

"restart": {
  "exclude": [
    "^public/",
    "^dist/"
  ],

  "include": [
    "\\.js$",
    "\\.json"
  ]
},
"throttle": 900000
}

  
3 //despues ve a package.jsonn y copea esto y pegalo

{
  "//1": "describes your app and its dependencies",
  "//2": "https://docs.npmjs.com/files/package.json",
  "//3": "updating this file will download and update your packages",
  "name": "hello-express",
  "version": "0.0.1",
  "description": "A simple Node app built on Express, instantly up and running.",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "discord.js": "^12.3.1",
    "express": "^4.17.1",
    "pornhub.js": "^0.2.2"
  },
  "engines": {
    "node": "12.x"
  },
  "repository": {
    "url": "https://glitch.com/edit/#!/hello-express"
  },
  "license": "MIT",
  "keywords": [
    "node",
    "glitch",
    "express"
  ],
  "devDependencies": {},
  "author": ""
}
