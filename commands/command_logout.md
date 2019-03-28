# Logout
**Syntax**: `/logout` \
**Aliases**: log, lo \
**Permission**: `piston.command.combattag.logout`

## Brief Description
Safely log out of the server without spawning an NPC logger

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.combattag.*`
      - `piston.command.combattag.logout`

#### Messages
Sent to command sender:
* `combat.logout.initial`
  * Parameter 0: 
    * **Description**: number of seconds until logout
    * **Type**: integer
* `combat.logout.already`
  * **Condition**: If the target player is already logging out
 