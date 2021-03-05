# signaljs
wbmra track+turnout+signal+abs_logic+ctc design and implementation

This s/w is being designed for a system that has a computer&display for every control panel. 
Assumed hardware is 
1) A Raspberry Pi4 and 7" touch panel used for each control panel
2) Pi4 and a HDMI or 4K monitor for the ctc display; keyboard and mouse for input
3) Uses the Pi's I2C to interface to standard boards which drive motors (Tortoises) and LEDS or get current readings (determine track occupancy)
4) All communication between computers uses Pi's built-in wifi and the MQTT protocol; one Pi4 is used as a router - no internet needed

The s/w will allow
design
1) interactive graphical design of track and control panels
2) interactive graphical picking of which track is mainline
3) interactive graphical picking of track where a switch throw affects adjacent switches
4) interactive graphical picking of which switches have signals (switches on mainline automatically have signals)
5) automatic generation of ctc display  
6) automatic determination of what state changes have to be communicationed between computers
wiring
7) interactive graphical clicking to set which i/o pin corresponds to which switch/LED/current detector
operation
8) operation, both with and without ctc

About 6): A CTC panel codes not need to know about yard switches.  And most CTC inputs only affect a single panel.

This project is being written in js and is heavily biased toward using functions which implement design rules and logic. 
User input to design or operate does not entail filling out forms.

To control i/o one has the choice
1) Johnny-5 to interface javaScript to hardware io
2) rewrite in Python, which on Pi's has native support for controlling io
.
The above design does not use the command stations, buses (Loconet) or software (JMRI) that are currently popular.
The control of locomotives may still be done by DCC.  JMRI may still be used to connect phone throttles.
Although this project is based on IOT technology, no consideration has been given to remote operation (yet?).
