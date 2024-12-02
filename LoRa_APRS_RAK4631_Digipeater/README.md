# LoRa APRS Digipeater for @RAKWireless WisBlock 4631

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________

(Afiliated Link for _RAK Wireless modules_)
- WisBlock Base (RAK19007) or (RAK19003)
- Nordic NRF52840 Module (RAK4631 (arduino))
- BME680 Sensor (RAK1906)


use this [link](https://url887.kickbooster.me/ls/click?upn=u001.rQqRChuldMyo9N3mcAI-2Bf2HF4aYB25xf7FmEbkTD-2BJPmW97aq6-2B-2FsJ-2Bmlj5qFSiRdEpe_HprRZeuCAf4z5NFKRFYVqVTXOS-2BXsX0r3A0LUEEvoKoVT4iXCw6WQzI4ENLL8PaHnA5P-2FfDxuqrI3BcZFumGrXLnv2loo9gjcgIq9nFjxNVnpvRELoEngdGoZ2c6LLp9d5dG2XTKk392BOczHQ4-2FI0zKhFh-2Bb0WE4jPKmIqiFNgFcgzMUX7xZbXw0clvgX1O73KOkJ8DxmsiqLmjWPqedJyfiYfDYsb-2Bcnj6SBY-2FQluqo3JG-2BszK7JDHe-2BUxc-2FjfIDyALruYuOxxrU0z4dO0-2Fw-3D-3D) and use this code for a % discount: **NGEQHU**

____________________________________________________


## Instructions:

## 0) Mount RAK4631 into RAK19007 (or RAK19003).

## 0.1) (OPTIONAL) Mount BME680 Sensor into SLOT-C

## 1) Prepare the Configuration info: you have to copy two strings into __Serial__ : (A) Digipeater Configuration and (B) LoRa Configuration. Prepare this two Strings before flashing the board.

A) On the first Reboot (as Digipeater won't find any configuration) you should enter the following:

callsign,digiMode,symbol,overlay,comment,latitude,longitude,sendBatteryTelemetry,beaconInternal,ultraEcoMode

example: AB1CDE-11,1,#,L,RAK4631-Digipeater,0.0000000,0.0000000,Y,15,Y,N

- callsign              = replace with your Valid Ham Callsign (in UpperCase).
- digiMode              = 1 for repeating "WIDE1-1", 2 for "WIDE2-n"
- symbol                = # ("#" is recommended)
- overlay               = L ("L" is recommended)
- comment               = RAK4631-Digipeater (don't use any *coma* in comment text)
- latitude              = in degrees and better to have 7 decimals
- longitude             = in degrees and better to have 7 decimals
- sendBatteryTelemetry  = Y ("Y" for yes, "N" for no)
- beaconInterval        = 15 (minutes)
- ultraEcoMode          = Y ("Y" for yes, "N" for no) (This makes the board sleep until LoRa Packet Rx using just 7mA at idle instead of 13.4mA)
- wxSensorActive        = N ("Y" for yes, "N" for no) (This enable BME680 Module and send Wx Telemetry Data: Temperature, Humidity, Pressure)

NOTE: if "wxSensorActive" is "Y" :
- RAK Module won't enter into ultraEcoMode as the BME680 would need the board to stay awake.
- Battery Voltage won't be sended in encoded Telemetry (as aprs-webpages wont process Battery encoded Telemetry in the same Wx Telemetry Packet.)

B) Prepare LoRa Configuration info:

Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power

example: 433.775,12,125.0,5,22

- Frequency       = your QRG for LoRa APRS as per your Country Settings
- SpreadingFactor = 7 to 12 as per your Country Settings
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4     = 5 to 7 as per your Country Settings
- Power           = 22 (dBm) is max for SX1262 in Rak 4631 Module


## 2) Press two times reset button to enter Virtual Disk Bootloader Mode: "RAK4631" external disc should appear in your PC/MAC/Linux Desktop.

## 3) Drag "firmware_RAK4631_digipeater.uf2" file into the folder/external disk "RAK4631". It should reboot right away and you should get into any app that let you enter __Serial__ commands (Arduino IDE, VSCODE ...)

## 4) The initial setup will ask you to paste the string sentences created in __(A)__ first and then on another line __(B)__.

## 5) Follow the instructions on __Serial__ info to finish configuration.

## 6) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2024.11.02 Added RAK1906 BME680 Sensor support.
- 2024.10.24 Ultra EcoMode added (uses 7mA at idle waiting for LoRa Packet instead of 13.4mA when not sleeping).
- 2024.10.16 Code improved and minor bugs.
- 2024.09.18 Battery Calculations Fix and full Configuration for Station and LoRa settings added.
- 2024.09.17 Battery Pins correction proposal
- 2024.09.15 Beta Test Firmware.

___________________________________________________

# Hope You Enjoy this, 73! CA2RXU, Valparaiso, Chile