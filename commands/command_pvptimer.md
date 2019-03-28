# Pvptimer
**Syntax**: `/pvptimer <subcommand> [opts...]` \
**Aliases**: pvp

## Brief Description
PVP timer related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.pvptimer.*`
      - `piston.command.pvptimer.enable`
      - `piston.command.pvptimer.time`
      - `piston.command.pvptimer.set`

## Sub-commands

### Off
**Description**: Enable player versus player combat \
**Usage**: `/pvptimer off` \
**Aliases**: enable \
**Permission**: `piston.command.pvptimer.enable` 

#### Messages
Sent to command sender:
* `command.timer.none`
  * **Condition**: When the player has no timer
* `command.timer.removed`
  
[//]: <> (-----------------------------------------------------------------) 

### Time
**Description**: Checks the remaining time an invincibility timer has
**Usage**: `/pvptimer check [player]` \
**Aliases**: time \
**Permission**: `piston.command.pvptimer.check`

#### Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

#### Messages
Sent to command sender:
* `command.timer.none`
  * **Condition**: If the target user has no timer
* `command.timer.time.expiry`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: time remaining on timer
    * **Type**: string
  
[//]: <> (-----------------------------------------------------------------) 

### Set
**Description**: Give a player some lives \
**Usage**: `/pvptimer set <player> <minutes>` \
**Permission**: `piston.command.pvptimer.set`

#### Parameters
| Parameter  | Description              | Type        | Required | Default            |
| ---------- | ------------------------ | ----------- | -------- | ------------------ |
| player     | Online player name       | string      | true     | n/a                |
| minutes    | Timer time (minutes > 0) | integer     | true     | n/a                |

#### Messages
Sent to command sender:
* `command.timer.set.out`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of minutes
    * **Type**: integer
  
Sent to target player:
* `command.timer.set.in`
  * Parameter 0: 
    * **Description**: number of minutes
    * **Type**: integer