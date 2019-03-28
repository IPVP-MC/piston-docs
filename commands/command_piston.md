# Piston
**Syntax**: `/piston <subcommand>` \

## Brief Description
Piston feature control

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.reload`

## Sub-commands

### Reload
**Description**: Reload the piston configuration \
**Usage**: `/piston reload` \
**Permission**: `piston.command.reload`

#### Messages
Sent to command sender:
* `command.reload`