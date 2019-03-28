# Slowchat
**Syntax**: `/slowchat <seconds>` \
**Aliases**: slow, sc \
**Permission**: `piston.command.default.slowchat`

## Brief Description
Sets a delay between chat messages

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.slowchat`

## Messages
Broadcast to server:
* `command.staff.chat.slow.enable`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of seconds
    * **Type**: integer
* `command.staff.chat.slow.disable`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string