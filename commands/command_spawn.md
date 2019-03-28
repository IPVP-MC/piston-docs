# Spawn
**Syntax**: `/spawn [-w]` \
**Permission**: `piston.command.default.spawn`

## Brief Description
Access the vault of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.spawn`
      - `piston.command.default.spawn.instant`

## Flags
| Flag  | Description                 | Required | Argument | Argument Type |
| ----- | --------------------------- | -------- | -------- | ------------- |
| -w    | Use current world spawn     | false    | n/a      | n/a           |

## Messages
Sent to command sender:
* `command.faction.home.tagged`
  * **Condition**: Cannot use spawn command when tagged
* `command.spawn.disabled`
  * **Condition**: Spawn command disabled
* `command.faction.timer.active`
  * **Condition**: Teleport timer active
* `command.faction.timer.warn.move`
  * Parameter 0: 
    * **Description**: static value (number of seconds)
    * **Value**: `2`
    * **Type**: integer
* `command.faction.timer.success`
  * Parameter 0: 
    * **Description**: static value 
    * **Value**: `spawn`
    * **Type**: string
  * Parameter 1: 
      * **Description**: time until teleport 
      * **Type**: string
* `command.spawn.success`
  * Successful instant teleportation