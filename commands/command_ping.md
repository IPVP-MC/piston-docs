# Ping
**Syntax**: `/ping [player]` \
**Aliases**: pv, playervault \
**Permission**: `piston.command.default.ping`

## Brief Description
View the ping of a player, or the average of the server

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.ping`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | n/a                |

## Messages
Sent to command sender:
* `command.ping.empty`
  * **Condition**: No average ping available
* `command.ping.average`
  * Parameter 0: 
    * **Description**: average ping of all players
    * **Type**: integer
* `command.ping.average`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target player ping
    * **Type**: integer