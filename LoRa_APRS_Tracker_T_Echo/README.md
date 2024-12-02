# LoRa_APRS_Tracker_T_Echo.

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________

(Afiliated Link for LILYGO T-ECHO modules)
[Aliexpress](https://s.click.aliexpress.com/e/_DmcgSyp) , [Lilygo](https://www.lilygo.cc/products/t-echo?bg_ref=M1lDRSwoKN)

____________________________________________________


## Instructions:

## 1) Prepare the Configuration info: you have to copy two strings into __Serial__ : (A) Tracker Configuration and (B) LoRa Configuration. Prepare this two Strings before flashing the board.

A) On the first Reboot (as Tracker won't find any configuration) you should enter the following:

callsign,pathType,symbol,overlay,comment,smartBeaconState,smartbeaconType,sendAltitude,sendBatteryTelemetry,bluetoothType

example: AB1CDE-7,1,[,/,T-ECHO-Tracker,Y,0,Y,Y,0


- callsign             = replace with your Valid Ham Callsign (in UpperCase).
- pathType             = 0 (for nothing) , 1 for "WIDE1-1", 2 for "WIDE1-1,WIDE2-1"
- symbol               = [ ("[" for Human/Runner, "b" for Bicycle, ">" for Car)
- overlay              = / ("/" is recommended)
- comment              = T-ECHO-Tracker (don't use any *coma* in comment text)
- smartBeaconState     = Y ("Y" for ON, "N" for OFF)
- smartbeaconType      = 0 (0 is slow speed station, 1 is mid, 2 is fast)
- sendAltitude         = Y ("Y" sends encoded Altitude, "N" sends encoded Speed + Course)
- sendBatteryTelemetry = Y ("Y" for yes, "N" for no)
- bluetoothType        = 0 (0 is OFF, 1 is BLE iPhone, 2 is BLE Android) ( SOON TO BE AVAILABLE! )

B) Prepare LoRa Configuration info:

Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power

example: 433.775,12,125.0,5,22

- Frequency       = your QRG for LoRa APRS as per your Country Settings
- SpreadingFactor = 7 to 12 as per your Country Settings
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4     = 5 to 7 as per your Country Settings
- Power           = 22 (dBm) is max for SX1262 in Rak 4631 Module


## 2) Press two times reset button to enter Virtual Disk Bootloader Mode: "TECHOBOOT" external disc should appear in your PC/MAC/Linux Desktop.

## 3) Drag "firmware_T_ECHO_tracker.uf2" file into the folder/external disk "TECHOBOOT". It should reboot right away and you should get into any app that let you enter __Serial__ commands (Arduino IDE, VSCODE ...)

## 4) The initial setup will ask you to paste the string sentences created in __(A)__ first and then on another line __(B)__.

## 5) Follow the instructions on __Serial__ info to finish configuration.

## 6) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2024.11.02 Beta Test Firmware.

___________________________________________________

# Hope You Enjoy this, 73! CA2RXU, Valparaiso, Chile