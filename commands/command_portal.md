# Portal
**Syntax**: `/portal` \
**Aliases**: endportal, eportal, ep, portl, endportl, eportl \
**Permission**: `piston.command.default.portal`

## Brief Description
Starts a countdown to light a valid end portal

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.portal`

## Messages
Sent to command sender:
* `command.portal.center`
  * **Condition**: Not standing in the center of a portal
* `command.portal.success`
* `command.portal.lighting`
  * Parameter 0: 
    * **Description**: static value (number of seconds)
    * **Value**: `5`
    * **Type**: integer