# Antenna Analyzer
This repository contains the detail to construct a VHF/UHF antenna analyzer instrument designed by VK5JST (Amateur Radio, May 2005). The design was converted to KiCad by TDARS.

# Overview
The analyzer has two connections; one from the radio transmitter (2W max, but you could use an attenuator), and one to the antenna. Note that the instrument also supports HF, but you'll still need to limit power to 2W max, or use an attenuator.

By using the rotary selector knob, it is possible to adjust the instrument to see full-scale deflection (FSD) on the built-in moving-coil meter movement, and then switch to SWR or R/Z to examine these values.

<img width="100%" align="left" src="images/overview-diag.jpg">

# One-Time Calibration
To calibrate the instrument one-time after building it, you just need a HF signal source of adjustable power. Do the following:

(1) Connect a low-power HF source to the RF input on the instrument, and ensure that nothing is attached to the antenna connector (to simulate a bad antenna)

(2) Set the selector knob to the Check Input position

(3) Slowly ramp up the input power until the meter scale reaches the center of the 'INPUT OK' section, which may occur at about 1W of transmitted power

(4) Set the selector knob to the Set FSD position, and then adjust the front panel potentiometer until the needle reaches the full scale position

(5) Set the selector knob to SWR, and adjust the trimmer resistor labeled TP1 to place the needle at the full scale position again

(6) Set the selector knob to R/Z and adjust the trimmer resistor labeled TP2 to place the needle again at the full scale position

(7) All is done!


