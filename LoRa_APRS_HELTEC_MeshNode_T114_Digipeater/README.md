# LoRa APRS Digipeater for HELTEC MeshNode T114

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________


## Instructions:

## 0) Prepare the Configuration info: you have to copy two strings into __Serial__ : (A) Digipeater Configuration and (B) LoRa Configuration. Prepare this two Strings before flashing the board.

A) On the first Reboot (as Digipeater won't find any configuration) you should enter the following:

callsign,digiMode,symbol,overlay,comment,latitude,longitude,sendBatteryTelemetry,beaconInternal,ultraEcoMode,wxSensorActive

example: AB1CDE-11,1,#,L,T114-Digipeater,0.0000000,0.0000000,Y,15,Y,N

- callsign              = replace with your Valid Ham Callsign (in UpperCase).
- digiMode              = 1 for repeating "WIDE1-1", 2 for "WIDE2-n"
- symbol                = # ("#" is recommended)
- overlay               = L ("L" is recommended)
- comment               = T114-Digipeater (don't use any *coma* in comment text)
- latitude              = in degrees and better to have 7 decimals
- longitude             = in degrees and better to have 7 decimals
- sendBatteryTelemetry  = Y ("Y" for yes, "N" for no)
- beaconInterval        = 15 (minutes)
- ultraEcoMode          = Y ("Y" for yes, "N" for no) (This makes the board sleep until LoRa Packet Rx using just 7mA at idle instead of 13.4mA)
- wxSensorActive        = N ("Y" for yes, "N" for no) (This enable BME280 Module and send Wx Telemetry Data: Temperature, Humidity, Pressure)

NOTE: if "wxSensorActive" is "Y" :
- Battery Voltage won't be sended in encoded Telemetry (as aprs-webpages wont process Battery encoded Telemetry in the same Wx Telemetry Packet.)

B) Prepare LoRa Configuration info:

Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power

example: 433.775,12,125.0,5,22

- Frequency       = your QRG for LoRa APRS as per your Country Settings.
- SpreadingFactor = 7 to 12 as per your Country Settings.
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4     = 5 to 7 as per your Country Settings.
- Power           = 22 (dBm) is max for SX1262 Module.


## 1) Press two times reset button to enter Virtual Disk Bootloader Mode: "HELTEC" or "HTxxx" external disc should appear in your PC/MAC/Linux Desktop.

## 2) Drag "firmware_HELTEC_MESHNODE_T114_digipeater.uf2" file into the folder/external disk "HELTEC" or "HTxxxx". It should reboot right away and you should get into any app that let you enter __Serial__ commands (Arduino IDE, VSCODE ...)

## 3) The initial setup will ask you to paste the string sentences created in __(A)__ first and then on another line __(B)__.

## 4) Follow the instructions on __Serial__ info to finish configuration.

## 5) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2025-08-11 Stable Version with improved Ultra EcoMode and Battery Monitor.
- 2025.05.12 First Beta Version for HELTEC MeshNode T114 Digipeater with Ultra EcoMode.

___________________________________________________

# Hope You Enjoy this, 73! CA2RXU, Valparaiso, Chile
