# LoRa APRS Tracker for @RAKWireless WisBlock 4631

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________

(Afiliated Link for _RAK Wireless modules_)
- WisBlock Base (RAK19007)
- Nordic NRF52840 Module (RAK4631 (arduino))
- U-blox ZOE-M8Q (RAK12500)


use this [link](https://url887.kickbooster.me/ls/click?upn=u001.rQqRChuldMyo9N3mcAI-2Bf2HF4aYB25xf7FmEbkTD-2BJPmW97aq6-2B-2FsJ-2Bmlj5qFSiRdEpe_HprRZeuCAf4z5NFKRFYVqVTXOS-2BXsX0r3A0LUEEvoKoVT4iXCw6WQzI4ENLL8PaHnA5P-2FfDxuqrI3BcZFumGrXLnv2loo9gjcgIq9nFjxNVnpvRELoEngdGoZ2c6LLp9d5dG2XTKk392BOczHQ4-2FI0zKhFh-2Bb0WE4jPKmIqiFNgFcgzMUX7xZbXw0clvgX1O73KOkJ8DxmsiqLmjWPqedJyfiYfDYsb-2Bcnj6SBY-2FQluqo3JG-2BszK7JDHe-2BUxc-2FjfIDyALruYuOxxrU0z4dO0-2Fw-3D-3D) and use this code for a % discount: **NGEQHU**

____________________________________________________


## Instructions:

## 0) Mount RAK4631 into RAK19007. Mount RAK12500 into RAK19007 (SLOT A).

## 1) Prepare the Configuration info: you have to copy two strings into __Serial__ : (A) Tracker Configuration and (B) LoRa Configuration. Prepare this two Strings before flashing the board.

A) On the first Reboot (as Tracker won't find any configuration) you should enter the following:

callsign,pathType,symbol,overlay,comment,smartBeaconState,smartbeaconType,sendAltitude,sendBatteryTelemetry,bluetoothType

example: AB1CDE-7,1,[,/,RAK4631-Tracker,Y,0,Y,Y,0


- callsign             = replace with your Valid Ham Callsign (in UpperCase).
- pathType             = 0 (for nothing) , 1 for "WIDE1-1", 2 for "WIDE1-1,WIDE2-1"
- symbol               = [ ("[" for Human/Runner, "b" for Bicycle, ">" for Car)
- overlay              = / ("/" is recommended)
- comment              = RAK4631-Tracker (don't use any *coma* in comment text)
- smartBeaconState     = Y ("Y" for ON, "N" for OFF)
- smartbeaconType      = 0 (0 is slow speed station, 1 is mid, 2 is fast)
- sendAltitude         = Y ("Y" sends encoded Altitude, "N" sends encoded Speed + Course)
- sendBatteryTelemetry = Y ("Y" for yes, "N" for no)
- bluetoothType        = 0 (0 is OFF, 1 is BLE iPhone, 2 is BLE Android)

B) Prepare LoRa Configuration info:

Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power

example: 433.775,12,125.0,5,22

- Frequency       = your QRG for LoRa APRS as per your Country Settings
- SpreadingFactor = 7 to 12 as per your Country Settings
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4     = 5 to 7 as per your Country Settings
- Power           = 22 (dBm) is max for SX1262 in Rak 4630 Module


## 2) Press two times reset button to enter Virtual Disk Bootloader Mode: "RAK4631" external disc should appear in your PC/MAC/Linux Desktop.

## 3) Drag "firmware_RAK4631_tracker.uf2" file into the folder/external disk "RAK4631". It should reboot right away and you should get into any app that let you enter __Serial__ commands (Arduino IDE, VSCODE ...)

## 4) The initial setup will ask you to paste the string sentences created in __(A)__ first and then on another line __(B)__.

## 5) Follow the instructions on __Serial__ info to finish configuration.

## 6) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2024.10.16 Beta Test Firmware.

___________________________________________________

# Hope You Enjoy this, 73! CA2RXU, Valparaiso, Chile