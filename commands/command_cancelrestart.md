# Cancelrestart
**Syntax**: `/cancelrestart` \
**Aliases**: stoprestart \
**Permission**: `piston.command.default.restart.cancel`

## Brief Description
Cancels the current server restart task

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.restart.cancel`

## Messages
Sent to command sender:
* `command.restart.not.exists`
  * **Condition**: No restart task to cancel
* `command.restart.stopped`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string