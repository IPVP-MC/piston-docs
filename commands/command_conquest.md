# Conquest
**Syntax**: `/conquest <subcommand> [opts...]` \
**Aliases**: conquests

## Brief Description
Conquest related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.conquest.*`
      - `piston.command.conquest.add`
      - `piston.command.conquest.remove`
      - `piston.command.conquest.start`
      - `piston.command.conquest.stop`

## Sub-commands

### Add
**Description**: Add a capture point to the conquest \
**Usage**: `/conquest add <name>` \
**Permission**: `piston.command.conquest.add`

#### Parameters

| Parameter  | Description           | Type        | Required | Default |
| ---------- | --------------------- | ----------- | -------- | ------- |
| name       | Name of capture point | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.conquest.add`
  * Parameter 0: 
    * **Description**: name of new capture point
    * **Type**: string
* `command.koth.create-region`
  * **Condition**: If no KOTH region is selected

[//]: <> (-----------------------------------------------------------------) 

### Remove
**Description**: Remove a capture point from the conquest \
**Usage**: `/conquest remove <name>` \
**Permission**: `piston.command.conquest.remove`

#### Parameters

| Parameter  | Description           | Type        | Required | Default |
| ---------- | --------------------- | ----------- | -------- | ------- |
| name       | Name of capture point | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.conquest.remove`
  * Parameter 0: 
    * **Description**: name of capture point
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Start
**Description**: Start the conquest \
**Usage**: `/conquest start` \
**Permission**: `piston.command.conquest.start`

[//]: <> (-----------------------------------------------------------------) 

### Stop
**Description**: Stop the conquest \
**Usage**: `/conquest stop` \
**Permission**: `piston.command.conquest.stop`
