# Underfloor heating pump controller (DIY)

A underfloor heating system distributes warm water through tubes to heat up a room. The system uses an electrical pump. In some of these systems the pump runs 24/7. This is not really necessary and wastes a lot of energy. Instead, it should only run when there is a demand for heating up the room. In other words, only when the boiler is delivering warm water and we want to heat up this particular room, the pump should run. The controller presented here, addresses the following scenario's:

- Warm water enters the underfloor heating circulation system. The pump is turned on.
- Colder water enters the underfloor heating circulation system. The pump is turned off
- Warm water enters the system. An override is set and the pump will not be turned on

The project uses [Home Assistant](https://www.home-assistant.io/) and the beautifully integrated [ESPHome](https://esphome.io/) system. The hardware exists of a slightly modified Sonoff S20 with a ds18b20 temperature sensor.

<table>
    <tr>
    <td align="left">
        <img src="images/ha.svg"
            alt="Home Assistant"
            href="https://www.home-assistant.io/"
            style="width: 60%"/>
     </td>
     <td align="left" width="70%">
        <img src="images/esphome.svg"
            alt="ESP Home"
            href="https://esphome.io/"
            style="width: 50%"/>
     </td>
     </tr>
</table>

## Saving energy

How much energy is wasted in case the pump is running 24/7? In my house, the pump is 60W. When running 24/7, it consumes 526 kWh a year. There is no demand for heat during summer, midweeks, midnights etc. Approximately 80% of a year the pump runs without a purpose. Wasted energy 421 kWh (100 Euro) a year. We have solar panels attached to the roof, generating 1000 kWh/year. The energy wasted is more than 40% of the generated energy!

This system saves energy in two ways. Only when warm water is entering the pump system, the pump starts to run. Only in this case the warm water will enter the tubes in the floor and the heat is spread in the room. Cold water will stop the pump from running.

Secondly, the controller helps in routing the flow of warm water to selected rooms. Only rooms with a demand for heat should receive warm water. This is called a multi zone climate control system. The override on the controller helps with the routing. If there is no demand for the floor heating system and warm water is received from the boiler, the controller will not start the pump.

## Corrosion prevention

When a pump is not running for a longer time, it may become stuck due to corrosion. The controller has some logic for this to run the pump every midnight for a minute.

## Building the controller

First of all a warning. This project involves opening up a Sonoff S20 Wifi switch and making some modifications. When plugged in the Sonoff is connected with live wires which can be very dangerous. Building and using the controller is at your own risk.

<img src="images/s20.png"
            alt="ESP Home"
            style="width: 30%"/>

The first step in the process is to prepare the S20 with ESPHome firmware. Please read [this detailed information](https://esphome.io/devices/sonoff_s20.html) how to flash ESPHome. The best is to solder a header on the main board. That helps in the next step.

We are now ready to add the DS18B20 sensor. The sensor will be connected to the header. More information on the ESPHome Dallas component can be found [here](https://esphome.io/components/sensor/dallas.html). It is very important to connect the resistor as described.

The S20 Wifi switch can be easily modified
![alt text](<https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/ui.png> "lovelace example")
![alt text](https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/s20.png "Sonoff S20")
![alt text](https://raw.githubusercontent.com/jeroenvdwaal/underfloor_heating_pump_controller/master/images/ds18b20.png "Temperature sensor")
