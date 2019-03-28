# Recolor
**Syntax**: `/recolor <color>` \
**Permission**: `piston.command.default.recolor`

## Brief Description
Recolor an item

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.recolor`
  - `piston.recolor.*`
    - `piston.recolor.aqua`
    - `piston.recolor.black`
    - `piston.recolor.blue`
    - `piston.recolor.bold`
    - `piston.recolor.dark_aqua`
    - `piston.recolor.dark_blue`
    - `piston.recolor.dark_gray`
    - `piston.recolor.dark_green`
    - `piston.recolor.dark_purple`
    - `piston.recolor.dark_red`
    - `piston.recolor.gold`
    - `piston.recolor.gray`
    - `piston.recolor.green`
    - `piston.recolor.italic`
    - `piston.recolor.light_purple`
    - `piston.recolor.magic`
    - `piston.recolor.red`
    - `piston.recolor.reset`
    - `piston.recolor.strikethrough`
    - `piston.recolor.underline`
    - `piston.recolor.white`
    - `piston.recolor.yellow`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| color      | Online player name  | [ChatColor](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/ChatColor.html)   | true     | n/a           |

## Messages
Sent to command sender:
* `command.recolor.hands-empty`
  * **Condition**: Sender has no item in hand
* `command.recolor.no-name`
  * **Condition**: Tried to color item with no name
* `command.recolor.not-colored`
  * **Condition**: Tried to reset item with no color
* `command.recolor.not-allowed`
  * **Condition**: Cannot color the current item
* `command.recolor.no-color`
  * **Condition**: Sender has no allowed colors
* `command.recolor.valid`
  * Parameter 0: 
    * **Description**: list of allowed colors
    * **Type**: string
* `command.recolor.remove-success`
* `command.recolor.color-success`
  * Parameter 0: 
    * **Description**: used color
    * **Type**: string
* `command.recolor.purchase-more`