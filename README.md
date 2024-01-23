# heatercontrol_hassio
Smart Heating Optimization with Home Assistant


I aimed to enhance the efficiency of my home heating system. Initially, there was only a single traditional thermostat located centrally in the house. However, due to the house being two floors and half of the upstairs being open to the downstairs, the heater ran for extended periods. To address this, I integrated Home Assistant on a Raspberry Pi and, over four years, consistently worked on optimizing and expanding the system.

Now, with 12 Zigbee temperature sensors strategically placed throughout the house, I can monitor the average temperature. This average temperature guides my heating control. Although I set the initial setpoint within the generic thermostat, the slow heating process resulted in excess energy consumption.

To tackle this issue, I devised a script that functions as a controller. It initiates when the heater switch, which opens the valve for the radiators, is activated. The script records the operator-set setpoint and then introduces a 15-minute delay (subject to future evaluation). After this delay, the script decreases the initial setpoint by 1.5 degrees, causing the heater switch to turn off and the radiator valve to close.

Following this, there's a 20-minute delay. After this period, the script checks if the house's temperature is higher than the initial setpoint. If not, the script restarts the cycle. If the temperature surpasses the setpoint, the script concludes, allowing the heater to rest.

I anticipate that this approach will lead to energy savings. The 20-minute duration allows the radiators to continue warming the house even after the valve is closed. Ongoing assessment of the script's effectiveness will be carried out.
