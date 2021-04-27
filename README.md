# ESP8266_SmokeAlarm_HomeAssistant

I found this idea from Martin Ger at this webpage - https://www.esp8266.com/viewtopic.php?t=14315  and corresponding video on YouTube here - https://www.youtube.com/watch?v=7ZcnPoZn_O0

Following his directions, I quickly found that the Kidde Smoke Detector I have (Model i9040) does not have the same pinout as his example in the video.

I also had trouble with the Arduino sketch he linked at https://www.cs.hs-rm.de/~gergelei/SmokeDetector.ino with errors found when compiling. I'm an Arduino software novice on a good day. So the trouble I had could certainly have been my lack of knowledge. But no matter what I tried, I could not get that sketch to work.

So instead, I started with a basic sketch copied from here - https://www.instructables.com/MQTT-Bare-Minimum-Sketch/   and customized (if you can call it that) to make it work for me. See my esp8266_sketch in the list of files above.

Hopefully this will help you make your cheap, dumb smoke alarms smart and connect to your Home Assistant

Building is pretty straight-forward. Upload the sketch to the ESP8266 and add the sensor: section to your Home Assistant configuration.yaml file. Before you get too far, power up the ESP on its own and see if you get the state change in Home Assistant. Then you need to find which pins on your Smoke Alarm IC/processor is the Vss, Vdd, I/O. I've included a couple examples in the files above. Wire everything up as the schematic shows (based on which pins your IC in the smoke alarm uses). 

Surprisingly, one of the more difficult parts for me was to try to stuff everything into the smoke alarm without covering the vent areas of the smoke sensor. You may want to take extra time out and plan this a little more. You may have some little open areas around the back of the battery box/space that you can tuck the voltage regulator and the transistor/resistor/diode bundle. Be sure to not cover the the vents to the smoke sensor. Keeping the wires long enough may help you tuck some things out of the way so you can get the cover put back on the smoke detector.

There are some additional notes at the bottom of the Arduino Sketch page - showing that you need different MQTT "topics" to tell the difference between each smoke alarm (if you have multiples).

Also, don't forget to give each smoke alarm a different IP address in the Arduino Sketch. Duplicate IPs will give you headaches.


Files included:
ESP8266_Smoke_Alarm_MyUpdated_Schematic.jpg          -  the schematic I used in my Smoke Alarm
ESP8266_Smoke_Alarm_Original_Schematic.jpg           -  the schematic that Martin Ger shows on the YouTube video
ESP8266_smoke_detector_FinishedProduct.pdf           -  shows how I stuffed everything in the Smoke Alarm
ESP_Smoke Alarm Original Schematic from Youtube.jpg  -  the actual screenshot of Martin Ger's schematic
Electronics Parts I used for ESP8266 Smoke Alarm.txt -  where I bought some of my parts and the list of what I used
Home_Assistant_Configuration.yaml_code               -  what you need to add to Home Assistant configuration.yaml
README.md                                            -  this file
esp8266_sketch                                       -  the sketch I used to put on the ESP8266 (note: if you have multiple detectors, a line needs to be changed for each)
