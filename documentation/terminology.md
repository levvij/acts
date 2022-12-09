# Terminology
ACTS tries to abstract each operating area into its own interchangeable program.

## District
A layout may be split into multiple districts. Each district can have each own controlling mechanism, for example a mainline or fiddle yard controller.
Each district keeps track of the trains it contains.

## Train
A train is a set of coupled locomotives and rail cars. It may only contain a single car.
Each train has a unique number (UUID). Splitting a train will result in two new trains with new unique numbers.

## Traction Unit
A traction unit is a locomotive or multiple units (DMU, EMU, ...). 
The traction unit will not refuse a command to run full speed into another unit, it has to rely on a unit from the second layer.

## Routing Unit
A routing unit is a turnout/point, turntable or any other piece of track which can switch a trains route.
The routing unit is not aware that a train will pass over it, it has to rely on accurate information from a layer 3 device.

## Stretch
A stretch defines a set of tracks which starts and ends at a routing unit or buffer. 

## Train Location
It is crucial for ACTS to know where the trains are located. A train is always treated as if it just made a huge speed boost or stopped entirely. An emergency stop will be triggered if a trains path (location + breaking distance) collides with another trains path. Limiting the possible location of a train will drastically increase the safety and frequency of trains.

## Face
A face defines a trains head or tail.
It can only ever be located in one district.
It has a max distance and min distance, as we are never sure where a train is exactly.

### Sensing Unit
A locating unit detects a trains location by sensing magnets, RFID chips, load sensors or light barriers.
The unit is not aware that a given input translates to a train being at a certain location - it is only responsible for reliably transmitting the input to a locator unit.

### Locator Unit
A locator unit combines sensor input from sensing units to estimate a trains faces as accurately as possible. 

## Inspector
The inspector is responsible for each trains safety - it has to actively avoid collisions by detecting breaking distance issues as far ahead as possible.

## Train Pilot
The pilot is responsible for one train. 
It is not aware of the trains journey.
It has to ensure that all traction units are controlled properly.
All speed limits will be watched too.

A human can act as the pilot too - Just be careful.

## Router
The router finds an optimal path for a train from A to B.
It makes sure to check in with other routers and might optimize their paths too.

## Scheduler
A scheduler defines journeys with a given planning strategy.
You can define a schedule manually, be entering each journey into a big table.
It might do this automatically, by taking both passenger and freight requests as an input (I am scared of the implementation of this feature).