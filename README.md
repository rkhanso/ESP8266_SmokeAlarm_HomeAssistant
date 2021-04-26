# ESP8266_SmokeAlarm_HomeAssistant

I found this idea from Martin Ger at this webpage - https://www.esp8266.com/viewtopic.php?t=14315  and corresponding video on YouTube here - https://www.youtube.com/watch?v=7ZcnPoZn_O0

Following his directions, I quickly found that the Kidde Smoke Detector I have (Model i9040) does not have the same pinout as his example in the video.

I also had trouble with the Arduino sketch he linked at https://www.cs.hs-rm.de/~gergelei/SmokeDetector.ino with errors found when compiling. I'm an Arduino software novice, at best. So the trouble I had could certainly have been my lack of knowledge. But no matter what I tried, I could not get that sketch to work.

I started with a basic sketch copied from here - https://www.instructables.com/MQTT-Bare-Minimum-Sketch/   and customized (if you can call it that) to make it work for me.

Hopefully this will help you make your cheap, dumb smoke alarms smart and connect to your Home Assistant
