# Crate
**Syntax**: `/crate <subcommand> [opts...]` \
**Aliases**: crates, cratekey, cratekeys

## Brief Description
Crate related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.crate.*`
      - `piston.command.crate.give`
      - `piston.command.crate.give-all`

## Sub-commands

### Give
**Description**: Give a crate to a player \
**Usage**: `/crate give <player> <key> [amount]` \
**Permission**: `piston.command.crate.give`

#### Parameters

| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| player     | Online player name  | string      | true     |  n/a    |
| key        | Configured key name | string      | true     |  n/a    |
| amount     | Number of keys      | integer     | false    |  1      |

#### Messages
Sent to command sender:
* `command.crate.give`
  * Parameter 0: 
    * **Description**: Key name
    * **Type**: string
  * Parameter 1:
    * **Description**: Key name
    * **Type**: string 
    
Sent to target player:
* `command.crate.receive`
  * Parameter 0: 
    * **Description**: Key name
    * **Type**: string
  * Parameter 1:
    * **Description**: Command sender name
    * **Type**: string 
* `item.dropped`
  * **Condition**: Only when player inventory full and overflow dropped
  
### Giveall
**Description**: Give a crate to all players currently on the server \
**Usage**: `/crate giveall <key> [amount]` \
**Permission**: `piston.command.crate.give-all`

#### Parameters

| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| key        | Configured key name | string      | true     |  n/a    |
| amount     | Number of keys      | integer     | false    |  1      |

#### Messages
Sent to command sender:
* `command.crate.give-all`
  * Parameter 0: 
    * **Description**: Key name
    * **Type**: string
  * Parameter 1:
    * **Description**: Number of players that received the key
    * **Type**: integer
    
Sent to receiving player:
* `command.crate.receive`
  * Parameter 0: 
    * **Description**: Key name
    * **Type**: string
  * Parameter 1:
    * **Description**: Command sender name
    * **Type**: string 
* `item.dropped`
  * **Condition**: Only when player inventory full and overflow dropped