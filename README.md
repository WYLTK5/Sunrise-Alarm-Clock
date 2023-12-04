# Sunrise-Alarm-Clock
An Alarm clock setup to turn on a set of LED's to act as a sunrise. Includes an LCD screen output and 2 other modes (Readings and Sunset)


Made this program and hardware setup to create a custom Sunrise Alarm Clock. This program pin setup is using an Arduino Mega 2560 for now but will be switching to a Arduino Leaonardo to free up my Mega 2560. Used a DS1307 RTC (Real Time Clock), LCD screen(16,2) with a RGB background lighting, 2 buttons, one rotary encoder with button integrated, 1 RGBW with the warm white, 1 TIP 220 transistor for the LCD brightness/colormixing(could use 3 to change the color through the program but the blue/red combo looks good), and a 12V 2A power supply.

The DS1307 RTC library I used was DS1307RTC.h by PaulStoffregen and contributors (https://github.com/PaulStoffregen/DS1307RTC). The Encoder library I used was BasicEncoder.h by Peter Harrison (https://github.com/micromouseonline/BasicEncoder/tree/main). The LCD library used was LiquidCrystal.h by Hans-Christoph Steiner and contributors (https://github.com/arduino-libraries/LiquidCrystal/tree/master). 

The project is somewhat of a work in progress with the odd functionality annoyance but as it sits each operation works as intended there is just some additional controls that I am slowly adding. 

There are 3 button inputs.
- The Reading button that turns on "ReadingMode" which controls the red, blue, and warm white lights.
- Sunset button that activates "SunsetMode" that turns off the blue light from ReadingMode if it is active and leaves only the red and white lights on.
      - Both these functions can be used to fade the lights on and off except when switching between reading mode and sunet mode the blue light gets turned off with no fading.
- The encoder button is used for the Alarm control and changing the "AlarmStateCount". One push *Count 1* allows you to change the "AlarmHour". Second push *Count 2* is to change the "AlarmMinute". Third push *Count 3* sets the Alarm and takes 10 minutes off the "AlarmHour/AlarmMinute" so the "Sunrise" starts 10 minutes before the set time and changes to *count 4*. *Count 5* gets activated when the tm.Hour and tm.Minute match the "AlarmStartHour" and "AlarmStartMinute", This activates the sunrise Effect. Once in the "SunriseMode" Pushing the encoder button changes to *Count 6* which fades the lights back down allowing time to gather clothes before the lights go off. Once the lights are fade off the Count gets set back to *Count 0*. Using the "Reading/Sunset" buttons will also turn the alarm off and switch to their lighting functions.

I have some improvements in mind and in the works but as it sits I am happy with how this has turned out so far for an early project in my programming journey. If you would like, let me know what you think and please share your thoughts.

Cheers, Ryan
