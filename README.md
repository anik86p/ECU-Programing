# ECU-Programing-With-C-
<!DOCTYPE html>
<html>
<body>
<h3>ECU 00</h3>
<p>
 Sensor functionality:
 Gear sensor: Two buttons (BT5 and BT6) on this ECU should be used as gear sensors. One
button should indicate that the user shifted up. The other button is for down shifting. In
every case a signal including the gear should be sent to the bus. Note: Let’s assume a 6-gear
sequential manual transmission is used. At start up the gearbox is always in neutral (N). The
6-gear transmission should have the following gears: R – reverse, N – neutral, 1, 2, 3, 4, 5, 6.
One byte should be used to send the data. Every bit in this byte represents one gear. So the
reverse gear should be represented by ‘0b00000001’. The neutral gear is represented by
‘0b00000010’ and so on.
 Door sensors: Two switches should represent sensors included in the doors. One switch for
the left door and another switch for the right door. If the doors are opened, a logical ‘0’
should be written to the bus. A logical ‘1’ should signalize that the door is closed.
 ECU functionality:
 This ECU receives the fuel level and the engine coolant temperature. If the fuel level reaches
1/10th of the maximum a signal should be written to the bus. If the coolant temperature
reaches 9/10th of the maximum another warning signal written to the bus.
 Moreover, it must check if ECU1 – Light Control is present. If ECU1 is not present led “P”
should periodically blink. Additionally an error message must be sent..</p>

<h3>ECU 11</h3>
<p>
 Sensor functionality:
 RPM: The potentiometer of this ECU should be used to read the RPM value. This value must
be sent to the bus. Note: The value received by the potentiometer is 1/10th of the actual
RPM. So a value of 410 would be 4100 RPM.
 Light mode switch: A switch on this ECU should be used as mode switch. The mode switch
toggles between the manual and the automatic light mode on this ECU.
 ECU functionality:
 This ECU implements two modes. The first mode is the manual mode. In manual mode the
ECU receives 6 signals which represent different light states. Each state switches a light on or
off. A logical ‘0’ received means the light is switched on. A logical ‘1’ should switch off a light.
 In automatic mode the low beam and the parking light should be switched on automatically if
the light value falls below 512. Use the light sensor on board to read light intensity.
 Moreover, it must check if ECU2 – Door Control is present. If ECU2 is not present led “P”
should periodically blink. Additionally an error message must be sent.</p>
<h3>ECU 22</h3>
<p>
 Sensor functionality:
 Fuel level: The potentiometer is used to represent the fuel level of the car. It should be sent
to the bus.
 Indicator switches: 3 switches should be used to control the state of the indicators. There
should be a switch for the left and right indicator, and the last switch should be used for the
hazard light (left and right indicator at the same time). Note: To signalize that an indicator is
switched on a logical ‘0’ should be sent. If it is switched off a logical ‘1’ must be sent.
 ECU functionality:
 This ECU receives the speed of the car and the state of the doors. The state of the doors must
be sent to the bus. If the car moves faster than 5 km/h and a door is opened a warning signal
should be sent additionally.
 Moreover, it must check if ECU3 – Engine Control is present. If ECU3 is not present led “P”
should periodically blink. Additionally an error message must be sent.
</p>
<h3>ECU 33</h3>
<p>
 Sensor functionality:
 Engine coolant temperature: The potentiometer should be used to determine the engine
coolant temperature and must be sent to the bus.
 Headlight switches: 3 switches should be used as headlight switches. One switch is used as
high beam switch, another one as low beam switch, and the third one as switch for the
parking light. A logical ‘0’ sent means the corresponding light is switched on and a logical ‘1’
should be sent if the light is switched off.
 ECU functionality:
 This ECU should calculate the speed depending on gear and RPM. The speed value must be
sent to the bus. The speed can be calculated by the following formula:
𝑠𝑝𝑒𝑒𝑑 =
𝑔𝑒𝑎𝑟 𝑟𝑎𝑡𝑖𝑜 ∗ 𝑟𝑝𝑚
100000
The gear ratios can be found in the following table:
Gear R N 1 2 3 4 5 6
Value 7842 0 7842 13112 19861 27038 33149 40035
The speed should have a resolution of 10 bits and must be sent to the bus.
 Moreover it must check if ECU0 – Monitoring is present. If ECU0 is not present led “P” should
periodically blink. Additionally an error message must be sent.

</p>
  
</body>
</html>
