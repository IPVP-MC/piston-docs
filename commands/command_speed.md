# Speed
**Syntax**: `/speed <speed> [player]` \
**Permission**: `piston.command.default.speed`

## Brief Description
Change the speed of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.speed`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| speed      | Speed value         | decimal     | true     | n/a                |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.speed.success`
  * Parameter 0: 
    * **Description**: type of speed (flight or walk)
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 2: 
    * **Description**: speed value
    * **Type**: decimal