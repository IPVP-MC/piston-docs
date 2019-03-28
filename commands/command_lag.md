# Vault
**Syntax**: `/lag` \
**Permission**: `piston.command.default.lag`

## Brief Description
View server information

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.lag`

## Messages
Sent to command sender:
* `command.lag.uptime`
  * Parameter 0: 
    * **Description**: time the server has been online
    * **Type**: string
* `command.lag.tps`
  * Parameter 0: 
    * **Description**: average tps in past minute
    * **Type**: decimal
  * Parameter 1: 
    * **Description**: average tps in past 5 minutes
    * **Type**: decimal
  * Parameter 2: 
    * **Description**: average tps in past 15 minutes
    * **Type**: decimal
* `command.lag.max-mem`
  * Parameter 0: 
    * **Description**: max memory in MB
    * **Type**: integer
* `command.lag.alloc-mem`
  * Parameter 0: 
    * **Description**: allocated memory in MB
    * **Type**: integer
* `command.lag.free-mem`
  * Parameter 0: 
    * **Description**: free memory in MB
    * **Type**: integer
* `command.lag.total-space`
  * Parameter 0: 
    * **Description**: total disk space in GB
    * **Type**: integer
* `command.lag.free-space`
  * Parameter 0: 
    * **Description**: free disk space in GB
    * **Type**: integer
* `command.lag.world`
  * Sent for every loaded world
  * Parameter 0: 
    * **Description**: name of world
    * **Type**: string
  * Parameter 1: 
    * **Description**: number of loaded chunks
    * **Type**: integer
  * Parameter 2: 
    * **Description**: number of entities 
    * **Type**: integer
  * Parameter 3: 
    * **Description**: number of tile entities
    * **Type**: integer
  