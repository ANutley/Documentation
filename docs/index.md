![DiscordSRV](https://lol.scarsz.me/AiKvTS/Logo-filled-stroke.png)  

<div markdown="1" id="center">

**The most powerful, configurable, open-source Discord bridge plugin out there.**  

[:material-discord: Discord](https://discordsrv.com/discord){ .md-button }
[:fontawesome-solid-faucet: SpigotMC](https://www.spigotmc.org/resources/discordsrv.18494/){ .md-button }
[:material-bucket-outline: BukkitDev](https://dev.bukkit.org/projects/discordsrv){ .md-button }

[:material-cloud-upload: Latest Release](https://get.discordsrv.com/){ .md-button }
[:material-cloud-tags: Latest Snapshot](https://snapshot.discordsrv.com/){ .md-button }

**Supports All Minecraft Versions from 1.7.9 to 1.16.5**  

_**We only give support for the latest release/dev builds; please update before asking for help**_

</div>

## Features
- Bridge between Minecraft and Discord chats
- Forward your Minecraft Console to a Discord text channel  
- Broadcast alerts based on certain events
- Voice Proximity through the Discord Voice Chat ([`voice.yml`](voice))  
- Require linking accounts (or certain role/s) to play ([`linking.yml`](linking))  
- Support for popular chat plugins (listed below)  
- Highly customizable

### Plugins we hook into:  
* #### Chat
    * [`Herochat`](https://www.spigotmc.org/resources/herochat.34305/updates), [`LegendChat`](https://www.spigotmc.org/resources/legendchat.6268/), [`LunaChat`](https://github.com/ucchyocean/LunaChat), [`TownyChat`](https://www.spigotmc.org/resources/towny-advanced.72694/), [`UltimateChat`](https://www.spigotmc.org/resources/ultimatechat.23767/), [`VentureChat`](https://www.spigotmc.org/resources/venturechat.771/)
* #### Vanish
    * [`Essentials`](https://www.spigotmc.org/resources/essentialsx.9089/), [`PhantomAdmin`](https://www.spigotmc.org/resources/phantomadmin.37845/), [`SuperVanish`](https://www.spigotmc.org/resources/supervanish-be-invisible.1331/), [`VanishNoPacket`](https://dev.bukkit.org/projects/vanish)
* #### World
    * [`Multiverse`](https://dev.bukkit.org/projects/multiverse-core/)
* [`Vault`](https://www.spigotmc.org/resources/vault.34315/)  
* [`LuckPerms`](https://luckperms.net/)
* [`PlaceholderAPI`](https://www.spigotmc.org/resources/placeholderapi.6245/)  - [DiscordSRV Expansion Placeholders](PAPI-Placeholders)
### Plugins that use our API:
* [DiscordSRV StaffChat](https://www.spigotmc.org/resources/discordsrv-staff-chat.44245/)
* [ChatControlPro](https://www.spigotmc.org/resources/chatcontrol-pro.10258/)
* [CMI](https://www.spigotmc.org/resources/cmi.3742/)
* [Plan](https://www.spigotmc.org/resources/plan-player-analytics.32536/)
* [EmojiChat](https://www.spigotmc.org/resources/emojichat.50955/)
* [PurpleIRC](https://www.spigotmc.org/resources/purpleirc.2836/)
* [ChatReplay](https://www.spigotmc.org/resources/chatreplay.28982/)
* [AuctionHouse](https://www.spigotmc.org/resources/auctionhouse.61836/)
* [Staff Facilities](https://www.spigotmc.org/resources/staff-facilities.13097/)
* [Staff++](https://www.spigotmc.org/resources/staff.83562/)
* [LiteBansBridge](https://www.spigotmc.org/resources/litebansbridge.76326/)
* [MCSF (My Christian Swear Filter)](https://www.spigotmc.org/resources/mcsf.54115/)
* [MZP-VoteParty](https://www.spigotmc.org/resources/mzp-voteparty.89754/)
* If you would like your plugin listed here, please bring it to `granny`'s attention in our [Discord](https://discordsrv.com/discord) server.
## Intended usage
By using this plugin, you are able to give players the ability to chat in-game with players on your Discord server, as well as having people on the Discord server be able to chat with people in the minecraft server - This can be useful for players that still want to communicate with players in-game, but can't access the Minecraft server for whatever reason.  

This plugin has a remote console feature. You can designate a text channel for the plugin to forward console messages, which also runs all messages sent into that channel as commands by the server console (You should restrict sending this channel to a developer or high ranking role only). Due to how Discord's permissions work, you can have some server roles have access to see the console, while also not allowing them to send messages in that channel, thus creating a read-only console for trusted staff members.  

Both chat and console are toggleable through the configuration file. Some options can be refreshed with `/discordsrv reload` by an OP or a player with the `discordsrv.reload` permission.  

## Bot Permissions

__Server Permissions__  
* `Manage Roles` - for [role synchronization](https://config.discordsrv.com/synchronization/GroupRoleSynchronizationGroupsAndRolesToSync) and [adding roles to linked players](https://config.discordsrv.com/config/MinecraftDiscordAccountLinkedRoleNameToAddUserTo)  
* `Manage Channels` - for [channel topic updater](https://config.discordsrv.com/messages/ChannelTopicUpdaterChatChannelTopicFormat)  
* `Ban Members` - for [ban synchronization](https://config.discordsrv.com/synchronization/BanSynchronizationDiscordToMinecraft)  
* `Manage Nicknames` - for [name synchronization](https://config.discordsrv.com/synchronization/NicknameSynchronizationEnabled)  
* `Manage Webhooks` - for [experimental webhook usage](https://config.discordsrv.com/config/Experiment_WebhookChatMessageDelivery) (Server-wide permission is _recommended_, but can be applied on a per-channel basis)  

__Channel Permissions__  
* `Read Text Channels & See Voice Channels` and `Send Messages` - Required in all of DiscordSRV's channels (including [console](https://pkrok.me/config/DiscordConsoleChannelId) and [voice lobby](https://config.discordsrv.com/voice/Lobby%20channel)), the [voice module category](https://config.discordsrv.com/voice/Voice%20category) and any other channels you want for [canned responses](https://config.discordsrv.com/config/DiscordCannedResponses)  
* `Manage Messages` - for message deletion features [playerlist](https://config.discordsrv.com/config/DiscordChatChannelListCommandEnabled), [chat channel commands](https://config.discordsrv.com/config/DiscordChatChannelConsoleCommandEnabled)  
* `Embed Links` - optionally for embedding ingame-posted links and required when embed messages are used [death](https://config.discordsrv.com/messages/MinecraftPlayerDeathMessage), [join/Leave](https://config.discordsrv.com/messages/MinecraftPlayerJoinMessage)  
* `Mention @everyone, @here and All Roles` - for mentioning @everyone if removed from [cut phrases in config.yml](https://config.discordsrv.com/config/DiscordChatChannelBlockedPhrases) and [mentions enabled](https://config.discordsrv.com/config/DiscordChatChannelTranslateMentions)  
* `Add Reactions` and `Read Message History` - for when the bot reacts with "💬" and "❗" to notify a [truncated message](https://config.discordsrv.com/config/DiscordChatChannelTruncateLength) is being sent from Discord to Minecraft  
* `Move Members` - required for the [voice lobby](https://config.discordsrv.com/voice/Lobby%20channel) and [voice category](https://config.discordsrv.com/voice/Voice%20category)

## Installation  
Visit the [Installation](Installation) page for clear and in-depth instructions on installing and setting up DiscordSRV.  

## Donations
First off, thank you from the bottom of my heart for the pizza. If you would like to donate, go to https://scarsz.me/donate. $10 is the suggested amount but you can donate however much you would like- anything is a massive thank you from me. In the note put your Discord username and if you're in DiscordSRV's server you'll be set as a donator and you'll receive some neat perks in the future. If you donated without the note, send me a PM on Discord and I'll manually check it.  
## Developers
If you want to interface DiscordSRV with your plugin, you can do so by adding the Maven dependency or adding the plugin jar (DiscordSRV version 1.18.0+) to your project. For an example of this, see [DiscordSRV-ApiTest](/DiscordSRV/DiscordSRV-ApiTest). Be sure to add "DiscordSRV" to your plugin's `plugin.yml` depends/softdepends list.  

=== "Maven"
    ```xml
    <repository>
        <id>Scarsz-Nexus</id>
        <url>https://nexus.scarsz.me/content/groups/public/</url>
    </repository>  
    ...  
    <dependency>
        <groupId>com.discordsrv</groupId>
        <artifactId>discordsrv</artifactId>
        <version>1.22.0</version>
        <scope>provided</scope>
    </dependency>
    ```  
=== "Gradle"
    ```js
    repositories {
        maven { url 'https://nexus.scarsz.me/content/groups/public/' }
    }  
    dependencies {
        compileOnly 'com.discordsrv:discordsrv:1.22.0'
    }
    ```

## Data usage
### Data collection
Anything and everything shown at https://bstats.org/plugin/bukkit/DiscordSRV will be visible to the public with your server included in the statistics. This is only for statistics; no private information of your server is sent. If you don't want your server included in this, specify the config option `MetricsDisabled` and set it to `true` in the config.yml file.  

## Update checking
DiscordSRV checks for updates using GitHub's API, and makes sure the version is safe to use via a minimum version (security feature), you may disable update checking by setting `UpdateCheckDisabled` to `true` in the config.yml file; however this may leave your server at risk if there is a security issue/exploit and you're running a vulnerable version.   