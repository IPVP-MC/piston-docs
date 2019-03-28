Piston

[//]: <> (metadata keys, messages, commands)

What is Piston?

Piston is an <b>AIO</b> ("All in one") Minecraft server plugin for Hardcore Faction servers. Initially developed for [IPVP](ipvp.org), Piston was developed to address all needs of a Hardcore Factions server. It encompasses the following aspects of an HCF server:
* <b>Factions</b> - Internal management of factions and users
* <b>Staff Tools</b> - A complete toolset for staff to find and deal with cheaters 
* <b>Scoreboard & Tab</b> - Full customization of the on-screen scoreboard
* <b>Armor Kits</b> - Equip armor to enable special effects 
* <b>Events</b> - Event system provides KOTH, Conquest, and more
* <b>Basic Functions</b> - Expected basic functions, such as timers, potion & enchantment limits, death messages, etc 

What Piston Is Not

While Piston covers a majority of functionality of Hardcore Factions servers, the scope of its feature set does not cover everything. Here are some examples of functionality that Piston <b>does not</b> cover:
* Anti-cheat
* Permissions plugin
* UHC
* Hub functions

Additionally, Piston will not cover requirements of a Cannoning Factions server. 

Software Requirements

Piston is built on top of the Spigot API and is backed by a MySQL database used primarily for data storage. The ProtocolLib and Vault plugins are used as well but are optional. A summary of requirements to run Piston are as follows:
* Spigot 1.7.10
* MySQL 5.7+
* ProtocolLib
* Vault

ProtocolLib

ProtocolLib is an optional plugin that may be present alongside Piston in order to enable the following features:
* Custom scoreboard
* Custom tab
* Player clicks-per-second counter
* Fake block visibility (ie. faction barriers)

Vault

Vault is an optional plugin that may be present alongside Piston in order to enable the following features:
* Chat placeholders for ranks