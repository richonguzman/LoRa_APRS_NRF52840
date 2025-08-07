# LoRa APRS Tracker for HELTEC MeshNode T114

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________

## Instructions:

## 0) Prepare the Configuration info: you have to copy two strings into __Serial__ : (A) Tracker Configuration and (B) LoRa Configuration. Prepare this two Strings before flashing the board.

A) On the first Reboot (as Tracker won't find any configuration) you should enter the following:

callsign,pathType,symbol,overlay,comment,smartBeaconActive,smartBeaconType,sendAltitude,sendBatteryTelemetry,bluetoothType

example: AB1CDE-7,1,[,/,MeshNode_T114_Tracker,Y,0,Y,Y,0

- callsign             = replace with your Valid Ham Callsign (in UpperCase).
- pathType             = 0 (for nothing) , 1 for "WIDE1-1", 2 for "WIDE1-1,WIDE2-1"
- symbol               = [ ("[" for Human/Runner, "b" for Bicycle, ">" for Car)
- overlay              = / ("/" is recommended)
- comment              = MeshNode_T114_Tracker (don't use any *coma* in comment text)
- smartBeaconActive    = Y ("Y" for ON, "N" for OFF)
- smartBeaconType      = 0 (0 is slow speed station, 1 is mid, 2 is fast)
- sendAltitude         = Y ("Y" sends encoded Altitude, "N" sends encoded Speed + Course)
- sendBatteryTelemetry = Y ("Y" for yes, "N" for no)
- bluetoothType        = 0 (0 is OFF, 1 is ON (for iPhone), 2 is ON (for Android)

B) Prepare LoRa Configuration info:

Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power

example: 433.775,12,125.0,5,22

- Frequency       = your QRG for LoRa APRS as per your Country Settings.
- SpreadingFactor = 7 to 12 as per your Country Settings.
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4     = 5 to 7 as per your Country Settings.
- Power           = 22 (dBm) is max for SX1262 Module.


## 1) Press two times reset button to enter Virtual Disk Bootloader Mode: "HELTEC" or "HTxxxx" external disc should appear in your PC/MAC/Linux Desktop.

## 2) Drag "firmware_HELTEC_MESHNODE_T114_tracker.uf2" file into the folder/external disk "HELTEC" or "HTxxxx". It should reboot right away and you should get into any app that let you enter __Serial__ commands (Arduino IDE, VSCODE ...)

## 3) The initial setup will ask you to paste the string sentences created in __(A)__ first and then on another line __(B)__.

## 4) Follow the instructions on __Serial__ info to finish configuration.

## 5) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2025.08.07 First Beta Version for HELTEC MeshNode T114 Tracker.

___________________________________________________

# Hope You Enjoy this, 73! CA2RXU, Valparaiso, Chile
