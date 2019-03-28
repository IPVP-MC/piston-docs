# Feed
**Syntax**: `/feed [player]` \
**Aliases**: eat \
**Permission**: `piston.command.default.feed`

## Brief Description
Feed yourself or a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.feed`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.feed.out`
  * Parameter 0: 
    * **Description**: target player name
    * **Type**: string
    
Sent to target player:
* `command.feed.in`
  * Parameter 0: 
    * **Description**: sender name
    * **Type**: string