# Signal_Generator
 RF signal generator 1-30 Mhz with 120dB digital attenuator

<p>Components :  
<li>Nextion 5 inch display
<li>Arduino Nano
<li>MCP4725 i2c 11 bit DAC
<li>AD9850 DDS module
<li>35 Mhz low pass filter
<li>LM324 comparator opamp
<li>AD603 variable RF opamp driven by substractor opammp (6V reference - DAC output voltage)
<li>4 x HMC472 6 bit 31.5 dB digital attenuators driven by 4 x MCP23008 8bit GPIO extenders)
<br>

<strong><p>How it works</strong>
<li>Arduino nano is connected via TTL Software serial to Nextion HMI display. It also drives AD9850 DDS module
<li> Once frequency is set via touch display, Arduino is converting String data into integer to address the DDS, also via i2c is setting DAC value from callibration table for a steady -13dBm / 50 ohms output in all 1-30Mhz range.
<li>For best linearity, I opted for 4 calibration points per 1 Mhz span.
<li>This -13dBm is used as a S9+60dB refference where from the next 120dB divider comes into play.
<li>From Nextion display, I can select the desired S point signal level from S1 up to S9+60 simply by passing desired attenuation value to 4x6 bit compute function in order to address 4x6 bit dividers.


