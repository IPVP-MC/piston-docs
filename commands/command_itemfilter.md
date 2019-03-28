# Itemfilter
**Syntax**: `/itemfilter <subcommand> [opts...]` \
**Aliases**: filter, if, cobble, cobblestone

## Brief Description
Item filter related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.itemfilter.*`
      - `piston.command.itemfilter.add`
      - `piston.command.itemfilter.remove`
      - `piston.command.itemfilter.toggle`

## Sub-commands

### Add
**Description**: Prevent an item from being picked up \
**Usage**: `/itemfilter add <material> [durability]` \
**Permission**: `piston.command.itemfilter.add`

#### Parameters

| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| material   | Item material       | [Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)    | true     |  n/a    |
| durability | Item durability     | short       | false    |  0      |

#### Messages
Sent to command sender:
* `command.filter.added`
* `command.filter.duplicate`
  * **Condition**: If the players item filter already contains the item
  
### Remove
**Description**: Allow an item to be picked up \
**Usage**: `/itemfilter remove <material> [durability]` \
**Permission**: `piston.command.itemfilter.remove`

#### Parameters

| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| material   | Item material       | [Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)    | true     |  n/a    |
| durability | Item durability     | short       | false    |  0      |

#### Messages
Sent to command sender:
* `command.filter.remove`
* `command.filter.not`
  * **Condition**: If the players item filter does not contain the item

### Toggle
**Description**: Toggle the enabled state of an item filter \
**Usage**: `/itemfilter toggle` \
**Permission**: `piston.command.itemfilter.toggle`

#### Messages
Sent to command sender:
* `command.filter.toggle`
