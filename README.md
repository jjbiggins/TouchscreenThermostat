# touchscreen_thermostat

The purpose of this lab was to design a user interface with the functionalities of a thermostat. The thermostat should display current temperature, time, set temperature, HVAC mode, HVAC status, and hold status. Additionally, the user should be able to configure the set temperature, time, and mode as well as implementing programmable set points. A good user interface design is the main focal point of the project. A design which includes all the functionality, but neglects a good user interface design can and will ruin the user experience. We accomplished this using an arduino, an Adafruit GFX touchscreen to show the UI, and a DS3231 to read and store temperature and time.
 
## 1. Final Test Report  
·       Does the main display have the following: current temperature, current set point, current day/time, HVAC mode, HVAC status, and hold status.
Y/N: Most are on the display, but hold status is not implemented due to there not being programmable set points to begin with.  Additionally, the current time is displayed, but not the day.

·       Does the Date/Time configuration have the following features: user can set date/time, date/time retained through power-down, time accuracy (RTC or other mechanism.)
Y/N 
 
	Were programmable points implemented with the following features: up to four set-points for weekdays, program up to four set-points for weekends, user can enable/disable set points, set points retained through power-down, main screen hold function  overrides set-points.
Y/N: Programmable points were not implemented by the time of our demo.

	Subjectively, was the UI intuitive, efficient, attractive, informative, resilient, and safe?
Y/N: Based on the feedback of the professors, we believe the UI overall was good. The UI was easy to use, had a good use of colors, was clean, and it’s simple; however, there could be some improvements to navigation.
 
	As most of the testing was done through trial and error, it was difficult to have a discernible testing methodology. We did rely a lot on the serial monitor provided by the Arduino IDE, however, to test many values when we weren’t getting desired results on the Adafruit. 
 
 
## 2. Design documentation  
Software and Firmware Design: 
