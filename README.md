# DripWatering
Drip Watering System based on the Arduino Uno Rev 4 with Capacitive Sensors and 12v Relays

The system uses pins A0 to A5 for the analog capacitive soil moisture sensors and pins D0 to D5 for the relays that control the water valves. I am using the 12V valves connected to the power supply in the box with a buck converter to power the Arduino.

When first turned on, or if it is not configure to connect to a wifi network it will start an AP with the SSID of Garden and a password of 123412341234. The IP address for the AP is 192.168.4.1, that is the default for the library so I left it. If it is configured for a wifi network it will try 3 times to connect then fall back to the AP.

There is a home page that shows the nickname you give the zone, the current moisture content, the valve status, a link to open/close the valve and the last time the valve was opened. This page will auto refresh every 10 seconds. There is also a link to the setup page. Only one valve can be open at a time, I did this because I was not sure of the draw for the valves and went with the safe approach.

On the setup page you can select Wifi Setup or Zone Setup. For the wifi setup, enter the SSID and password for your local area network, along with the IP address you want to assign to the device, with the subnet mask, default gateway and DNS. There is a place to enter your timezone offset in hours. Don't forget to change that when we switch between Day Light Savings and Standard Times. When you save this page the information is saved to the Non-Volatile Storage so it is available after a power cycle, and the device reboots.

The Zone Setup page lets you add zones, up to 6, and assign their values. Zones have a nickname that shows on the home page, a wet and dry reading that is specific to the sensor applied, a minimum moisture content in percent for when to open the valve, a watering time for when the valve is opened either automatically or through the Home Page. Zones can be disable or enabled through the switch on this page. If they are disabled they will report the moisture content but not open the valve.
The Wet and Dry setting have a link to report the sensor values so you can put the sensor in wet soil, run the test and get the value on the form. Then run the test for dry with the sensor in dry soil. Saving the settings will write the information to the NVS and reboot the device.



