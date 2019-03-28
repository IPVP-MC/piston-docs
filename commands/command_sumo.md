# Sumo
**Syntax**: `/sumo <subcommand> [opts...]` \
**Aliases**: sum, sumow, sumowrestle, wrestle

## Brief Description
Sumo related sub-commands

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.sumo.*`
      - `piston.command.sumo.start`
      - `piston.command.sumo.join`
      - `piston.command.sumo.leave`

## Sub-commands

### Start
**Description**: Start a sumo wrestling competition \
**Usage**: `/sumo start <max-players>` \
**Permission**: `piston.command.sumo.start`

#### Parameters

| Parameter   | Description                            | Type        | Required | Default |
| ----------- | -------------------------------------- | ----------- | -------- | ------- |
| max-players | Max players in sumo tournament (n > 2) | integer     | true     |  n/a    |

#### Messages
Sent to command sender:
* `sumo.disabled`
  * **Condition**: Sumo tournaments are disabled
* `sumo.running`
  * **Condition**: Sumo event is currently running
* `sumo.combat`
  * **Condition**: Command sender in combat
* `sumo.staff`
  * **Condition**: Command sender in staff mode
* `sumo.timer`
  * **Condition**: Command sender has a timer
* `sumo.start-delay`
  * **Condition**: Starting a sumo before cooldown delay
  
Broadcast to server:
* `sumo.host`
  * Parameter 0: 
    * **Description**: name of host
    * **Type**: string

[//]: <> (-----------------------------------------------------------------) 

### Join
**Description**: Join a sumo wrestling queue \
**Usage**: `/sumo join` \
**Permission**: `piston.command.sumo.join`

#### Messages
Sent to command sender:
* `sumo.none`
  * **Condition**: No tournament active
* `sumo.started`
  * **Condition**: Tournament has already started
* `sumo.already-joined`
  * **Condition**: Already in queue
* `sumo.combat`
  * **Condition**: Command sender in combat
* `sumo.staff`
  * **Condition**: Command sender in staff mode
* `sumo.timer`
  * **Condition**: Command sender has a timer
  
Broadcast to server:
* `sumo.join`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
  * Parameter 1: 
    * **Description**: current players in tournament
    * **Type**: integer
  * Parameter 2: 
    * **Description**: max players in tournament
    * **Type**: integer

[//]: <> (-----------------------------------------------------------------) 

### Leave
**Description**: Start the conquest \
**Usage**: `/sumo leave` \
**Permission**: `piston.command.sumo.leave`

#### Messages
Sent to command sender:
* `sumo.none`
  * **Condition**: No tournament active
* `sumo.not-participant`
  * **Condition**: Command sender not in tournament
* `sumo.leave-fighting`
  * Parameter 0: 
    * **Description**: name of sender
    * **Type**: string
* `sumo.leave`
