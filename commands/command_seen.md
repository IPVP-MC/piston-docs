# Vault
**Syntax**: `/seen [player]` \
**Aliases**: show \
**Permission**: `piston.command.default.seen`

## Brief Description
View the current online or offline time of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.seen`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Player name         | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.error.target.missing`
  * **Condition**: Target player has never logged in
* `command.seen.time`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: target online status ("online" or "offline")
    * **Type**: string
  * Parameter 2: 
    * **Description**: amount of time since last login or logout
    * **Type**: string
* `command.seen.uuid`
  * **Requirement**: Console only
  * Parameter 0: 
    * **Description**: target player UUID
    * **Type**: string
* `command.seen.ip`
  * **Requirement**: Console only
  * Parameter 0: 
    * **Description**: target player IP address
    * **Type**: string