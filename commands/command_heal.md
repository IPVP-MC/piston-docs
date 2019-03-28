# Heal
**Syntax**: `/heal [player] [-p]` \
**Permission**: `piston.command.default.heal`

## Brief Description
Heal yourself or a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.heal`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Flags
| Flag  | Description                 | Required | Argument | Argument Type |
| ----- | --------------------------- | -------- | -------- | ------------- |
| -p    | Clear target player potions | false    | n/a      | n/a           |

## Messages
Sent to command sender:
* `command.heal.out`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
    
Sent to target player:
* `command.heal.in`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string