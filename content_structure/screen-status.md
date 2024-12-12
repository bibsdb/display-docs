---
layout: default
title: Screen status
parent: Content Structure
nav_order: 8
---

# Screen status

##  List view

In the list view of screens, there is a column called "Status".

This column shows the status of the connection of a "screen" in the administration and an
actual "machine" running the screen data. 

This status can be:

* "+ Tilkobl": The screen is not connected to a machine.
* ✓ (green):  The machine is connected and running the latest code.
* i (yellow circle): The machine is not running the newest released code.
* ! (red triangle): The machine has not called the API within the last hour or the access token is expired.

## Screen edit view

In the screen edit view, the "Tilkobling" section shows the status of the connection between the
screen entity and a machine running the screen data.

The status can be:

* "Skærmen er tilkoblet" (green): The machine is connected and running the latest code.
* "Skærmen kører ikke seneste udgivelse" (yellow circle): The machine is not running the newest released code.
* "Skærmen har ikke kommunikeret i mere end en time" (red triangle): The machine has not called the API the latest hour.

Furthermore, the section "Tilkobling" will show the following data:

```text
* Seneste kommunikation: 14/12 2024 11:35
* Version: 1.0.9
* Kodeudgivelsestidspunkt: 17/6 2024 17:26
```

This shows when the latest communication has occured, what client version the machine is running,
and the time of client code release.
