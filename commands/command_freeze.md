# Freeze
**Syntax**: `/freeze <player>` \
**Aliases**: halt \
**Permission**: `piston.command.staff.freeze`

## Brief Description
Freeze a player, preventing all movement

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.staff.*`
      - `piston.command.staff.freeze`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.staff.freeze.off`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string 
* `command.staff.freeze.on`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string

Sent to target player:
* `command.staff.freeze.unfrozen`
  * When player gets unfrozen
* `command.staff.freeze.unfrozen`
  * When player gets frozen