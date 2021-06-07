## 👋 Hola
### Me llamo `krozzz`, Soy dueño de un bot de discord llamado **Lunar**, el cual puedes añadir presionando este botón -> **[Click Aquí](https://dsc.gg/lunarbot)**, Te dejo un par de tips aquí debajo!
---
##### Codigo de inicio para un bot de discord
```js
/////Inicio
const Discord = require("discord.js");
const client = new Discord.Client();

/////Definiciones
let prefix = "!" //Establecemos el prefijo

/////Evento ready
client.on("ready", async() => {
     console.log(`He iniciado, mi nombre es ${client.user.tag} y estoy en ${client.guild.cache.size} servidores!`) //Enviaremos un mensaje a nuestra consola
     client.user.setPresence({
	status: 'online', //Seleccionamos online, para que el bot se vea online, puedes elejir, "online"/"idle"/"dnd"
	activity: {
	  name: `Estoy usando el codigo base de @KrozZz#9534!`, //Seleccionamos un estado para nuestro bot, pueden cambiar esto!
          type: 'WATCHING' //Seleccionamos la acción que el bot esta haciendo, en este caso es WATCHING(Viendo), pueden elejir, "PLAYING"/"WATCHING"/"STREAMING", en español: Jugando, Viendo, Stremeando
	  }
     });
});

/////Evento message
client.on("message", => async message => {
     if(message.author.bot) return; //Si el autor del mensaje es un bot, no funcionara ningun comando
     
     if(!message.content.startsWith(prefix)) return; //Si el mensaje no inicia con el prefijo, no funcionara ningun comando
    
     const args = message.content.slice(prefix.length).trim().split(/ +/g); //Definimos args, para que solo funcione si el principio del mensaje es el prefix y el comando
     const command = args.shift().toLowerCase(); //Definimos command para evitar poner **if(!message.content.startsWith(prefix + "comando"))**
     
     if(command === "ping"){
          return message.channel.send("Pong!"); //Si comando es igual a ping, retorna pong
     }
});
```
#### Tambien pueden hacer [click aquí](https://portalmybot.com/codes) para ir a una pagina donde hay codigos para comandos!
