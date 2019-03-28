# Restoreinventory
**Syntax**: `/restoreinventory <player> <reason>` \
**Aliases**: restoreinv, restore, inv, inventory, invrestore \
**Permission**: `piston.command.staff.restoreinventory`

## Brief Description
Restores the last death inventory of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.staff.*`
      - `piston.command.staff.restoreinventory`

## Parameters
| Parameter  | Description            | Type        | Required | Default            |
| ---------- | ---------------------- | ----------- | -------- | ------------------ |
| player     | Online player name     | string      | true     | n/a                |
| reason     | Reason for restoration | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.staff.restore.none`
  * **Condition**: Target has no inventory to restore
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
* `command.staff.restore.last`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: player who last restored
    * **Type**: string
    
Broadcast to server:
* `command.staff.restore.notify`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 1: 
    * **Description**: player who restored
    * **Type**: string
  * Parameter 2:
    * **Description**: reason for restoration
    * **Type**: string