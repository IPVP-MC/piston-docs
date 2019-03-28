# Suicide
**Syntax**: `/suicide` \
**Aliases**: kill, kys, kms \
**Permission**: `piston.command.default.suicide`

## Brief Description
Commit suicide

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.suicide`

## Messages
Sent to command sender:
* `command.suicide.tagged`
  * **Condition**: Tagged suicide attempt
* `command.suicide.timer-active`
  * **Condition**: Timer currently active
* `sumo.command`
  * **Condition**: Cannot use command in sumo tournament
* `suicide.start`
  * Parameter 0: 
      * **Description**: time until teleport 
      * **Type**: string
* `command.faction.timer.warn.move`
  * Parameter 0: 
    * **Description**: static value (number of seconds)
    * **Value**: `2`
    * **Type**: integer