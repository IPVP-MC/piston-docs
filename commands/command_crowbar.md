# Crowbar
**Syntax**: `/crowbar <subcommand> [opts...]` \
**Aliases**: cb, crow, wrench

## Brief Description
Crowbar related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.crowbar.*`
      - `piston.command.crowbar.give`

## Sub-commands

### Give
**Description**: Give a crowbar to a player \
**Usage**: `/crowbar give <player>` \
**Permission**: `piston.command.crowbar.give`

#### Parameters

| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| player     | Online player name  | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.crowbar.give.out`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
    
Sent to target player:
* `command.crowbar.give.in`
  * Parameter 0: 
    * **Description**: command sender name
    * **Type**: string