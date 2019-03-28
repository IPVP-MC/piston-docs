# World
**Syntax**: `/world <world>` \
**Permission**: `piston.command.default.world`

## Brief Description
Teleport between worlds

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.world`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| world      | World name          | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.teleport-world`
  * Parameter 0: 
    * **Description**: world name
    * **Type**: string