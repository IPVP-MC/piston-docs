# Pay
**Syntax**: `/pay [player]` \
**Permission**: `piston.command.default.pay`

## Brief Description
Pay a player some money

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.pay`
      - `piston.command.default.pay.infinite`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.pay.self`
  * **Condition**: Sender cannot self pay
* `command.error.balance.insufficient`
  * **Condition**: Sender has insufficient money
* `command.pay.out`
  * Parameter 0: 
    * **Description**: amount of money sent
    * **Type**: integer
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string

Sent to target player:
* `command.pay.in`
  * Parameter 0: 
    * **Description**: amount of money sent
    * **Type**: integer
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string