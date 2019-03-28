# Report
**Syntax**: `/report <player> <text>` \
**Aliases**: panic \
**Permission**: `piston.command.staff.report`

## Brief Description
Access the vault of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.staff.*`
      - `piston.command.staff.report`
      - `piston.command.staff.report.delay`
  - `piston.notify.*`
    - `piston.notifiy.command.*`
      - `piston.notify.command.report`

## Parameters
| Parameter  | Description            | Type        | Required | Default            |
| ---------- | ---------------------- | ----------- | -------- | ------------------ |
| player     | Online player name     | string      | false    | current player     |
| text       | Report message         | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.staff.request.cooldown`
  * **Condition**: Sent a request too fast
  * Parameter 0: 
    * **Description**: time until next allowed request
    * **Type**: string 
* `command.staff.report.sent`

Broadcast:
* `command.staff.report.notify`
  * Only to those with permission `piston.notify.command.report`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string 
  * Parameter 0: 
    * **Description**: help text
    * **Type**: string 