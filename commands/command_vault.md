# Vault
**Syntax**: `/vault [player]` \
**Aliases**: pv, playervault \
**Permission**: `piston.command.default.vault`

## Brief Description
Access the vault of a player

## Permission Tree
- `piston.*`
  - `piston.command.*`
    - `piston.command.default.*`
      - `piston.command.default.vault`

## Parameters
| Parameter  | Description         | Type        | Required | Default            |
| ---------- | ------------------- | ----------- | -------- | ------------------ |
| player     | Online player name  | string      | false    | current player     |

## Messages
Sent to command sender:
* `command.vault.no-pages`
  * **Condition**: Sender has no vault pages
* `command.vault.sumo`
  * **Condition**: Sender is in a sumo match
* `command.vault.target.no-permissions`
  * **Condition**: Cannot view another players vault
* `command.vault.target.none`
  * **Condition**: Target player has no vault
* `command.vault.loading`
  * Loading the target players vault