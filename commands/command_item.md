# Item
**Syntax**: `/item <item|numeric> [amount [itemmeta..]]` \
**Aliases**: items, i \
**Permission**: `piston.command.default.item`

## Brief Description
Give an item to yourself

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.item`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| item       | Item type           | [Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)      | true    | n/a     |
| numeric    | Item id             | integer     | true     | n/a                |
| amount     | Stack size          | integer     | false    | 1                  |
| itemmeta   | Item meta           | string      | false    | n/a                |

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
  
**Example Usage**: `/item STONE 1 name:Custom_Name lore:First_Line|Second_Line data:1`

## Messages
Sent to command sender:
* `command.item`
  * Parameter 0: 
    * **Description**: item amount
    * **Type**: integer
  * Parameter 0: 
    * **Description**: item material
    * **Type**: string