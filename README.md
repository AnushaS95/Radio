# Radio
Design a radio, using different buttons like scan on and scan off;
A miniature portable FM radio has three controls. An on/off switch turns the device on and off. Tuning is controlled by two buttons scan and reset which operate as follows. When the radio is turned on or reset is pressed, the radio is tuned to the top frequency of the FM band (108 MHz). When scan is pressed, the radio scans towards the bottom of the band (88 MHz). It stops scanning when it locks on to a station or it reaches the bottom (end). If the radio is currently tuned to a station and scan is pressed then it starts to scan from the frequency of that station towards the bottom. Similarly, when reset is pressed the receiver tunes to the top. Using the alphabet {on, off, scan, reset, lock, end}, model the FM radio as a java program.
I have also designed the FSP for the above: 
RADIO = OFF, 
OFF= (on -> TOPFREQ),
TOPFREQ = (scan-> SEARCHING | reset-> TOPFREQ  | off -> OFF),
SEARCHING = (scan-> SEARCHING | reset -> TOPFREQ | off -> OFF | lock -> TUNED | end -> BOTTOMFREQ),
TUNED = (scan-> SEARCHING | reset -> TOPFREQ | off ->OFF ),
BOTTOMFREQ = (scan-> BOTTOMFREQ | reset -> TOPFREQ | off -> OFF).
//intitially the radio is off, we can only perform one action ie.
“ON” to turn it on,After ON is performed, 
we can “scan” for more channels or turn it “off” or “reset” it.
If we turn it “off”, we can only turn it back “on”.
If we scan it we can “scan” again or “Reset” it or turn it “off” or “lock” the channel or “end”From “reset”, 
we can turn it “off” or “scan” or “reset” again.
If we lock it, we can “scan” again, “reset” it or turn it “off” and can be done if we “end” it  .
