drone-competition
=======

API document for the Advisa drones

general
---

The drones can be controlled through a WebSocket API. The drones are stateful and as such commands will persist until halted. This means running the `front` command will cause the drone to go forwards until running the `front-stop` command.

initialization
---
Emit `request-drone` to ask the server for a specific drone. If one is availble you will get a successfull return and the name of the drone acquired. When a drone has been acquired successfully it is possible to continue issuing API commands to control the provided drone. This will also acquire the live stream from the drone's build-in camera. 

Alternatively emit `listen-drone` to acquire only the live stream.

Each of these require you to provide the drone name in order to request that specific drone. The available drones are:

- barbarossa
- overlord

api
----

- `takeoff`: Make the drone take of and place itself in a hover
- `land`: Land the drone, nice and easy
- `stop`: Stop the drone moving in its current direction
- `up`: Start going upwards
- `up-stop`: Stop going upwards
- `down`: Start going downwards
- `down-stop`: Stop going downwards
- `clockwise`: Start rotating clockwise
- `clockwise-stop`: Stop rotating clockwise
- `counter-clockwise`: Start rotating counter-clockwise
- `counter-clockwise-stop`: Stop rotating counter-clockwise
- `front`: Start going forwards
- `front-stop`: Stop going forwards
- `back`: Start going backwards
- `back-stop`: Stop going backwards
- `right`: Start going right
- `right-stop`: Stop going right
- `left`: Start going left
- `left-stop`: Stop going left
- `flip-left`: Make a flip to the left
- `flip-right`: Make a flip to the right
- `vz-dance`: Well, dance
- `disable-emergency`: Emergency disable the drone
    
example app
----

Check out the example app for some pointers and inspiration.
