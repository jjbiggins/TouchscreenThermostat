# **Lab Report 3**

_Team Balanced – Thermostat_

Tamara Sakaji, Connor Eschrich, David Hausken, and Joe Biggins

The purpose of this lab was to design a user interface with the functionalities of a thermostat. The thermostat should display current temperature, time, set temperature, HVAC mode, HVAC status, and hold status. Additionally, the user should be able to configure the set temperature, time, and mode as well as implementing programmable set points. A good user interface design is the main focal point of the project. A design which includes all the functionality, but neglects a good user interface design can and will ruin the user experience. We accomplished this using an arduino, an Adafruit GFX touchscreen to show the UI, and a DS3231 to read and store temperature and time.

1.       **Final Test Report**

·       Does the main display have the following: current temperature, current set point, current day/time, HVAC mode, HVAC status, and hold status.

- Y/ **N** : Most are on the display, but hold status is not implemented due to there not being programmable set points to begin with.  Additionally, the current time is displayed, but not the day.

·       Does the Date/Time configuration have the following features: user can set date/time, date/time retained through power-down, time accuracy (RTC or other mechanism.)

- **Y**** /N**

Were programmable points implemented with the following features: up to four set-points for weekdays, program up to four set-points for weekends, user can enable/disable set points, set points retained through power-down, main screen hold function  overrides set-points.

- Y/ **N** : Programmable points were not implemented by the time of our demo.

Subjectively, was the UI intuitive, efficient, attractive, informative, resilient, and safe?

- **Y** /N: Based on the feedback of the professors, we believe the UI overall was good. The UI was easy to use, had a good use of colors, was clean, and it&#39;s simple; however, there could be some improvements to navigation.

As most of the testing was done through trial and error, it was difficult to have a discernible testing methodology. We did rely a lot on the serial monitor provided by the Arduino IDE, however, to test many values when we weren&#39;t getting desired results on the Adafruit.

2.   **Design documentation**

Software and Firmware Design:

Our software was designed to be object-oriented. For our group, it was difficult for us to initially visualize how to make this multi-page application on the touch screen in the Arduino language. Typically an application would be based off an M(odel)V(iew)C(ontroller) setup, but we did not have that functionality for Arduino, so we decided to look at the touchscreen as a Thermostat object in Arduino. We had two classes within the Thermostat, Temperature, and Date. These classes contained methods that were responsible for the setup of the screens which contained their information, along with getters and setters for each class variable.

We used several libraries to make our programming experience way easier. We used the Adafruit\_TouchScreen library to actually interact with the touchscreen and the the Adafruit-GFX library to insert shapes and colors onto the screen. The DS3231 library was used to retrieve and set the DS3231&#39;s time and temperature.

We decided to use tabs as our outline so we could make the UI as clean and easy-to-use as possible. We chose four tabs, initially they were Temperature, Mode, Status, DateTime. As we began programming, we decided to change them to Current, Set Temp, Mode, Set Time. This change occurred because we thought the main page would be more useful with the time, current temperature, and status so it would tell the user the information that they would need to see at a glance. The user then could navigate to another tab in order to change/set any other features of the thermostat. We didn&#39;t want the user to be able to accidentally tap the screen or change a mode without more than one step, so they didn&#39;t make any unwanted changes to their temperature, mode, or time. This is also why we included &#39;Clear&#39; and &#39;Set&#39; buttons for when they were changing the time, the day, or the set temperature. This made it so they would have to intentionally hit &#39;Set&#39; if they wanted to change anything.

Our setup() function declared our objects and set all of our initial values for variables. It set up all of our tabs and set the default tab to the &#39;Current&#39; page.

Our loop() function contained handled any events for the touchscreen, mainly the screen being touched. There were statements that would handle the changing of tabs, and would highlight the current tab and set the previous tab back to its default. It also clears the screen and loads the specified screen for the tab by calling a method in either the Temperature or Date class. Then we had statements that would handle the events depending on which tab was the current tab. These statements would detect events based on the area of the screen that was touched and if it was in the specified boundaries where a component was. ![](https://raw.githubusercontent.com/jjbiggins/touchscreen_thermostat/master/Pasted%20Graphic%202.png)

(i) Initial UI Storyboard Design

![](https://raw.githubusercontent.com/jjbiggins/touchscreen_thermostat/master/Scanned%20with%20CamScanner.png)

(ii) Object-Oriented Design

![](https://raw.githubusercontent.com/jjbiggins/touchscreen_thermostat/master/Pasted%20Graphic.png)

(iii) Screenshots from final product

Hardware Design-

Components used in circuit:

-Arduino Uno

-Adafruit touchscreen

-DS3231 RTC

-2x 10k Ohm resistors

-2x 220 Ohm resistors

-one blue LED

-one red LED

The circuit diagram is shown below:

![](https://raw.githubusercontent.com/jjbiggins/touchscreen_thermostat/master/Pasted%20Graphic%20copy.png)

The adafruit touchscreen was configured as a capacitive touchscreen in order to detect any fingers touching the screen.SPI mode was used which required 5 pins to be connected the arduino as shown in the circuit diagram, as well as the SDA and SCL lines. Originally, the touchscreen would stop working when we connected the SDA and SCL to both the touchscreen and the RTC, we tried different wiring schemes and ideas but nothing seemed to work. We eventually figured out that we needed a pullup resistor in order to get both the touchscreen and the RTC working simultaneously.

3.       **Final Report**

Upon diligent self-evaluation of Lab 3, our group drew upon numerous lessons that revealed themselves through the trying, laborious processes that coincided with the previous two labs. In our efforts to rectify, or, at the very least mitigate, the issues the arose in the previous two labs, we exhausted substantial time to develop a detailed plan for the design and implementation of our eventual product. In doing so, we sought to develop a through, yet flexible, plan that allowed for consistent, progressive building; while, simultaneously, maintain a firm grasp on the broader scope of the project. The result, was, more or less, an equal division of work while fostering a cohesive, cooperative team environment that produced an extremely rich and profitable intra-team relationship. Nonetheless, the technical aspect of this lab proved trying; our teams&#39; attempt to negate the aforementioned obstacles went as follows: from a hardware aspect, our team relied on Tamara&#39;s expertise almost exclusively. Being the solo &quot;hardware person&quot; on our team,  she constructed the entire circuit. Initially, we overlooked the clock and temperature entities; thus, Tamara constructed exceptional cicurtry, omitting our oversight. Concurrently, as Tamara was diligently working on her craft, Connor and David, with minor help from Joe, worked to seamlessly integrate the hardware with their software to produce an impeccable user interface. As we pondered the software production process, we developed a deep understanding of the abstract nature of the UI-touchscreen relationship. Under the leadership of Connor, we were able to develop simplistic, yet rich, GUI. While, in reflection of Professor Kuhl and Professor Mudumbai&#39;s assessment, we, as a group, came to terms with our errors in the interpretation of the assignments requirements. Engineering, at its essence, is producing a functioning, practical entity in accordance to given parameters, and, admittedly, we came up short in align our products functionality with the specified dictates. I digress. Once we acknowledged the need for temperature/clock functionality, we altered the circuit, adding two pullup resistor, to integrate our RTX component into the pre-existing circuitry. From there, we built out the remaining GUI feature, under our false pretenses, but completed them all the same. In conclusion, while this lab proved challenging, we gained valuable lesson the will prove applicable to our final project. Furthermore, we deepen our intra-team relationships, and now have an even clearer understand of our individual strengths and weaknesses. While the product we produced was largely degraded, we, through overcoming adversity, have a clearer understanding of the essential aspects that go into producing a truly amazing product.
