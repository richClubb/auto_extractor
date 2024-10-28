Auto Extractor
--------------

This is the starting repo for the automatic dust extractor control for Fizzpop.

# Problem Definition

We have a good size wood shop with a large number of machine tools and it's frustrating when you need to make a cut to; go, turn on the extractor, open the blast gate and then make the cut, then do the same in reverse. Most often people don't so the dust builds up near the machines. This in turn creates excess dust and mess which is bad for health and also just general tidiness and safety.

# Requirements

* Ability to turn the main dust extractor on and off with overrun after the machine is turned off.
* Ability to control the blast gates for each of the machines
* Extensible to new machines should work for 10+ machines
* Open-source hardware and software

## Stretch goals

* Air quality monitoring to control a air purifier
* Stats page for air quality
* Speed control for the main extractor? Is this worth doing?

# Known difficulties

## Usage / power on-off 

The machines don't have a common power interface so it might be difficult to figure out when the machine is running.
* The table saw is 3 phase
* Most of the other machines are single phase

## Multiple machines in use at the same time

Each extra gate you open will create extra paths for air to flow, at some point too many open gates will mean that the ariflow through any one channel will not be enough for dust to clear.
* prioritise the "most important" path
* only open the maximum number of ports

## Manual Control of Blast Gates

If the system goes wrong it should be easy to manually override the blast gate actuator and use it manually.

## Blast gate locations

The blast gates are sometimes not physically near the machine.

# Initial Ideas

The system will consist of; central controller, blast gate actuators and machine monitors.

Communication over CAN as it's easy to route to different areas of the room

Power for the leaf nodes will be via POE, the motors shouldn't need that much current.
