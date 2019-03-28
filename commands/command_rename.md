# Rename
**Syntax**: `/rename <name>` \
**Permission**: `piston.command.default.rename`

## Brief Description
Rename an item

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.rename`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| name       | Item name           | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.rename.hands-empty`
  * **Condition**: Sender has no item in hand
* `command.rename.not-allowed`
  * **Condition**: Cannot rename the current item
* `command.rename.colored`
  * **Condition**: Cannot rename a colored item
* `command.rename.invalid`
  * **Condition**: Invalid name provided
* `command.rename.success`
  * Parameter 0: 
    * **Description**: new item name
    * **Type**: string  


