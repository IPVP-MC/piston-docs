# Faction
**Syntax**: `/factions <subcommand> [opts...]` \
**Aliases**: f, fac, factions, team, teams, t, group, groups, g

## Brief Description
Faction related sub-commands

## Permission Tree
- `piston.*`
  - `piston.bypass.*`
    - `piston.bypass.command.*`
      - `piston.bypass.command.create.delay`
  - `piston.command.*`
    - `piston.command.factions.*`
      - `piston.command.factions.player`
        - `piston.command.factions.accept`
        - `piston.command.factions.ally`
        - `piston.command.factions.announce`
        - `piston.command.factions.chat`
        - `piston.command.factions.claim`
        - `piston.command.factions.viewclaims`
        - `piston.command.factions.create`
        - `piston.command.factions.demote`
        - `piston.command.factions.deposit`
        - `piston.command.factions.disband`
        - `piston.command.factions.focus`
        - `piston.command.factions.help`
        - `piston.command.factions.history`
        - `piston.command.factions.home`
        - `piston.command.factions.invite`
        - `piston.command.factions.invites`
        - `piston.command.factions.kick`
        - `piston.command.factions.kills`
        - `piston.command.factions.leader`
        - `piston.command.factions.leave`
        - `piston.command.factions.list`
        - `piston.command.factions.map`
        - `piston.command.factions.ores`
        - `piston.command.factions.promote`
        - `piston.command.factions.reject`
        - `piston.command.factions.rename`
        - `piston.command.factions.resethome`
        - `piston.command.factions.sethome`
        - `piston.command.factions.show`
        - `piston.command.factions.stuck`
        - `piston.command.factions.unally`
        - `piston.command.factions.unclaim`
        - `piston.command.factions.uninvite`
        - `piston.command.factions.withdraw`
      - `piston.command.factions.staff`
        - `piston.command.factions.chatspy`
        - `piston.command.factions.claimfor`
        - `piston.command.factions.clearclaims`
        - `piston.command.factions.clearallclaims`
        - `piston.command.factions.forcedemote`
        - `piston.command.factions.forcejoin`
        - `piston.command.factions.forcekick`
        - `piston.command.factions.forceleader`
        - `piston.command.factions.forcepromote`
        - `piston.command.factions.forceunclaimhere`
        - `piston.command.factions.mute`
        - `piston.command.factions.remove`
        - `piston.command.factions.setdtr`
        - `piston.command.factions.setdtrregen`
        - `piston.command.factions.show.announcement`
        - `piston.command.factions.toggleflag`

## Player Sub-commands

### Accept
**Description**: Accept a join request from a faction \
**Usage**: `/faction accept <faction>` \
**Aliases**: join, a \
**Permission**: `piston.command.factions.accept`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| faction    | Name of faction     | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.accept.maxed`
  * **Condition**: Faction at max user capacity
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of users in faction
    * **Type**: integer
* `command.faction.accept.not-invited`
  * **Condition**: Not invited to faction
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
* `command.faction.accept.frozen`
  * **Condition**: Sender is frozen
  
Sent to faction:
* `command.faction.accept.joined`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Announce
**Description**: Set your faction announcement \
**Usage**: `/faction announce <text>` \
**Aliases**: announcement, motd \
**Permission**: `piston.command.factions.announce`

#### Parameters
| Parameter  | Description              | Type        | Required | Default |
| ---------- | ------------------------ | ----------- | -------- | ------- |
| text       | New faction announcement | string      | true     |  n/a    |

#### Messages
Sent to faction:
* `command.faction.announce.remove`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
* `command.faction.announce.set.`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: announcement text
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Chat
**Description**: Send a message to your faction or allies \
**Usage**: `/faction chat <type> [message]` \
**Aliases**: c, message, msg \
**Permission**: `piston.command.factions.chat`

#### Parameters
| Parameter  | Description              | Type        | Required | Default |
| ---------- | ------------------------ | ----------- | -------- | ------- |
| type       | Chat message type        | string      | true     |  n/a    |
| message    | Message to send          | string      | false    |  n/a    |

**Note**: Not specifying a message will set the current chat channel to `type`

#### Chat Channels
Types of faction channels:
* faction
* public

#### Messages
Sent to command sender:
* `command.faction.chat.set`
  * Parameter 0: 
    * **Description**: channel name
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Claim
**Description**: Claim land in the wilderness \
**Usage**: `/faction claim` \
**Aliases**: claimland \
**Permission**: `piston.command.factions.claim`

#### Messages
Sent to command sender:
* `command.faction.raidable`
  * **Condition**: Faction is raidable
* `command.faction.claim.max`
  * **Condition**: Faction has too many claims
* `command.faction.claim.inv`
  * **Condition**: No inventory space for claim wand
* `command.faction.claim.claiming`
  * **Condition**: Already claiming
* `command.faction.claim.combat`
  * **Condition**: Sender in combat
* `command.faction.claim.wand`

[//]: <> (-----------------------------------------------------------------) 

### Claims
**Description**: View all claims for a faction \
**Usage**: `/faction claims [faction]` \
**Aliases**: viewclaims \
**Permission**: `piston.command.factions.viewclaims`

#### Parameters
| Parameter  | Description              | Type        | Required | Default |
| ---------- | ------------------------ | ----------- | -------- | ------- |
| faction    | Name of faction          | string      | false    |  n/a    |

#### Messages
Sent to command sender:
* `command.error.faction.required`
  * **Condition**: No faction specified & not in faction
* `command.faction.claims.none`
  * **Condition**: Faction has no claims
* `command.faction.claims.header`
  * Parameter 0:
    * **Description**: name of faction
    * **Type**: string
  * Parameter 1:
    * **Description**: number of claims
    * **Type**: integer
* `command.faction.claims.line`
  * Sent for every owned claim
  * Parameter 0:
    * **Description**: claim description
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Create
**Description**: Create a faction \
**Usage**: `/faction create <name>` \
**Aliases**: make, define \
**Permission**: `piston.command.factions.create`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| name       | Name of faction     | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.create.name.taken`
  * **Condition**: Faction name already exists
* `command.faction.create.name.length`
  * **Condition**: Faction name too long
* `command.faction.create.name.invalid`
  * **Condition**: Faction name invalid
* `command.faction.create.name.alphanumeric`
  * **Condition**: Faction name has illegal characters
* `command.faction.create.cooldown`
  * **Condition**: Faction creation is on cooldown
  * Parameter 0: 
    * **Description**: name of KOTH
    * **Type**: string

Broadcast to server:
* `command.faction.create.broadcast`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 1: 
    * **Description**: name of sender
    * **Type**: string
    

[//]: <> (-----------------------------------------------------------------) 

### Demote
**Description**: Demote a captain \
**Usage**: `/faction demote <player>` \
**Aliases**: uncaptain, delcaptain, delofficer
**Permission**: `piston.command.factions.demote`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of captain            | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.error.faction.other.not-same`
  * **Condition**: Target player not in same faction
* `command.faction.demote.leader`
  * **Condition**: Attempted to demote leader
  
Sent to faction:
* `command.faction.demote.success`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: role name
    * **Type**: string


[//]: <> (-----------------------------------------------------------------) 

### Deposit
**Description**: Deposit money into the faction \
**Usage**: `/faction deposit <amount>` \
**Aliases**: d
**Permission**: `piston.command.factions.deposit`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| amount     | Money to deposit (n >= 0)  | integer     | true     |  n/a    |

**Note**: Value `all` is also accepted for `amount`

#### Messages
Sent to command sender:
* `command.error.balance.insufficient`
  * **Condition**: Insufficient balance
* `command.faction.deposit.invalid`
  * **Condition**: Attempt to deposit < 0

Sent to faction:
* `command.faction.deposit.success`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: amount deposited
    * **Type**: integer
    
[//]: <> (-----------------------------------------------------------------) 

### Disband
**Description**: Disband your faction \
**Usage**: `/faction disband` \
**Permission**: `piston.command.factions.disband`

#### Messages
Sent to command sender:
* `command.faction.raidable`
  * **Condition**: Cannot disband when raidable
* `command.faction.deposit.invalid`
  * **Condition**: Attempt to deposit < 0

Sent to faction:
* `command.faction.disband`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 1: 
    * **Description**: command sender name
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------) 

### Focus
**Description**: Mark a player as the faction focus in battles \
**Usage**: `/faction focus <player>` \
**Permission**: `piston.command.factions.focus`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.error.target.offline`
  * **Condition**: Target player offline
* `command.faction.focus.own`
  * **Condition**: Cannot focus own faction member
* `command.faction.focus.unset.command`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string
* `command.faction.focus.set`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### History
**Description**: View the factions history \
**Usage**: `/faction history <archive> [page]` \
**Aliases**: hist \
**Permission**: `piston.command.factions.focus`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| archive    | Name of player or faction  | string      | true     |  n/a    |
| page       | History page number        | integer     | false    |  1      |

#### Messages
Sent to command sender:
* `command.faction.history.page`
* `command.faction.history.none`
* `command.faction.border`
* `command.faction.list.header`
  * Parameter 0: 
    * Uses `command.faction.history.header` with type of history as parameter
    * **Description**: history header
    * **Type**: string
  * Parameter 1: 
    * **Description**: current page number
    * **Type**: integer
  * Parameter 2: 
    * **Description**: total pages
    * **Type**: integer
* `command.faction.history.line`
  * Parameter 0: 
    * **Description**: date
    * **Type**: string
  * Parameter 1: 
    * **Description**: history content
    * **Type**: string
* `command.faction.list.footer1`
  * Parameter 0: 
    * **Description**: current page number
    * **Type**: integer
  * Parameter 1: 
    * **Description**: total pages
    * **Type**: integer
* `command.faction.list.footer2`
  * Parameter 0: 
    * **Description**: static text
    * **Value**: `/f history <archive> <page>`
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------) 

### Home
**Description**: Teleport to the faction home \
**Usage**: `/faction home` \
**Permission**: `piston.command.factions.home`

#### Messages
Sent to command sender:
* `command.faction.home.tagged`
  * **Condition**: Command sender tagged
* `sumo.command`
  * **Condition**: Cannot use in sumo tournament
* `command.faction.home.none`
  * **Condition**: No faction home
* `command.faction.home.height`
  * **Condition**: Faction home is at too high Y elevation
* `command.faction.home.world`
  * **Condition**: Faction home is in invalid world
* `command.faction.home.enemy`
  * **Condition**: Current location in enemy territory
* `command.faction.timer.active`
  * **Condition**: Teleport timer already active
* `command.faction.timer.success`
  * Parameter 0: 
    * **Description**: static text
    * **Value**: `your faction home`
    * **Type**: string
  * Parameter 1: 
      * **Description**: time to teleport
      * **Type**: string
* `command.faction.timer.warn.move`
  * Parameter 0: 
    * **Description**: static value
    * **Value**: `2`
    * **Type**: integer

[//]: <> (-----------------------------------------------------------------) 

### Invite
**Description**: Invite a player to the faction \
**Usage**: `/faction invite <player>` \
**Aliases**: inv, invitemember, inviteplayer \
**Permission**: `piston.command.factions.invite`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.error.target.offline`
  * **Condition**: Target player offline
* `command.faction.invite.member`
  * **Condition**: Cannot invite own member
* `command.faction.raidable`
  * **Condition**: Cannot invite while raidable
* `command.faction.invite.duplicate`
  * **Condition**: Already invited target
* `command.faction.invite.disabled`
  * **Condition**: Target player disabled invites
Sent to target player:
* `command.faction.invite.out`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: faction name
    * **Type**: string

Sent to faction:
* `command.faction.invite.success`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Kick
**Description**: Kick a player from the faction \
**Usage**: `/faction kick <player>` \
**Aliases**: kickmember, kickplayer \
**Permission**: `piston.command.factions.kick`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.raidable`
  * **Condition**: Cannot kick from raidable faction
* `command.error.faction.other.not-same`
  * **Condition**: Target player not in faction
* `command.faction.kick.rank`
  * **Condition**: Target player higher rank
* `command.faction.kick.combat`
  * **Condition**: Cannot kick in-combat player

Sent to target player:
* `command.faction.kick.recipient`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
* `command.faction.kick.safe`

Sent to faction:
* `command.faction.kick.success`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: command sender name
    * **Type**: string
* `command.faction.kick.cooldown`
  * Parameter 0: 
    * **Description**: cooldown time
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Leader
**Description**: Assign a new leader for the faction \
**Usage**: `/faction leader <player>` \
**Aliases**: setleader, newleader \
**Permission**: `piston.command.factions.leader`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.error.faction.other.not-same`
  * **Condition**: Target player not in faction
* `command.faction.leader.self`
  * **Condition**: Cannot promote self to leader
  
Sent to faction:
* `command.faction.leader.success`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Leave
**Description**: Leave your current faction \
**Usage**: `/faction leave` \
**Permission**: `piston.command.factions.leave`

#### Messages
Sent to command sender:
* `command.faction.leave.assign`
  * **Condition**: Cannot leave as leader
* `command.faction.leave.combat`
  * **Condition**: Cannot leave in combat
* `command.faction.leave.territory`
  * **Condition**: Cannot leave in faction territory
* `command.faction.raidable`
  * **Condition**: Cannot leave while faction raidable
* `command.faction.leave.success`  
  
Sent to faction:
* `command.faction.leave.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------) 

### List
**Description**: View a list of factions \
**Usage**: `/faction list [page]` \
**Permission**: `piston.command.factions.list`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| page       | Page number                | integer     | false    | 1       |

#### Messages
Sent to command sender:
* `command.faction.list.empty`
  * **Condition**: No factions to display
* `command.faction.border`
* `command.faction.list.header`
  * Parameter 0:
    * **Description**: static value
    * **Value**: `Faction List`
    * **Type**: string
  * Parameter 1: 
    * **Description**: current page number
    * **Type**: integer
  * Parameter 2: 
    * **Description**: total pages
    * **Type**: integer
* `command.faction.list.line`
  * Parameter 0: 
    * **Description**: position
    * **Type**: integer
  * Parameter 1: 
    * **Description**: faction name (colored)
    * **Type**: string
  * Parameter 2: 
    * **Description**: faction name (uncolored)
    * **Type**: string
  * Parameter 3: 
    * **Description**: number of online users
    * **Type**: integer
  * Parameter 4: 
    * **Description**: total users
    * **Type**: integer
  * Parameter 5: 
    * **Description**: faction dtr
    * **Type**: string
  * Parameter 6: 
    * **Description**: faction max dtr
    * **Type**: string
* `command.faction.list.footer1`
  * Parameter 0: 
    * **Description**: current page number
    * **Type**: integer
  * Parameter 1: 
    * **Description**: total pages
    * **Type**: integer
* `command.faction.list.footer2`
  * Parameter 0: 
    * **Description**: static text
    * **Value**: `/f list <page>`
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Map
**Description**: Display nearby faction claims \
**Usage**: `/faction map` \
**Permission**: `piston.command.factions.map`

#### Messages
Sent to command sender:
* `command.faction.map.nothing`
  * **Condition**: No nearby claims
* `command.faction.map.disable`
* `command.faction.map.describe`
  * Parameter 0: 
    * **Description**: faction name
    * **Type**: string
  * Parameter 1: 
    * **Description**: claim description
    * **Type**: string
  * Parameter 2: 
    * **Description**: border stained glass color
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Ores
**Description**: View the amount of ores a player has mined \
**Usage**: `/faction ores <player>` \
**Permission**: `piston.command.factions.ores`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.ores.none.total`
  * **Condition**: No ores mined
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
* `command.faction.ores.none.faction`
  * **Condition**: Faction has no ores mined
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
* `command.faction.ores.header.total`
* `command.faction.ores.header.faction`
* `command.faction.ores.line`
  * Parameter 0: 
    * **Description**: block name
    * **Type**: string
  * Parameter 1: 
    * **Description**: amount
    * **Type**: integer

[//]: <> (-----------------------------------------------------------------) 

### Promote
**Description**: Promote a member in the faction \
**Usage**: `/faction promote <player>` \
**Aliases**: promote, captain, officer, mod, moderator \
**Permission**: `piston.command.factions.promote`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.error.faction.other.not-same`
  * **Condition**: Target player not in same faction
* `command.faction.promote.below`
  * **Condition**: Attempted to promote higher ranked player
  
Sent to faction:
* `command.faction.promote.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 2: 
    * **Description**: role name
    * **Type**: string

[//]: <> (-----------------------------------------------------------------)

### Reject
**Description**: Reject an invitation to join a faction \
**Usage**: `/faction reject <faction>` \
**Aliases**: deny \
**Permission**: `piston.command.factions.reject`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| faction    | Name of faction     | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.accept.not-invited`
  * **Condition**: Not invited to faction
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
* `command.faction.reject.success`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
  
Sent to faction:
* `command.faction.reject.notify`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Rename
**Description**: Rename the faction \
**Usage**: `/faction rename <name>` \
**Aliases**: setname, changename \
**Permission**: `piston.command.factions.rename`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| name       | New faction name    | string      | true     | n/a     |

#### Messages
Sent to command sender:
* `command.faction.rename.same`
  * **Condition**: Same faction name
  
Broadcast to server:
* `command.faction.rename.success`
  * Parameter 0: 
    * **Description**: old faction name
    * **Type**: string
  * Parameter 1: 
    * **Description**: new faction name
    * **Type**: string
  * Parameter 2: 
    * **Description**: command sender name
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Resethome
**Description**: Unset the faction home location \
**Usage**: `/faction resethome` \
**Aliases**: clearhome, removehome, remhome, deletehome, delhome, unsethome \
**Permission**: `piston.command.factions.unsethome`

#### Messages
Sent to command sender:
* `command.faction.resethome.not-set`
  * **Condition**: No faction home
  
Broadcast to faction:
* `command.faction.resethome.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Sethome
**Description**: Set the faction home location \
**Usage**: `/faction sethome` \
**Permission**: `piston.command.factions.sethome`

#### Messages
Sent to command sender:
* `command.faction.sethome.y`
  * **Condition**: Y elevation too high
* `command.faction.sethome.territory`
  * **Condition**: Not in faction territory
  
Broadcast to faction:
* `command.faction.sethome.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Show
**Description**: Show details about a faction \
**Usage**: `/faction show [faction|player]` \
**Aliases**: i, info, who \
**Permission**: `piston.command.factions.show`

#### Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| faction    | Faction query       | string      | false    | own player faction |
| player     | Player query        | string      | false    | n/a                |

#### Messages
Sent to command sender:
* `command.error.faction.required`
  * **Condition**: no faction provided

Messages in faction output:
* `command.faction.border`
* `command.faction.show.name`
  * Parameter 0: 
    * **Description**: faction name
    * **Type**: string
  * Parameter 1: 
    * **Description**: online users
    * **Type**: integer
  * Parameter 2: 
    * **Description**: total users
    * **Type**: integer
* `command.faction.show.name-with-home`
  * Parameter 0: 
    * **Description**: faction name
    * **Type**: string
  * Parameter 1: 
    * **Description**: online users
    * **Type**: integer
  * Parameter 2: 
    * **Description**: total users
    * **Type**: integer
  * Parameter 3: 
    * **Description**: faction home x co-ordinate
    * **Type**: integer
  * Parameter 3: 
    * **Description**: faction home z co-ordinate
    * **Type**: integer
* `command.faction.show.user-format.delimiter`
* `command.faction.show.user-format.online`
* `command.faction.show.user-format.offline`
* `command.faction.show.announcement`
  * **Condition**: Only if sender can view announcement
  * Parameter 0: 
    * **Description**: faction announcement
    * **Type**: string
* `command.faction.show.stats`
  * Parameter 0: 
    * **Description**: faction balance
    * **Type**: integer
  * Parameter 1: 
    * **Description**: faction kills
    * **Type**: integer
  * Parameter 2: 
    * **Description**: faction koth captures
    * **Type**: integer
* `command.faction.show.creation`
  * **Condition**: If faction date creation is shown (config option `messages.options.faction.show.creation.display`)
  * Parameter 0: 
    * **Description**: faction creation date
    * **Type**: string
* `command.faction.show.dtr`
  * Parameter 0: 
    * **Description**: faction dtr
    * **Type**: string
  * Parameter 1:
    * **Description**: faction max dtr
    * **Type**: string
* `command.faction.show.freeze`
  * **Condition**: Only if faction dtr is frozen
  * Parameter 0: 
    * **Description**: faction dtr freeze duration
    * **Type**: integer

[//]: <> (-----------------------------------------------------------------)

### Stuck
**Description**: Teleport to a safe location \
**Usage**: `/faction stuck` \
**Permission**: `piston.command.factions.stuck`

#### Messages
Sent to command sender:
* `command.faction.world`
  * **Condition**: Must be in overworld
* `command.faction.timer.active`
  * **Condition**: Teleport timer already active
* `sumo.command`
  * **Condition**: Cannot use command in sumo tournament
* `command.faction.stuck.failed`
  * **Condition**: No safe location found
* `command.faction.timer.success`
  * Parameter 0: 
    * **Description**: static text
    * **Value**: `a safe location`
    * **Type**: string
  * Parameter 1: 
      * **Description**: time to teleport
      * **Type**: string
* `command.faction.timer.warn.move`
  * Parameter 0: 
    * **Description**: static value
    * **Value**: `2`
    * **Type**: integer

[//]: <> (-----------------------------------------------------------------)

### Unclaim
**Description**: Unclaim land from the faction \
**Usage**: `/faction unclaim [all]` \
**Permission**: `piston.command.factions.unclaim`

#### Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| all        | Unclaim all claims  | string      | false    | n/a                |

#### Messages
Sent to command sender:
* `command.faction.raidable`
  * **Condition**: Cannot unclaim when raidable
* `command.faction.unclaim.not-owner`
  * **Condition**: Only the owner can unclaim

Broadcast to faction:
* `command.faction.unclaim.home`
  * **Condition**: Faction home was unset in the process
* `command.faction.unclaim.refund`
  * Parameter 0: 
    * **Description**: amount refunded
    * **Type**: integer
* `command.faction.unclaim.remove`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of claims removed
    * **Type**: integer
    
[//]: <> (-----------------------------------------------------------------)

### Uninvite
**Description**: Remove an invitation to a player \
**Usage**: `/faction uninvite <player>` \
**Aliases**: deinv, deinvite, uninv, revoke \
**Permission**: `piston.command.factions.uninvite`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.uninvite.not-invited`
  * **Condition**: Target player not invited

Sent to target player:
* `command.faction.uninvite.target`
  * Parameter 0: 
    * **Description**: faction name
    * **Type**: string
  * Parameter 1: 
    * **Description**: command sender name
    * **Type**: integer

Broadcast to faction:
* `command.faction.uninvite.notify` 
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string

[//]: <> (-----------------------------------------------------------------)

### Withdraw
**Description**: Withdraw money from the faction balance \
**Usage**: `/faction withdraw <amount>` \
**Aliases**: w \
**Permission**: `piston.command.factions.withdraw`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| amount     | Amount to withdraw         | integer     | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.withdraw.money`
  * **Condition**: Faction has no money

Sent to faction:
* `command.faction.withdraw.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: amount withdrawn
    * **Type**: integer
    
## Staff Sub-commands
    
[//]: <> (-----------------------------------------------------------------)

### Chatspy
**Description**: Spy on the chat of a faction \
**Usage**: `/faction chatspy <list|add|remove> <faction>` \
**Permission**: `piston.command.factions.chatspy`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| list       | Show list of factions      | string      | true     |  n/a    |
| add        | Add a faction to spy on    | string      | true     |  n/a    |
| remove     | Remove a spied on faction  | string      | true     |  n/a    |
| faction    | Name of faction            | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.staff.chatspy.invalid`
  * **Condition**: No faction provided
* `command.faction.staff.chatspy.list`
  * Parameter 0: 
    * **Description**: list of factions
    * **Type**: string
* `command.faction.staff.chatspy.add`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
* `command.faction.staff.chatspy.remove`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Claimfor
**Description**: Receive a claim wand or claim land for another faction \
**Usage**: `/faction claimfor [faction]` \
**Permission**: `piston.command.factions.claimfor`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| faction    | Name of faction            | string      | false    |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.claim.inv`
  * **Condition**: No inventory space for claim wand
* `command.faction.claim.claiming`
  * **Condition**: Already claiming
* `command.faction.staff.claimfor.selection`
  * **Condition**: Incomplete selection
* `command.faction.staff.claimfor.success`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string

[//]: <> (-----------------------------------------------------------------)

### Clearclaims
**Description**: Clear the claims of a faction \
**Usage**: `/faction clearclaims <faction>` \
**Permission**: `piston.command.factions.clearclaims`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| faction    | Name of faction            | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.staff.clearclaims.success`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
    
Sent to faction:
* `command.faction.staff.clearclaims.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Clearallclaims
**Description**: Clear the claims of all facitons \
**Usage**: `/faction clearallclaims` \
**Permission**: `piston.command.factions.clearallclaims`

#### Messages
Sent to command sender:
* `command.error.console`
  * **Condition**: Must be console

Broadcast to server:
* `command.faction.staff.clearallclaims.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Forcedemote
**Description**: Forces the demotion of a faction member \
**Usage**: `/faction forcedemote <player>` \
**Permission**: `piston.command.factions.forcedemote`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.staff.forcerank.success`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
  * Parameter 1: 
    * **Description**: new role
    * **Type**: string
    
Sent to faction:
* `command.faction.staff.forcedemote.notify`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
  * Parameter 1: 
    * **Description**: new role
    * **Type**: string
  * Parameter 2: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Forcejoin
**Description**: Forcefully join a faction \
**Usage**: `/faction forcejoin <faction>` \
**Permission**: `piston.command.factions.forcejoin`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| faction    | Name of faction            | string      | true     |  n/a    |

#### Messages
Sent to faction:
* `command.faction.staff.forcejoin.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Forcekick
**Description**: Forces the demotion of a faction member \
**Usage**: `/faction forcekick <player>` \
**Permission**: `piston.command.factions.forcekick`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.staff.forcekick.success`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
    
Sent to faction:
* `command.faction.staff.forcekick.notify`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
  * Parameter 1: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Forcepromote
**Description**: Forces the promotion of a faction member \
**Usage**: `/faction forcepromote <player>` \
**Permission**: `piston.command.factions.forcepromote`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| player     | Name of player             | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.faction.staff.forcerank.success`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
  * Parameter 1: 
    * **Description**: new role
    * **Type**: string
    
Sent to faction:
* `command.faction.staff.forcepromote.notify`
  * Parameter 0: 
    * **Description**: name of target player
    * **Type**: string
  * Parameter 1: 
    * **Description**: new role
    * **Type**: string
  * Parameter 2: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Forceunclaimhere
**Description**: Forces land unclaim at current location \
**Usage**: `/faction forceunclaimhere` \
**Permission**: `piston.command.factions.forceunclaimhere`

#### Messages
Sent to command sender:
* `command.faction.staff.forceunclaimhere.nothing`
  * **Condition**: No claim at location
* `command.faction.staff.forceunclaimhere.nothing`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
    
Sent to faction:
* `command.faction.unclaim.remove`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: static value
    * **Value**: `1`
    * **Type**: integer
    
[//]: <> (-----------------------------------------------------------------)

### Remove
**Description**: Removes a faction \
**Usage**: `/faction remove <faction>` \
**Permission**: `piston.command.factions.remove`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| faction    | Name of faction            | string      | true     |  n/a    |

#### Messages
Broadcast to server:
* `command.faction.staff.remove.notify`
  * Parameter 0: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 1: 
    * **Description**: name of command sender
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Setdtr
**Description**: Sets the dtr of a faction \
**Usage**: `/faction setdtr <faction> <value> <reason>` \
**Aliases**: dtr, sdtr \
**Permission**: `piston.command.factions.setdtr`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| faction    | Name of faction            | string      | true     |  n/a    |
| value      | New dtr (-5 <= n <= 32)    | decimal     | true     |  n/a    |
| reason     | Reason for change          | string      | true     |  n/a    |

#### Messages
Broadcast to server:
* `command.faction.staff.setdtr.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 2: 
    * **Description**: new dtr
    * **Type**: decimal
  * Parameter 3: 
    * **Description**: reason for change
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Setfreeze
**Description**: Sets the dtr freeze of a faction \
**Usage**: `/faction setdtr <faction> <seconds> <reason>` \
**Aliases**: setdtrregen, dtrregen, dtregen, setdtregen, sdtrregen, sdr, regen, freeze, setdtrfreeze \
**Permission**: `piston.command.factions.setdtrregen`

#### Parameters
| Parameter  | Description                    | Type        | Required | Default |
| ---------- | ------------------------------ | ----------- | -------- | ------- |
| faction    | Name of faction                | string      | true     |  n/a    |
| seconds    | Seconds to freeze for (n >= 0) | integer     | true     |  n/a    |
| reason     | Reason for change              | string      | true     |  n/a    |

#### Messages
Broadcast to server:
* `command.faction.staff.setfreeze.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 2: 
    * **Description**: time frozen for
    * **Type**: string
  * Parameter 3: 
    * **Description**: reason for change
    * **Type**: string
    
[//]: <> (-----------------------------------------------------------------)

### Toggleflag
**Description**: Toggles a boolean flag on a faction \
**Usage**: `/faction toggleflag <faction> <flag>` \
**Permission**: `piston.command.factions.toggleflag`

#### Parameters
| Parameter  | Description                    | Type        | Required | Default |
| ---------- | ------------------------------ | ----------- | -------- | ------- |
| faction    | Name of faction                | string      | true     |  n/a    |
| flag       | Flag to toggle                 | string      | true     |  n/a    |

#### Flags
Used faction flags:
* `SAFEZONE`
* `SPECIAL`
* `GLOWSTONE`
* `DENY_PVP_TIMER`

#### Messages
Broadcast to server:
* `command.faction.staff.toggleflag.notify`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: flag
    * **Type**: string
  * Parameter 2: 
    * **Description**: name of faction
    * **Type**: string
  * Parameter 3: 
    * **Description**: new state
    * **Type**: boolean