# Underfloor heating pump controller

A underfloor heating pump controller is a device to save energy. The pump will only run when there is a demand for heating up the room. The following situations are covered:
- Warm water is entering the underfloor pump system, the the pump turned on.
- Colder water is entering the system, the pump is turned off
- Warm water is entering the system. An override is set and the pump will not be turned on

### Saving energy

This system saves energy in two ways. Only when warm water is entering the pump system, the pump starts to run. Only in this case the warm water will enter the tubes in the floor and the heat is spread in the room. Cold water will stop the pump from running. Without an controller the system pumps cold water through the tubes for no reason. For example the whole summer. 

Secondly, the controller helps in routing the flow of warm water to selected rooms. Only rooms with a demand for heat should receive warm water. This is called a multi zone climate control system. The override on the controller helps with the routing. If there is no demand for the floor heating system and warm water is received, the controller does not start the pump. This prevents warm water entering the system and heating up the room.

### Anti corrosion
The controller contains some logic to prevent corrosion in the pump. A pump that is not running can become stuck if not run regulary. The controller takes care of this by running the pump automatically every night for a minute. 
### Building the controller
The controller is created with a modified Sonoff S20.

The S20 Wifi switch can be easily modified 
![alt text](https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/ui.png "lovelace example")
![](https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/s20.png)
![](https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/ds18b20.png)
