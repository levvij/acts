# Modularity
ACTS is split into replaceable modules.

## Physical Layer
### Traction Controller
The traction controller controls the traction units (= locomotives) within a train.
- EtherRail Traction Controller (dcc alternative over wifi)
- DCC Based Traction Controller (DCC++, Z21 LAN Protocol, ...)
- ...

### Route Controller
This controls all the route controlling units on the layout (points, turntables, ...).
- EtherRail Route Controller
- DCC Based Point Controller
- ...

### Signal Controller
This controls all the route controlling units on the layout (points, turntables, ...).
- EtherRail Signal Controller
- DCC Based Signal Controller
- ...

## Locating
The locator tries to figure out where a train is. 
The more inputs, the more accurate the location.
If possible use multiple of the following modules
- EtherRail Balise Magnet Locator
- EtherRail Power Monitor
- EtherRail RFID Sensor
- DCC Based Block Detection

## Safety
We do not recommend replacing the safety module ;)
This is implemented by the inspector module

## Pilot
- Automatic Train Pilot
- Manual Train Pilot (= a throttle)

## Router
Multiple routers modules might be used, to allow special operation within fiddle yards, ...
- Line Router
- Fiddle Yard Router
- Automatic Train Assembler Router
- Manual Router (= a throttle)

## Scheduler
A lot of different schedulers may be used to find the most optimal way to generate routes.
- Swiss Clock Face Scheduler (Taktfahrplan)
- Fixed Schedule
- ...