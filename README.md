# Wanted
Wanted
// Import biblioteki Discord.js
const Discord = require('discord.js');

// Utwórz nowego klienta Discorda
const client = new Discord.Client();

// Zdefiniuj token bota
const token = 'TWÓJ_TOKEN_BOTA';

// Funkcja wita nowych użytkowników
client.on('guildMemberAdd', member => {
    // ID kanału, na którym ma być wysłane powitanie
    const channelID = 'ID_KANAŁU';

    // Sprawdź, czy bot ma dostęp do kanału
    const channel = member.guild.channels.cache.get(channelID);
    if (!channel) return console.error("Nie można znaleźć kanału.");

    // Wyślij powitanie na wybranym kanale
    channel.send(`Witaj ${member}, witamy na naszym serwerze!`);
});

// Zdarzenie połączenia bota
client.on('ready', () => {
    console.log(`Zalogowano jako ${client.user.tag}!`);
});

// Zaloguj bota przy użyciu podanego tokena
client.login(token);
