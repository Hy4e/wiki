---
id: GetVehicleHealth
title: GetVehicleHealth
description: Get the health of a vehicle.
tags: ["vehicle"]
---

## Description

Get the health of a vehicle.

| Name          | Description                                                                  |
| ------------- | ---------------------------------------------------------------------------- |
| vehicleid     | The ID of the vehicle to get the health of.                                  |
| &Float:health | A float variable in which to store the vehicle's health, passed by reference |

## Returns

1 - success

0 - failure (invalid vehicle ID).

The vehicle's health is stored in the referenced variable, not in the return value.

## Examples

```c
if(strcmp(cmdtext, "/repair", true) == 0)
{
    new Float:health;
    new veh = GetPlayerVehicleID(playerid);
    GetVehicleHealth(veh, health);
    if(health > 500) return SendClientMessage(playerid, COLOR_RED, "Vehicle doesn't need repairing!");
    SetVehicleHealth(veh, 1000);
    SendClientMessage(playerid, COLOR_GREEN, "Vehicle repaired!");
}
```

## Notes

:::tip

Full vehicle health is 1000, however higher values are possible and increase the health of the vehicle. For more information on health values, see here.

:::

:::tip

A vehicle catches on fire when its health is below 250. It will explode a few seconds later.

:::

## Related Functions

- [SetVehicleHealth](SetVehicleHealth.md): Set the health of a vehicle.
- [GetPlayerHealth](GetPlayerHealth.md): Find out how much health a player has.
- [GetPlayerArmour](GetPlayerArmour.md): Find out how much armour a player has.
