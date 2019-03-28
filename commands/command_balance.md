# Balance
**Syntax**: `/balance [player]` \
**Aliases**: bal \
**Permission**: `piston.command.default.balance`

## Brief Description
Check the balance of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.balance`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.balance`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
  * Parameter 0: 
    * **Description**: target player balance
    * **Type**: integer