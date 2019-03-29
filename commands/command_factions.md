# Factions
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

## Sub-commands

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
    
    
    
    
[//]: <> (history next)
