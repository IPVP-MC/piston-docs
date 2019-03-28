# Restart
**Syntax**: `/restart <seconds>` \
**Aliases**: reboot \
**Permission**: `piston.command.default.restart`

## Brief Description
Restart the server

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.restart`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.restart.exists`
  * **Condition**: Server already restarting
* `command.restart.start`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string