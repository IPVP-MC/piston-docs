# Ontime
**Syntax**: `/ontime [player]` \
**Aliases**: online, onlinetime, otime, ot, on, ont \
**Permission**: `piston.command.default.ontime`

## Brief Description
View the amount of time a player has spent on the server

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.ontime`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.ontime.nothing`
  * **Condition**: Target player has no tracked online time
* `command.ontime.text`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: ontime type ("played the server" or "sat still")
    * **Type**: string
  * Parameter 2: 
    * **Description**: amount of time
    * **Type**: string
  * Parameter 3: 
    * **Description**: amount of time today
    * **Type**: string
  * Parameter 4: 
    * **Description**: amount of time in current month
    * **Type**: string