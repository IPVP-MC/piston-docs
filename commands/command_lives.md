# Lives
**Syntax**: `/lives <subcommand> [opts...]` \
**Aliases**: live, life, deathban, deathbans

## Brief Description
Lives and deathban related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.lives.*`
      - `piston.command.lives.check`
      - `piston.command.lives.checkdeathban`
      - `piston.command.lives.give`
      - `piston.command.lives.give.infinite`
      - `piston.command.lives.revive`
      - `piston.command.lives.revive.staff`
      - `piston.command.lives.set`
      - `piston.command.lives.cleardeathbans`

## Sub-commands

### Check
**Description**: Checks the number of lives that a player has \
**Usage**: `/lives check [player]` \
**Permission**: `piston.command.lives.check`

#### Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

**Note**: When the `[player]` optional parameter is not specified, the target becomes the current player executing the command. 

#### Messages
Sent to command sender:
* `command.lives.check`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of lives
    * **Type**: integer
  
[//]: <> (-----------------------------------------------------------------) 

### Checkdeathban
**Description**: Checks the current deathban status of a player \
**Usage**: `/lives checkdeathban <player>` \
**Aliases**: deathban, viewdeathban, viewdb, checkdb, cdb, vdb \
**Permission**: `piston.command.lives.checkdeathban`

#### Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | true     | n/a                |

#### Messages
Sent to command sender:
* `command.lives.not-banned`
  * **Condition**: If the user is online or is not deathbanned
* `command.lives.ban.date`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: time of deathban
    * **Type**: string
* `command.lives.ban.time`
  * Parameter 0: 
    * **Description**: remaining deathban time
    * **Type**: string
* `command.lives.ban.location`
  * Parameter 0: 
    * **Description**: x co-ordinate
    * **Type**: integer
  * Parameter 1: 
    * **Description**: y co-ordinate
    * **Type**: integer
  * Parameter 2: 
    * **Description**: z co-ordinate
    * **Type**: integer
  * Parameter 3: 
    * **Description**: world name
    * **Type**: string
* `command.lives.ban.reason`
  * Parameter 0: 
    * **Description**: reason for deathban
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Give
**Description**: Give a player some lives \
**Usage**: `/lives give <player> <amount>` \
**Aliases**: trade \
**Permission**: `piston.command.lives.give`

#### Parameters
| Parameter  | Description             | Type        | Required | Default            |
| ---------- | ----------------------- | ----------- | -------- | ------------------ |
| player     | Online player name      | string      | true     | n/a                |
| amount     | Number of lives (n > 0) | integer     | true     | n/a                |

#### Messages
Sent to command sender:
* `command.lives.give.out`
  * Parameter 0: 
    * **Description**: number of lives
    * **Type**: integer
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string
* `command.lives.insufficient`
  * **Condition**: If the sender has less lives than they are trying to give
  
Sent to target player:
* `command.lives.give.in`
  * Parameter 0: 
    * **Description**: number of lives
    * **Type**: integer
  * Parameter 1: 
    * **Description**: command sender name
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Revive
**Description**: Revives a death banned player \
**Usage**: `/lives revive [player]` \
**Permission**: `piston.command.lives.revive`

#### Parameters
| Parameter  | Description             | Type        | Required | Default            |
| ---------- | ----------------------- | ----------- | -------- | ------------------ |
| player     | Target player name      | string      | false    | n/a                |

**Note**: Player is only ever not entered when a dead player is logging in to revive themselves

#### Messages
Sent to command sender:
* `command.lives.revive.success`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
* `command.lives.revive.self`
  * When the user self-revives
* `command.lives.revive.other.fail`
  * **Condition**: If the sender does not have permission to revive other players
* `command.lives.not-banned`
  * **Condition**: If the target player is not death banned
* `command.lives.insufficient`
  * **Condition**: If the sender does not have enough lives 
  
[//]: <> (-----------------------------------------------------------------) 

### Set
**Description**: Sets the lives count of a player \
**Usage**: `/lives set <player> <amount>` \
**Permission**: `piston.command.lives.set`

#### Parameters
| Parameter  | Description              | Type        | Required | Default            |
| ---------- | ------------------------ | ----------- | -------- | ------------------ |
| player     | Online player name       | string      | true     | n/a                |
| amount     | Number of lives (n >= 0) | integer     | true     | n/a                |

#### Messages
Sent to command sender:
* `command.lives.set.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 2: 
    * **Description**: number of lives
    * **Type**: integer
    
[//]: <> (-----------------------------------------------------------------) 

### Cleardeathbans
**Description**: Clears all deathbans \
**Usage**: `/lives cleardeathbans` \
**Permission**: `piston.command.lives.cleardeathbans`

#### Messages
Broadcast to server:
* `command.lives.clearbans.notify`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string
