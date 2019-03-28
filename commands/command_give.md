# Give
**Syntax**: `/give <player> <item|numeric> [amount [itemmeta..]]` \
**Permission**: `piston.command.default.give`

## Brief Description
Give an item to a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.give`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | true     | n/a                |
| item       | Item type           | [Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)      | true    | n/a     |
| numeric    | Item id             | integer     | true     | n/a                |
| amount     | Stack size          | integer     | false    | 1                  |
| itemmeta   | Item meta           | string      | false    | n/a                |

## Flags
| Flag  | Description                              | Required | Argument | Argument Type |
| ----- | ---------------------------------------- | -------- | -------- | ------------- |
| -s    | Don't send a message to receiving player | false    | n/a      | n/a           |

## Item Metadata
Adding metadata to the item is done through the `itemmeta` parameter. Possible options are:
* name
  * sets the name of the item
  * add spaces with `_`
* lore
  * adds lore to the item
  * separate lines with `|`
* data
  * sets the durability of the item
  
**Example Usage**: `/give <player> STONE 1 name:Custom_Name lore:First_Line|Second_Line data:1`

## Messages
Sent to command sender:
* `command.give.out`
  * Parameter 0: 
    * **Description**: item amount
    * **Type**: integer
  * Parameter 1: 
    * **Description**: item material
    * **Type**: string
  * Parameter 2: 
    * **Description**: target player name
    * **Type**: string
    
Sent to target player
* `command.give.in`
  * Parameter 0: 
    * **Description**: item amount
    * **Type**: integer
  * Parameter 1: 
    * **Description**: item material
    * **Type**: string
  * Parameter 2: 
    * **Description**: sender name
    * **Type**: string