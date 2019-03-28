# Fly
**Syntax**: `/fly [player]` \
**Permission**: `piston.command.default.fly`

## Brief Description
Allow players to fly

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.fly`
      - `piston.command.default.fly.others`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.fly.other`
  * **Condition**: Sender requires `pison.command.default.fly.others` permission
* `command.fly.success`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: whether the player can fly-
    * **Type**: boolean
