# robocar-dashboard
Robocar Rally Dashboard website


This is a dashboard I used at a recent Robocar Rally event. It displays live camera feeds from Raspberry Pi powered "Donkey Cars" (http://www.donkeycar.com/) as well as a lap time table in an iframe. 

This can be hosted in a web server (on the same network as the cars) or simply opened up locally in a browser. I just opened the html file locally in a browser on another Raspberry Pi hooked up to a large TV display near the track. Works best on a 1920x1080 display in fullscreen mode. The page is set to auto-refresh itself every 60 seconds, and displays an "Off Air" graphic (also included in this repo) for any cars not currently broadcasting. Replace IP addresses in each "loadImage" function call with the IP address of each team's donkey car.

If you are controlling your donkey car directly from it's web server, it will broadcast it's live camera feed without any modifications to the ~/d2/manage.py script. If, however, you are driving your donkey car from a joystick (with the manage.py drive --js flag), the web server is not started and the camera feed is not available. However, with a few modifications to manage.py, you can get the web server to start up, broadcasting it's live video feed, while still being able to drive the donkey car from a joystick, like a PS3 controller.

I have included my modified version of manage.py in this repo in case you would like to use it how I did. Please note that this modification doesn't seem to play nice with the regular web server driving mode (manage.py drive [without --js]), so you might want to keep two copies of manage.py if you switch back and forth a lot. Any pull requests on methods to avoid this issue are welcome!
