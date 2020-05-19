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

Our software was designed to be object-oriented. For our group, it was difficult for us to initially visualize how to make this multi-page application on the touch screen in the Arduino language. Typically an application would be based off an M(odel)V(iew)C(ontroller) setup, but we did not have that functionality for Arduino, so we decided to look at the touchscreen as a Thermostat object in Arduino. We had two classes within the Thermostat, Temperature, and Date. These classes contained methods that were responsible for the setup of the screens which contained their information, along with getters and setters for each class variable. 
We used several libraries to make our programming experience way easier. We used the Adafruit_TouchScreen library to actually interact with the touchscreen and the the Adafruit-GFX library to insert shapes and colors onto the screen. The DS3231 library was used to retrieve and set the DS3231’s time and temperature.
We decided to use tabs as our outline so we could make the UI as clean and easy-to-use as possible. We chose four tabs, initially they were Temperature, Mode, Status, DateTime. As we began programming, we decided to change them to Current, Set Temp, Mode, Set Time. This change occurred because we thought the main page would be more useful with the time, current temperature, and status so it would tell the user the information that they would need to see at a glance. The user then could navigate to another tab in order to change/set any other features of the thermostat. We didn’t want the user to be able to accidentally tap the screen or change a mode without more than one step, so they didn’t make any unwanted changes to their temperature, mode, or time. This is also why we included ‘Clear’ and ‘Set’ buttons for when they were changing the time, the day, or the set temperature. This made it so they would have to intentionally hit ‘Set’ if they wanted to change anything. 
Our setup() function declared our objects and set all of our initial values for variables. It set up all of our tabs and set the default tab to the ‘Current’ page.
