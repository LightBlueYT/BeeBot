//Calling Packages
const Discord = require("discord.js");
const client = new Discord.Client();
const newUsers = new Discord.Collection();
const fs = require("fs");


//Prefix
const prefix = "!";


//Calling Function
 client.on('message', async(message) => {
     
     
//Help command
if(message.content.startsWith(prefix + '/^help/i')){
var HelpGEN = new Discord.RichEmbed()
.setTitle('General Commands')
.addField('!ping', 'Sends back a message with the bots ping! :ping_pong:')
.addField('!binfo', 'Well it tells you the bots info if that wasent obvious already.')
.addField('!suggest', 'Feel like the bot need something more too it? Either join the server or use this command!');
var HelpMOD = new Discord.RichEmbed()
.setTitle('Mod Commands')
.addField('!prune', 'Prunes all the messages from the channel. (Can not be specified with a number!)')
.addField('!ban', 'Thor comes to the rescue with hes StormBanner and bans a user!')
.addField('!kick', 'If you ever need to kick someone this is what you need.');
var HelpMISC = new Discord.RichEmbed()
.setTitle('Misc Commands')
.addField('!avatar', 'Shows your accounts avatar.');
message.channel.send('Help have been sent into your messages!');
return message.author.send(HelpGEN + HelpMOD + HelpMIS);
}


//Boot Command
if(message.content.startsWith(prefix + '/^boot/i')){
await message.reply("Bot is rebooting please use /ping in a second");
client.commands.forEach( async cmd => {
await client.unloadCommand(cmd);   
  });
  process.exit(5);
};


//Ping Command
if(message.content.startsWith(prefix + '/^ping/i')){
var Ping = new Discord.RichEmbed()
.setTitle (new Date().getTime() - message.createdTimestamp + " MS")
.setDescription(':ping_pong: :ping_pong:')
.setColor('ffffffff')
return message.channel.send(Ping)
}


//UserAvatar Command
if(message.content.startsWith(prefix + '/^avatar/i')){
return message.reply(' Heres your avatar! ' + message.author.avatarURL + ' What a handsome and good made avatar')
}

//BotInfo Command
if(message.content.startsWith(prefix + '/^binfo')){
var BInfo = new Discord.RichEmbed()
.setTitle('Bot Info')
.setDescription ('Info about the bot')
.addField('Bots Developer(s) ', '@Light#5575')
.addField('Bots prefix ', '! (NOT CHANGEABLE!)')
}


//Ban Command
if (!message.guild) return;
if (message.content.startsWith(prefix + '/^ban/i')) {
if (message.member.hasPermission("BAN_MEMBERS")) {
const user = message.mentions.users.first();
if (user) {const member = message.guild.member(user);
if (member) { member.ban('Optional reason that will display in the audit logs').then(() => {
message.reply(`Successfully banned ${user.tag}`);
}).catch(err => {message.reply('I was unable to ban the member');
console.error(err);
});     } 
else { message.reply('That user isn\'t in this guild!');
}} 
 else {message.reply('You didn\'t mention the user to ban!');
}}}
    
    
//Kick Command
if (!message.guild) return;
if (message.content.startsWith(prefix + '/^kick/i')) {
if (message.member.hasPermission("KICK_MEMBERS")) {
const user = message.mentions.users.first();
if (user) {const member = message.guild.member(user);
if (member) { member.kick('Optional reason that will display in the audit logs').then(() => {
 message.reply(`Successfully kicked ${user.tag}`);
}).catch(err => {message.reply('I was unable to kick the member');
console.error(err);
});     } 
else { message.reply('That user isn\'t in this guild!');
}} 
else {message.reply('You didn\'t mention the user to kick!');
}}}
    
    
//Prune commands
if (message.content.startsWith("!prune")) {
if (message.member.hasPermission("MANAGE_MESSAGES")) {
message.channel.fetchMessages()
.then(function(list){
message.channel.bulkDelete(list);
}, function(err){message.channel.send("ERROR: ERROR CLEARING CHANNEL.")})       }}


//Suggestion command
var str = message.content;
str = str.replace("!suggest", "");
if (message.content.startsWith("!/^suggest/i")){
return client.channels.get('514917785248202773').send(message.author.tag+" suggested " + str)
}


//End message Function
});
