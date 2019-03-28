# Combattag
**Syntax**: `/combattag [who]` \
**Aliases**: tag, combatlog, ct, check \
**Permission**: `piston.command.combattag.check`

[//]: <> (TODO: Player-only command indication) 

## Brief Description
View the combat tag time of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.combattag.*`
      - `piston.command.combattag.check`
      - `piston.command.combattag.check.others`

## Parameters

| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| who        | Online player name  | string      | false    |  current player    |

**Note**: When the `[who]` optional parameter is not specified, the target becomes the current player executing the command. 

#### Messages
Sent to command sender:
* `command.combat.expires`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: remaining duration (formatted date)
    * **Type**: string
* `command.combat.not-tagged`
  * **Condition**: If the target player is not combat tagged
* `command.combat.check.other`
  * **Condition**: When a player uses the `[who]` parameter without the `piston.command.combattag.check.others` permission
 