# Multiplayer Game Modes

DevilutionX provides three modes for setting up multiplayer games. These can be seen in the in-game `Multi Player` menu.

* ZeroTier
* Client-Server (TCP)
* Loopback

Any multiplayer character created in any mode can also be played in any other mode.

*Some platforms do not support ZeroTier at this time. This list includes--but may not be limited to--Nintendo 3DS, Nintendo Switch, and PlayStation Vita. If your platform does not support ZeroTier, it will not show up in the `Multi Player` menu*

## ZeroTier

This mode provides the easiest way to play with others over the internet. No external configuration (such as entering IP addresses, ports, firewall rules, etc.) should be necessary to play games on the ZeroTier network. All you need to do is run the game, select this mode, and start creating or joining games.

![Image showing where joinable games will appear](https://media.discordapp.net/attachments/851552676033724437/906573763204755486/unknown.png)

When entering the in-game `ZeroTier` menu, your device will automatically configure itself to join the ZeroTier network so it can exchange messages with others on that network. This autoconfiguration may take somewhere around a full minute the first time you attempt to use this mode. If you are having trouble creating or joining games in this mode, you can try waiting around in the menu for the autoconfiguration to complete.

When a hosting a game using the ZeroTier mode, a name will be randomly generated and automatically assigned to the game session. In order to see the name of the game session you are currently playing, open the automap and check the upper-left corner of the game window.

ZeroTier games are not hosted on any server, nor are they hosted by any particular player. The game session is maintained by every peer who has joined the game, and as far as the game session is concerned, all peers are equal. As long as any player is still actively playing the game, players can join, leave, or rejoin in any order and the game session will remain active. The game session will disappear the moment all players have left the game.

ZeroTier configuration is stored in the DevilutionX configuration directory (`--config-dir`). This configuration directory contains your device's ZeroTier network address. You will not be able to run multiple clients from the same device using the same ZeroTier configuration. For more information about how to change your configuration directory, see: https://github.com/diasurgical/devilutionX/wiki/DevilutionX-additional-arguments-configuration-guide#configdir).

**Router Configuration Tips:** The ZeroTier network uses a variety of hole-punching techniques to establish communications over the physical network to achieve the most efficient routes possible between peers on the network. On most networks, one or more of these techniques should be viable to enable ZeroTier to communicate with clients without the need for any external configuration. For more information, visit https://zerotier.atlassian.net/wiki/spaces/SD/pages/6815768/Router+Configuration+Tips.

**Technical Information:** The ZeroTier Protocol Design Whitepaper provides a high-level technical overview describing how the protocol works and what it's designed to do. To read the whitepaper, visit https://docs.zerotier.com/zerotier/manual/.

## Client-Server (TCP)

DevilutionX has built-in TCP/IP support which only requires the host to expose a single TCP port to play the game with others. This mode is ideal for playing with others on a local area network where firewalls may be less of a concern, but it can also be used to play over the internet.

*By default, the game will use port 6112. See [diablo.ini Network section](https://github.com/diasurgical/devilutionX/wiki/DevilutionX-diablo.ini-configuration-guide#Network) for configuration options.*

When joining a game on a local area network, you will need to use the internal IP address of the host system in order to connect. Usually, this IP address exists in the form 192.168.X.X and can be found using the `ipconfig` tool on Windows operating systems.

When joining a game over the internet, you must use the public IP address of the host's network to connect to their game. Typically, this can be obtained by reviewing the network configuration in the host's router or by Googling "What is my IP?" from the host's system. Furthermore, the host must edit their router's configuration to forward the TCP port through the router to the host system on their local network. Note that some ISPs use security policies or NAT rules to make this port forwarding impossible. If you have trouble hosting games over the internet, you may need to contact your ISP so they can help troubleshoot.

If you receive a timeout error after a long pause when attempting to join a TCP game, this is a strong indication that a firewall is blocking packets. Ensure that the firewall configuration on the host system is not blocking traffic to the TCP port you are using to connect. For Windows hosts, you may need to adjust settings in Windows Firewall to allow incoming connections.

When troubleshooting TCP connectivity, it is often useful to use a step-by-step approach to make sure that you can establish connections with the host using a more simple network configuration before moving on to a more complex one. You can start by running two game clients on the host system and joining a game using the 127.0.0.1 IP address to verify that the host is listening on the correct TCP port. After that, you can test a local connection using two systems on the local network using the 192.168.X.X address of the host system to test local firewall configuration. Once that is working, you can try using the same two systems on the local network using the public IP of the network to test the port forwarding rules on the router. Following these steps can help you to narrow down the source of network issues that prevent you from hosting games over the internet.

## Loopback

This mode allows you to play solo games using Multiplayer characters without the need for a physical network connection. This is distinct from the Single Player game mode as you cannot use Single Player characters in Multiplayer game modes and vice-versa.

# Public/Private Games

All private games are encrypted and password protected. Public games are not encrypted or password protected and can therefore be joined by any host that can establish a network connection to your system.

When you enter the in-game `ZeroTier` menu, the game broadcasts multicast messages over the ZeroTier network to find peers who are currently hosting public games. If it receives a response, the game names will appear as additional list items in the menu under the `Join Game` option. It may take several seconds for the list of games to populate, and this game list will attempt to refresh every 30 seconds.

When using TCP to join public games, you must use the `Join Game` option. When prompted for a password, simply leave the password field blank to join the public game.

# Does DevilutionX work with Battle.net?

Battle.net is a service provided by Blizzard. We are not associated with them, so we have not worked on integrating with their service.