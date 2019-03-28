# Helpop
**Syntax**: `/helpop <text>` \
**Aliases**: panic \
**Permission**: `piston.command.staff.helpop`

## Brief Description
Request help from a staff member

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.staff.*`
      - `piston.command.staff.helpop`
      - `piston.command.staff.helpop.delay`
  - `piston.notify.*`
    - `piston.notifiy.command.*`
      - `piston.notify.command.helpop`

## Parameters
| Parameter  | Description            | Type        | Required | Default            |
| ---------- | ---------------------- | ----------- | -------- | ------------------ |
| text       | Message about problem  | string      | true     | n/a                |

## Messages
Sent to command sender:
* `command.staff.request.cooldown`
  * **Condition**: Sent a request too fast
  * Parameter 0: 
    * **Description**: time until next allowed request
    * **Type**: string 
* `command.staff.help.sent`

Broadcast:
* `command.staff.help.notify`
  * Only to those with permission `piston.notify.command.helpop`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string 
  * Parameter 0: 
    * **Description**: help text
    * **Type**: string 