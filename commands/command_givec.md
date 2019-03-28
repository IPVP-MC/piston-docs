# Givec
**Syntax**: `/givec <player> <config-path>` \
**Permission**: `piston.command.default.givec`

## Brief Description
Give an item defined in the configuration to a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.givec`

## Parameters
| Parameter   | Description           | Type        | Required | Default            |
| ----------- | --------------------- | ----------- | -------- | ------------------ |
| player      | Online player name    | string      | true     | n/a                |
| config-path | Path in configuration | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.givec.invalid`
  * **Condition**: Invalid configuration path
* `command.givec.out`
  * Parameter 0: 
    * **Description**: configuration path
    * **Type**: string
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string