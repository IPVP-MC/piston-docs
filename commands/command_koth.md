# Koth
**Syntax**: `/koth <subcommand> [opts...]` \
**Aliases**: koths, king

## Brief Description
Koth related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.koth.*`
      - `piston.command.koth.list`
      - `piston.command.koth.create`
      - `piston.command.koth.delete`
      - `piston.command.koth.reschedule`
      - `piston.command.koth.start`
      - `piston.command.koth.stop`
      - `piston.command.koth.capturetime`
      - `piston.command.koth.maxduration`

## Sub-commands

### Start
**Description**: Start a new KOTH \
**Usage**: `/koth start <name>` \
**Permission**: `piston.command.koth.start`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| name       | Name of KOTH        | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.koth.start.running`
  * **Condition**: If there is already a KOTH running
  
[//]: <> (-----------------------------------------------------------------) 

### Stop
**Description**: Stop a running KOTH \
**Usage**: `/koth stop` \
**Permission**: `piston.command.koth.stop`

#### Messages
Sent to command sender:
* `command.koth.stop.none`
  * **Condition**: If there is no running KOTH
  
[//]: <> (-----------------------------------------------------------------) 

### List
**Description**: View the KOTH list \
**Usage**: `/koth list` \
**Permission**: `piston.command.koth.list`

#### Messages
Sent to command sender:
* `command.koth.list.header`
* `command.koth.list.entry`
  * Sent for every scheduled KOTH
  * Parameter 0: 
    * **Description**: name of KOTH
    * **Type**: string
  * Parameter 1: 
    * **Description**: duration remaining until start
    * **Type**: string
* `command.koth.list.footer`
* `command.koth.none-planned`
  * **Condition**: If there are no planned KOTHs
  
[//]: <> (-----------------------------------------------------------------) 

### Reschedule
**Description**: Refill the KOTH schedule \
**Usage**: `/koth reschedule` \
**Permission**: `piston.command.koth.reschedule`

#### Messages
Server broadcast:
* `koth.reschedule`
  * Parameter 0: 
    * **Description**: name of command sender
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Create
**Description**: Create a new KOTH from a claim selection \
**Usage**: `/koth create <name>` \
**Permission**: `piston.command.koth.create`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| name       | Name of KOTH        | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.koth.create`
  * Parameter 0: 
    * **Description**: name of KOTH
    * **Type**: string
* `command.koth.create-region`
  * **Condition**: If there is no selection, or if the selection is incomplete

[//]: <> (-----------------------------------------------------------------) 

### Delete
**Description**: Deletes an existing KOTH \
**Usage**: `/koth delete <name>` \
**Permission**: `piston.command.koth.delete`

#### Parameters
| Parameter  | Description         | Type        | Required | Default |
| ---------- | ------------------- | ----------- | -------- | ------- |
| name       | Name of KOTH        | string      | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.koth.delete`
  * Parameter 0: 
    * **Description**: name of KOTH
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Capturetime
**Description**: Sets the capture time of a KOTH \
**Usage**: `/koth capturetime <name> <seconds>` \
**Aliases**: setcapturetime, captime, setcaptime
**Permission**: `piston.command.koth.capturetime`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| name       | Name of KOTH               | string      | true     |  n/a    |
| seconds    | Capture time (seconds > 0) | integer     | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.koth.update-koth-time`
  * Parameter 0: 
    * **Description**: static value
    * **Type**: string
    * **Value**: `capture time`
  * Parameter 1: 
    * **Description**: name of KOTH
    * **Type**: string
  * Parameter 2: 
      * **Description**: formatted duration time
      * **Type**: string 

[//]: <> (-----------------------------------------------------------------) 

### Maxduration
**Description**: Sets the duration of a KOTH \
**Usage**: `/koth setduration <name> <seconds>` \
**Aliases**: duration, setduration
**Permission**: `piston.command.koth.maxduration`

#### Parameters
| Parameter  | Description                | Type        | Required | Default |
| ---------- | -------------------------- | ----------- | -------- | ------- |
| name       | Name of KOTH               | string      | true     |  n/a    |
| seconds    | Capture time (seconds > 0) | integer     | true     |  n/a    |

#### Messages
Sent to command sender:
* `command.koth.update-koth-time`
  * Parameter 0: 
    * **Description**: static value
    * **Type**: string
    * **Value**: `duration`
  * Parameter 1: 
    * **Description**: name of KOTH
    * **Type**: string
  * Parameter 2: 
      * **Description**: formatted duration time
      * **Type**: string
