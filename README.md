# SpotNik
StepTo / PushTo / Digital Setting Circles for EQ Mounted Telescopes Based on Arduino &amp; optional LX200 protocol

Since some time I have a nice 5'' telescope with EQ3 mount, which has a sufficient quality to view many deep sky objects - but the challenge is always to find these objects at all!!!

I have already tested everything possible, manual setting circles (doesn't work at all), finder scope, LED finder, TELRAD ... The TELRAD is by far the best, but with a lightpoluted sky it is difficult to find the reference stars for some objects ...

SpotNik - StepTo / PushTo / Digital Setting Circles for EQ Mounted Telescopes Based on Arduino

There are also many commercial and opensource GoTo and StepTo systems. But none really fitted for me - either too expensive, too complex, not suitable for EQ mount, not yet developed to the end ...

Since I didn't want to spend a lot of money and wanted to have a simple and robust system, I decided to build my own Stepto system with Arduino - named SpotNik as it should be cost-effective & reliable ...

The main requirements were

    StepTo / PushTo / Digital Settings Circles (DSC) system for EQ mount
    Low cost with minimal material and tooling
    Standalone system based on Arduino
    Optional Bluetooth connection with LX200 protocol to Sky Safari, Stellarium etc.

Most of all I was inspired by https://www.instructables.com/Arduino-Star-Finder... - many thanks for that!

#######################################################################################################################################################################
The Features of SpotNik

Main functions

    Step from a (hopefully) easy to find reference star to a selected target
    Practicable accuracy - theoretical resolution of ~ 12" - practical min. 0.5° (Telrad 0.5° - 2°; 6x30 finder scope 6°, 25mm / 650mm 2° field of view)
    Database with more than 1000 deep sky objects, including reference stars, nebulae, galaxies, star clusters, globular clusters, double stars and red stars
    Display of RA, DEC, name, type, constellation and magnitude of the object
    Filtering of objects by celestial regions and by constellations
    Switch view between current position & difference of RA / DEC to target
    Earth rotation is taken into account
    Test of sensors included
    Save settings for restart
    Optional Bluetooth connection with LX200 protocol to Sky Safari Plus (tested), Stellarium (not tested) etc.

HMI features

    Intuitive and easy control of HMI via rotary encoder
    LCD display with 16 x 2 characters
    Good readability by day and night due to fast change of LCD brightness & LCD contrast via software
    Display of object names including greek characters
    Software reset

Usage

    Low power consumption < 80mA at minimal LCD brightness (without bluetooth)
    Access to USB in housing
    Fast start-up < 3 sec

Build up / robustness

    System with minimal and standard parts
    Low hardware requirements
    Power supply in housing
    Simple electrical integration & easy replacement via 3.5mm cable
    Setup with home equipment such as drill, saw, hot glue (e.g. no 3D printer required)
    Parts from the hardware store whereever possib

######################################################################################################################################################################
What Previous Experience Do I Need?


    Previous experience with Arduino is useful but not necessary.
    You should have some experience with electronics to assemble and test the system.
    You should be able to solder and use a multimeter. (I have spent two hours looking for a fault during my build, which turned out to be a loose contact. The used jumper Wires were defective, so the sensor did not deliver a signal. Without a multimeter - no chance.)
    And then of course creativity and tinkering experience. Especially the topic of housing and mechanical integration took me some time and trial and error until everything was the way I wanted it.


######################################################################################################################################################################
Material

    1 x Arduino Uno R3 - 8€
    3 x Rotary Encoder KY-040 - 6€
    1 x LCD 1602 - 4€
    4 x GT2 pulley 20 teeth 5mm hole for 6mm belt - 4€
    2 x S2M timing belt 80 teeth 160mm closed - 2€
    Jumper wire cables (male / female 100mm & 200mm) - 3€
    1 x case 155 mm x 50 mm x 92 mm - 7€
    1 x power switch - 1€
    1 x battery holder 6 x AA - 2€
    1 x power cable with hollow plug 5,5/2,1mm 200m long - 2€
    4 x 3.5mm 4-pin jacks - 2€
    2 x 3.5mm 4-pin cables - 3€
    1 x female connector strip 2,54mm - 1€
    optional 1 x bluetooth module hc-05 - 7€
    optional 1 x 10kOhm, 1 x 20kOhm resistor

Additionally some things from the grab box or the hardware store about 10€.
Aluminum L-profile, cable ties, screws, PVC rigid foam, tubes, ... - maybe a longer screw for RA and/or DEC-axis

Total cost < 60€ including all stuff

######################################################################################################################################################################
Tools

You should get along by with a small workshop equipment. Depending on how you implement in particular the subject of housing and mounting the sensors it can be different.

I used the following tools:

    Soldering iron
    Drilling machine
    Files
    Saw
    Hot glue gun
    Screwdrivers
    Open-end wrench
    Pliers
    Folding rule
    Caliper gauge
    Hair dryer
    Computer with Arduino IDE

######################################################################################################################################################################
Installation in Case

Two things were important to me for the choice of the case - power supply (batteries) integrated and access to USB interface from the outside. Then I put the components together, estimated the necessary case size and looked for a cheap case based on that. Of cause other designs are possible - e.g. power supply with a power bank. Here I describe the assembly of my housing.

    LCD display
        Solder jumper wire cables (200mm) according to connection list (see Wiring Table)
        Saw out a hole for the display (first drill some holes and then filing to suitable size)
        Cut out frame from pvc hardfoam and glue on the LCD display with hot glue through the holes in the corners
        Fix the frame with hot glue in the case
    Battery compartment
        Cut out partition wall for battery compartment from pvc hardfoam
        Fix it vertically in the case with hot glue (while battery box in the case)
    Power button
        Drill hole for power button
        Solder the power button in the + lane of the power cable
        Solder - connection / + connection of cable to battery holder 
    HMI rotary encoder
        Drill hole for rotary encoder
        Connect female / male jumper wires (100mm) to it (see Wiring Table)
    3,5mm jacks
        Drill two holes
        Solder male jumper wires (100mm) to all four connections of 3,5mm jacks
        Install the jacks
    GND & 5V connectors
        Take two female connector strips with seven (for GND) and five (for 5V) connectors
        Solder the pins of each strip together
        Fix the connectors with hot glue to the case wall
    Holder for Arduino
        Cut out a plate from pvc hardfoam
        Fix it horizontally in the case with hot glue with some distance to the LCD display
        Plug in the power supply to the Arduino
        Put in the Arduino as close to the wall as possible
        Mark the end of the Arduino on the plate
        Cut out a plate from hardfoam
        Fix it vertically on the plate as end stop for the Arduino
    USB access for Arduino
        Put the Arduino in the case
        Mark the position of the USB jack
        Saw out a hole for USB plug
    Optional bluetooth module
        Attention - the RX connection must be connected with a voltage divider! e.g. 10kOhm in series between RX of the HC-05 and TX of the Arduino and 20kOhm between RX of the HC-05 and GND. Will also work with other resistors > 1kOhm - condition is that the second resistor has a value twice as high as the first one.Some details and picture in e.g.[http://archive.fabacademy.org/fabacademy2017/fablabbcn/students/91/week15.html] "*In fact arduino logic ports use 5V signals, while the bluetooth module uses 3.3V signals, so a voltage divider is needed on the TX(module)-RX(arduino), otherwise the board can be damaged. Here's diagram showing the connection."
        Take a femal connector strip with five connectors and plug it on the module
        Solder 20kOhm resistor between RX and GND of the connector strip
        Solder 10kOhm resistor between RX of connector strip and male jumper wire (100mm) and isolate it with heat shrink tubing or insulating tape
        Connect female / male jumper wires (100mm) to connector strip (see Wiring Table)
    Jumper wires
        Put in the Arduino
        Plug in the jumper wires as described in the Wiring Table

######################################################################################################################################################################
Wiring Table

Instead of a picture here the pin numbers of the parts and the Arduino.

LCD <-> Arduino

    VSS<->GND
    VDD<->5V
    V0<->11
    RS<->12
    RW<->GND
    E<->13
    D4<->9
    D5<->8
    D6<->7
    D7<->6
    A<->10
    K<->GND

HMI rotary encoder <-> Arduino

    GND<->GND
    +<->5V
    SW<->3
    DT<->4
    CLK<->5

RA rotary encoder <-> Arduino

    GND<->GND
    +<->5V
    DT<->A0
    CLK<->A1

DEC rotary encoder <-> Arduino

    GND<->GND
    +<->5V
    DT<->A2
    CLK<->A3

HC-05 <-> Arduino

    VCC<->2
    GND<->GND
    RX<->TX (Attention! - integrate resistor)
    TX<->RX

######################################################################################################################################################################
Install the Sensors - RA Axis

The mechanical integration of the sensors has the biggest effort for each telescope, because the mounts are different. My solution can therefore only be a (not perfect) suggestion. Another approach for a different eq mount is described here - https://www.observatorio-majadahonda.com/digital-setting-circles

The advantage of the RA axis is that the mount is already prepared for the installation of a motor. This makes the integration relatively easy.

Material for the RA axis

    PVC hardfoam 3mm x 70 mm x 70 mm
    Screw Allen M8 x 24mm
    3 x washers 8,4 mm x 24 mm
    2 x GT2 pulley 20 teeth (drilled out to ~6.2mm)
    KY-040
    3.5mm 4-pin jack

Bend the pvc hard foam using a hair dryer. Drill holes as shown in the picture. Put one washer above and two below the foam to get the right distance. Put the second pulley on the shaft of the telescope.

######################################################################################################################################################################
Install the Sensors - DEC Axis

The dec axis was much more complicated in my assembly because there was no axis free to mount a pulley. Therefore, I have rebuilt the slow motion cable that way it includes the pulley.

Material for the slow motion cable

    Tube - inner diameter 16-18mm (to fit on GT2 pulley), length 30mm
        1 x hole 5mm
        2 x hole 4,5mm 90° offset (for GT2 pulley) 
    Tube - outer diameter 13 - 15,5 mm (to fit in 1st tube) length 30mm
    1 x hole 4,5mm
    Screw for GD2 Allen M4 x 6mm
    Screw Allen M4 x 25mm
    Nut M4
    PVC tube 14mm (e.q. for aquarium)
    GT2 pulley 20 teeth

Material for the telescope

    Aluminium L profile 30 mm x 20 mm x 3 mm, length 60 mm
    Aluminium L profile 30 mm x 20 mm x 3 mm, length 66 mm
    Screw M6 x 15 mm
    Stop nut M6
    Screw M4 x 15 mm
    Nut M4
    GT2 pulley 20 teeth (drilled out to ~6.2mm)
    KY-040
    3.5mm 4-pin jack
    Wires

Look on the photos for the holes etc. You do not need the exact same material and also not the exact same dimensions. The nuts are pressed in the aluminium.

######################################################################################################################################################################
Upload the Sketch

If you have no previous experience with Arduino, it is best to look at a few websites on the net. Even if you don't have to program anything here, it is helpful. Here are the main steps.

    Install the Arduino IDE
    Connect Arduino via USB cable
    Put the Sketch in a folder with the same name and open it in Arduino IDE
    Select under Tools / Board / Arduino AVR / Arduino Leonardo
    Under Tools / Port select the port to which the Arduino is connected
    Under Sketch / Upload upload the sketch

######################################################################################################################################################################
General Control & Menu Structure of SpotNik

The HMI of SpotNik has a flat menu structure. All items are on the same layer. To change a menu entry you have to turn the rotary encoder. To select it you have to press the button. If you press it again you come back to the main menu (accept "Align" and "Target". Here the menu structure

- Longpress (> 5 seconds) of the button triggers a soft reset

(X) means pressing the button / (O) means turning the rotary encoder

Welcome Screen (X) or (O) -> Main Menu

Main Menu (O)

    DEC
        (X) show current DEC sensor direction
            (O) change DEC sensor direction
                (X) set DEC sensor direction & Main Menu

    Align
        (X) show currenct reference star
            (O) change of reference star
                (X) set reference star & display position, name, constellation of reference star = current position
                    (O) change display between difference / target / current position
                    (X) Main Menu
    Target
        (X) show current target
            (O) change of target object
                (X) set target object & display difference of current position and target position
                    (O) change display between difference / target / current position
                    (X) Main Menu
    Region
        (X) show current region filter
            (O) change of region filter
            (X) set region & Main Menu 
    Const
        (X) show current constellation filter
            (O) change constellation filter
            (X) set constellation filter & Main Menu 
    Brightness
        (X) show current LCD brightness
            (O) change LCD brightness
            (X) set LCD brightness & Main Menu 
    Contrast
        (X) show current LCD contrast
            (O) change LCD contrast
            (X) set LCD contrast & Main Menu 
    Sensors
        (X) wait for input of RA / DEC sensor & display number impulses
            (X) Main Menu
    BT Conn
        (X) show status of bluetooth connection
            (O) switch bluetooth on / off & display status of bluetooth & status of LX200 connection
            (X) Main Menu

######################################################################################################################################################################
Setup SpotNik

Before you can use SpotNik, you have to set up and test the system once. Once this is done, the values remain the same. Essentially, the rotary sensors need to be checked and the parameterization adjusted to the translation of the mount. It sounds probably complicated but it is not, if you do it step by step.

1st - Do the sensors provide any values at all?

First, we have to adjust the translation of the axes and the direction of rotation in the software.

    Connect the sensors RA / DEC to the SpotNik
    Select the menu item "Sensors".
    Turn the respective gear box, the displayed values should change.
    If nothing happens, check sensors, wiring, etc.
    If everything is ok, go to the next step.

2nd - Do the sensors provide the appropriate number of pulses?

Here we check if the sensors work properly and provide the pulses / per revolution specified in the datasheet.

    Rotate the RA and DEC axes with the gear box so that the sensor rotates one full revolution. With a 1:1 ratio between gear box and sensor, this is one revolution at the gear box. If a different gear ratio is used, we must account for this accordingly.
    Then SpotNik should show the values of pulses per revolution of the sensors. For the KY-040 this is 20 pulses.
    If the values do not fit, check again the electrics and mechanics of the sensors.

    If the values fit, go to the next step.

3rd - Setup of the RA / DEC axis

Here we determine the conversion values for the sensors and do the setup in the sketch.

RA axis

    Set the display of the sensors to zero by going out of the menu once and back again.
    Set the RA display to a full hour.
    Turn the gear box of the RA axis so that it rotates counterclockwise when viewed from above.
    Turn the RA axis by a sufficiently large hour angle to a full hour (6h hour angle is sufficient).
    Read the number of pulses of the sensor.
    If the value is negative, put the sign in front of the value of the DEC axis.
    Multiply the displayed value with the factor 24 / rotated hour angle to get the value for 24h.
    Enter the value in the sketch under #define IMPULSE24HRA. 

Example

    Rotation by 6h in counterclockwise direction
    693 pulses are displayed
    24h/6h = 4
    693 x 4 = 2772
    Enter value in Sketch --> #define IMPULSE24HRA 2772

DEC axis

    If the value of the DEC axis is not zero, set the display to zero by going out of the menu once and back again.
    Set the DEC display to a full 10°.
    Turn the gear box of the DEC axis so that it rotates counterclockwise when viewed from above.
    Rotate the DEC axis by a sufficiently large angle (90° is sufficient).
    Read the number of pulses of the sensor.
    If the value is negative, put the sign in front of the value of the DEC axis.
    Multiply the displayed value by the factor 360/angle of rotation to get the value for 360°.
    Enter the value in the sketch under #define IMPULSE360DEGDEC.

Example

    Rotation by 90° in counterclockwise direction -
    446 pulses are displayed
    360°/90° = 4
    -446 x 4 = -1784
    Value is negative
    Enter value in Sketch --> #define IMPULSE360DEGDEC -1784

--> Finally, re-upload the sketch.

Final - Does SpotNik provide the appropriate values in practical use?

Here we finally check if the setup is correct.

    Set up the telescope once and imagine you are pointing at a star.
    Select any star at reference and press.
    Then the current position is displayed.
    Rotate east on the RA axis - the displayed value should increase.
    If this is not the case, adjust #define IMPULSE24HRA.
    Rotate DEC axis towards zenith - the displayed value should increase.
    If this is not the case, adjust #define IMPULSE24HDEC.

Now SpotNik is ready for use!

######################################################################################################################################################################
Usage of SpotNik

Preparation

To begin, align the telescope correctly as described in the mount's instructions. If necessary, read the instructions for the mount on the Internet or in a book. (e.g. https://www.skyatnightmagazine.com/advice/equator...

The main topics are:

    Set latitude
    Align telescope level
    Point up RA axis to the north celestial pole

ATTENTION - If you rotate the tube 180° in right ascension

With a EQ mount, it may be necessary to rotate the tube 180° in right ascension, depending on the celestial direction to avoid that the tube collieds with the mounting.

    In this case, the rotation of the DEC sensor reverses.
    To compensate this, change the value in the menu item "DEC" to "reverse". By this SpotNik internally multiplies the IMPULSE24HDEC by -1.
    If you turn the telescope back to the normal orientation, set the value under "DEC" rotation back to "normal".
    I put a sticker on the DEC achse mount to remind me. For this, the telescope must always be mounted in the same direction, e.g. always with the sticker on the right side, when the telescope is aligned to the north at the beginning.

Align to reference star

    Change to the menu item "Align" and select a reference star. The star should be close to the desired target object to keep the travel distance small and accuracy high.
    Align the telescope to this star. Until a reference star has been aimed at, the clamps of the axes can be loosened to adjust the telescope quickly. Then clamp the axes and do not loosen them until a new reference star has been aligned.
    Again - thighten the axes really strong!!! This is error source number one!
    Press the button - now the position of the star is shown in the display and after a short time the RA display starts to change - the earth rotation is taken into account. Every time to go back to the menu item "Align" and select a star the position is reset again.

Select a target

    If no target has been selected yet, press the button and change to the menu item "Target" and select an object there.
    After pressing the button once, the coordinates of the object will be displayed.
    After pressing again, the difference that the telescope is to be moved is displayed.
    Now turn the worm drives until RA and DEC are approximately zero. Now the object should be visible in the eyepiece.
    It can be helpful to turn past the target and back again to compensate for backlash in the gearbox.

Filter objects by celestial area / constellation

To select the desired object from over 1,000 quicker, you can filter by celestial region and/or constellation. These celestial regions are taken from the book "Deep Sky Travel Guide" by Ronald Stoyan.

    To filter by sky area, switch to the menu item "Area".
    Select from the areas North, Winter, Spring, Summer, Autumn.
    Now only reference stars, objects and constellations from these areas are displayed.
    If you want to restrict the display even more, you can select a constellation under the menu item "Const".
    Now only the objects of this constellation are displayed, the reference stars are not affected.

Switching between Digital Setting Circles and StepTo

When the reference star or the target is displayed, the view can be changed by turning the rotary encoder. Turning the rotary encoder switches between the current position (Digital Setting Circles) and the difference to the target coordinate (StepTo).

LCD settings

The brightness and contrast of the LCD display can be adjusted. To do this, switch to the "Brightness" or "Contrast" menu items and change the settings there.

######################################################################################################################################################################
SpotNik & Sky Safari

First of all - SpotNik has only been tested with Sky Safari Plus on an Android phone.

    Install Sky Safari Plus on your cell phone.
    Integrate HC-05 bluetooth module into SpotNik.
    Turn on the Bluetooth connection between the cell phone and SpotNik.
    Pair cell phone and SpotNik (HC-05 with key "1234")
    Open Sky Safari Plus
    Under Settings / Scope / Setup select "Meade LX200 Classic", "Equatorial GoTo" or "Equatorial PushTo" and "Connect via bluetooth".
    Click on telescope in the main screen - press button "connect" - wait for the connection to be established (this may take a minute)
    Then you can select a reference star in SpotNik and the Sky Safari should align to this position.
    If you have selected a GoTo telescope you can also select targets in Sky Safari and send them via "GoTo" to Spotnik.
    If you are in the menu item "Align" or in the display "Curr" the reference position will be adjusted to the coordinates.
    In all other cases the target position will be adjusted.
######################################################################################################################################################################
Considerations & Background

What do have to do to find a DSO object easily?
Take a known star and move relatively (!) to it by difference of RA and DEC. Therefore you don't need kown the real time or siderean time, position or whatever. All you need to do is to aligne your telescope with a known star and move from there!

What do I need additionally?
To find the reference stars for alignment you need a good starmap. And something to find the reference star easliy. I prefer TELRAD respective Omegon Radiant as it is very fast and accurate. As alternative you can use Sky Safari Plus or Stellarium.

Is it possible to use low cost rotation encoders?
Many solutions use expensive optical rotary encoders 20-40€ each mainly because of the resolution. If you attach the rotary encoder to the worm gear box of an EQ, you can achieve also a high resolution. KY-040 is a mechanical rotary encoder which has 20 pulses / revolution. Typical gear boxes have 1:88 - 1:144 ratio. Mostly the DEC axis has a lower ratio than the RA axis and therefore has the lower resolution.

This leads to 20 * 88 = respectively 20 * 144 = 2780 pulses / 360°. This means a resolution of 0,12° - 0,2° plus a backlash in the worm gear. The other components have a field of view between 0,5° and 2° (TELRAD 0,5° - 2°; 6x30 finder scope 6°, 25mm / 650mm with 50° Plössl ocular - 2°)

Compared to the field of view of other components this should be sufficient to find the desired object.

How to achieve a robust read-out of the rotary encoders?

A robust readout of the encoders is the core of the whole function. For this I had to experiment a bit and finally found a very robust setup. Main points are the usage of the internal pullup resistors (therefore the usage of KY-040 is mandatory) and a stable software debouncing, where I used a solution from [https://www.best-microcontroller-projects.com/rotary-encoder.html] - thanks!

Longterm usage of the encoders?

As the KY-040 is a mechanical encoder the question is, how long will it last? From the datasheet of the included encoder it should last about 100,000 circles ((by the way, what does that mean? 360° rotation or pulses?) If you assume that this means pulses, let's calculate - 15 objects per night to move for each 15° --> 2780 Impulses / 360 * 15° *15 = 115 = 1737 Impulses / night. 100,000 / 1737 --> 57 nights. So one KY-040 should be enough for 57 around the price of 2€.

Why an Arduino UNO R3?

I started the project with an Arduino Mega 2560 and had it nearly finished. Then however - after a breakdown of the Arduino (the ugly "stk500v2_ReceiveMessage(): timeout avrdude" problem, which seems to be a hardware problem with cheaper copies of the Mega) I switched to a Leonardo I had lying around and started switching almost all data to PROGMEM, which was pretty simple. Then I kept for a while because it's small, reliable, affordable and a very common Arduino. At the end of the project I switched to the UNO R3. Its big advantage is the bigger Flash (~+3.5kB) as I ran out of memory when I integrated the bluetooth interface. The disadvantage is that it has only on serial port - which I used for the bluetooth connection as I had not enough free ports. So debugging when connected to a LX200 source is not possible. As alternatives you could a) use a I2C LCD and use the softserial b) use a Arduino Mega c) reduce the number of deep sky objects d) reduce some smaller functions like LCD brightness and contrast.

Why HMI control with rotary encoder?

Other solutions use buttons or touch displays. For two reasons I decided to use a rotary encoder. First - as I ordered 5 pieces of KY-040, there were three left. So I used one of them to operate the HMI. Second - this makes the system it very easy to use. You don't have to search for buttons in the dark and you can "spin" through the list of stars and DSO objects very fast. No wonder that e.g. in cars rotary encoders are often used as input device.

How fit over 1000 deep sky objects in the memory?

The lack of memory was one of the hardest parts. As I needed to keep the database of stars in the memory of the Arduino (no SD card) I had to think how this would fit in this small "space".

First of all, the classical hints for the reduction of memory requirements were considered. Here again some in short.

    Use data type with smallest memory requirement e.g. byte for numbers from 0-255
    Avoid strings where possible
    Use Const
    Use "F" macro for print statements
    Use PROGMEM instead of SRAM

With more than 1000 objects and the information I wanted save for each object (name, RA, DEC, constellation, type, magnitude) there are easily more than 12kByte just for the objects. Plus the sketch itself and information about constellations and areas. The SRAM would never have been enough for this, so as many objects as possible had to be stored in the flash via PROGMEM. Once you have used this it is not harder than accessing an array. But also the flash memory of the Arduino Leonardo is not very large, de facto only 28672 bytes of the 32kByte are available... (UNO has 3.5 kByte more and Mega even more). During programming I came again and again to the edge of the flash memory and therefore had to optimize again and again. So almost all libraries were removed, the deep sky objects were coded to be able to use as small data types as possible. For example, the names are coded by ID in an extra lookup table, because this reduces the number of names to be stored from about 1,100 to ~200. The magnitude and type are encoded in one byte - again saving of1100 bytes. The objects of the southern starry sky unfortunately had to be removed, because otherwise again the memory would not have been sufficient.

Why a LCD 1602?
I use a standard LCD 1602 display (in blue - red would be better - but I didn't had one). Why? Because it came with the Arduino set and is completely sufficient for this task. I connected it in serial mode. Why? First there was a problem with the Rotary Encoder in I2C mode, but in a different setup (still with interrupts). I left it like this, maybe the software works also with an I2C display. On the other hand you can adjust the contrast in the serial mode via software what I find advantageous, as it is comfortable as you don't have to open the housing.

How to show special characters on the LCD1602?

In order to display the names of all stars correctly, you must be able to display Greek letters. Unfortunately, the LCD1602 has only a small part of the Greek letters. Moreover, you can't simply store them in a string. So I coded the Greek letters into western ones and rebuilt the missing ones as custom characters. So it was still possible to use the cheap LCD1602.

Does it matter to which pins I connect?

For most connections it doesn't matter which pin of the Arduino you use. Exceptions are the pin for contrast and the brightness of the LCD, SW of the rotary encoder and the bluetooth interface.

For the LCD contrast you need a high frequency PWM to avoid flickering (Leonardo,Micro,Yún 3 and 11: 980 Hz // Mega pins 4 and 13: 980 Hz). For the brightness you need a PWM pin.

For the button of the rotary encoder an interupt capable pin should be used. Digital pins for interrupts on Micro,Leonardo and other 32u4 based are 0,1,2,3,7.

The rotary sensors for RA and DEC are connected to analog pins. The reason for this is that the Leonardo does not have enough digital pins in the design. But this is not a problem. Just note that for the analog pins the pull up resistor of the KY-040 should be set as well as the internal pull up resistor. Otherwise SpotNik will show any values before the sensors are connected. But this is already implemented in the sketch.

For the bluetooth connection the Leonardo comes with a hardware serial interface (RX/TX). With other Arduinos like the UNO you may have to switch to a softserial. For this the code has to be adapted accordingly.

Why use audio cables?

You have to connect the Arduino to the sensors mounted to the telescope. For this some kind of wiring is necessary. This should be as robust as possible, cheap and easy to replace in case of damage (e.g. cable break). Therfore I choose standard audio cables. You have to (!) use 4 core cables, because the rotary encoders need 4 connections to the Arduino. The 4 poles are needed to connect DT, CLK, GND and 5V. 5V is needed to use the built-in pullup resistor. Otherwise the sensors will not work properly.

Why hardware serial for Bluetooth interface?
I tested the software serial and it did not work stable in the setup. Since in some forums acuh instabilities were reported I left it with the hardware serial. The only disadvantage is the limited debugging when the bluetooth interface is active. Then you have to be careful with the messages not to disturb the connection to the LX200 source.

Why no real time clock?
The build-in timer of the Arduino is accurate enough, so you don't need a real time clock. Arduinos with ceramic resonators (as the Leonardo) have an error of about ±0.5%. [https://forum.arduino.cc/t/how-accurate-is-millis/183407/2]. This means in one hour = 3,600 seconds * 0,005 = 18 seconds. This should be good enough compared to the needed resolution. Even more as I expect to re-align frequently.

Save settings
When you restart the system, you don't want to setup everything again. So each time you press the rotary encoder the current settings are saved to the EEprom and reloaded at startup. This includes the reference star, the target, the area, constellation LCD brightness & contrast.

######################################################################################################################################################################
Credits

Without a lot of research on the internet and the many hints and examples found there, i would never have been able to realize this project. Here is a list of sites that have inspired me and helped me to move forward.

Arduino tips

    eeprom https://elektro.turanis.de/html/prj138/index.html... -
    progmem https://www.arduino.cc/reference/de/language/vari...
    robust rotary encoder reading https://www.arduino.cc/reference/de/language/vari...
    integrated pull-ups of KY-040 https://www.arduino.cc/reference/de/language/vari...
    robust rotary encoder reading https://www.arduino.cc/reference/de/language/vari...
    interna of LCD 1602 https://www.arduino.cc/reference/de/language/vari...
    custom characters https://www.arduino.cc/reference/de/language/vari... // https://www.arduino.cc/reference/de/language/vari...
    bluetooth hc05 -http://archive.fabacademy.org/fabacademy2017/fabla...

Other DSC / step to / goto approaches

    Where it all began ... - nice approach for dobson - https://www.instructables.com/Arduino-Star-Finder... -
    Quite close to my approach (found it, when I was allready finished ...) https://www.observatorio-majadahonda.com/digital-...
    Some good hints on LX200 - https://www.amateurastrophotography.com/control-t...
    More hints on LX200 - https://peges.de/astro/steuerung/arduino/noMide/n...
    The most sophisticated I found - https://skyandtelescope.org/observing/stargazers-corner/rduinoscope-boiana-diy-go-to-unit/
    Example for connection to LX200 source https://sites.google.com/site/ardugoto/
    DOB with BT on LX200 https://stargazerslounge.com/topic/315928-dob-hook...
    Older overview on DSC (from 2000) http://www.bogan.ca/astro/telescopes/digtcrcl.htm...
    Raspberry Pi - iTelescope http://simonbox.info/index.php/astronomy
    https://create.arduino.cc/projecthub/3wheels/digi...
    Astroduino is a project for making hardware and software for controlling your telescope https://sourceforge.net/projects/astroduino/
    WiFi enabled Digital Setting Circles https://github.com/synfinatic/teensy-dsc
    Low accuracy DSC, usage of accelerometer and magnetometer sensors instead of optical encoders https://github.com/vlaate/vladsc
    Interesting (20 years old!) project on DSCs https://eksfiles.net/digital-setting-circles/
    DSC system is based on the Digital Setting Circles project by Dave Ek. https://sites.google.com/site/gigimysite/home/astro/dsc-ekbox
    Approach on DSC with USB connection http://www.asemonline.org/ek?tmpl=%2Fsystem%2Fapp%...

Deep Sky ObjectsAlthough there are a lot of lists of stars on the web I used these lists. Mainly because of high number of stars, including the constellations and sufficient RA / DEC resolution.

    The brightest stars https://calgary.rasc.ca/stellarmagnitudes.htm#sta...
    Double stars http://takitoshimi.starfree.jp/
    650 DSO http://www.deepskywatch.com/files/dso-guide/DSO-g...
    Areas Deep Sky Atlas / Reiseführer - popular German books on DSOs

Translation

    To turn my good German into not too bad English, I used deepl.com for many sections. Thanks for the possibility to use it for free! -> Translated with www.DeepL.com/Translator (free version) ...

######################################################################################################################################################################
What Else?

I hope this instructable helps you to build your own EQ StepTo system so that you can find your deep sky objects easier and faster!

Maybe it is not programmed and designed the best way - but I hope it is useful for you.

If you have any hints to improve the code & the design - feel free to contact me!

And if you don't use it you maybe get some ideas for your own projects.
Beside the main function I like most

    the stable rotary encoder
    the software base LCD setup
    the rotary encoder HMI
    the 3,5mm wiring

Other things are

    save data in PROGMEM
    save data in EEPROM
    Bluetooth & LX200 access
    special characters in LCD1602

Of course a project is never complete ... here some ideas for further development ...

    Adapt SW / HW to dobson mount (mainly calculation of AZ / ... & other rotary encoder and/or gearbox)
    Include a motor on the RA-axxis e.g. for astrophotography
    Include more LX200 sources (e.g. Stellarium)

######################################################################################################################################################################
