# LoRa APRS Digirepeater for @RAKWireless WisBlock 4631

## You can support this project to continue to grow:

[<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/github-sponsors.png">](https://github.com/sponsors/richonguzman)     [<img src="https://github.com/richonguzman/LoRa_APRS_Tracker/blob/main/images/paypalme.png">](http://paypal.me/richonguzman)


____________________________________________________

(Afiliated Link for _RAK Wireless modules_)
- WisBlock Base (RAK19007)
- Nordic NRF52840 Module (RAK4631 (arduino))
- U-blox ZOE-M8Q (RAK12500


use this [link](https://url887.kickbooster.me/ls/click?upn=u001.rQqRChuldMyo9N3mcAI-2Bf2HF4aYB25xf7FmEbkTD-2BJPmW97aq6-2B-2FsJ-2Bmlj5qFSiRdEpe_HprRZeuCAf4z5NFKRFYVqVTXOS-2BXsX0r3A0LUEEvoKoVT4iXCw6WQzI4ENLL8PaHnA5P-2FfDxuqrI3BcZFumGrXLnv2loo9gjcgIq9nFjxNVnpvRELoEngdGoZ2c6LLp9d5dG2XTKk392BOczHQ4-2FI0zKhFh-2Bb0WE4jPKmIqiFNgFcgzMUX7xZbXw0clvgX1O73KOkJ8DxmsiqLmjWPqedJyfiYfDYsb-2Bcnj6SBY-2FQluqo3JG-2BszK7JDHe-2BUxc-2FjfIDyALruYuOxxrU0z4dO0-2Fw-3D-3D) and use this code for a % discount: **NGEQHU**

____________________________________________________


Instructions:

1) You have to copy two strings with (A) Station Configuration and (B) LoRa Configuration:

A) prepare Station Configuration info (As the initial configuration wont find any station_conf file with the configuration you should enter the following one):

"CALLSIGN,digiMode,symbol,overlay,comment,latitude,longitude,sendBatteryTelemetry,beaconInternal"

example: "AB1CDE-11,1,#,L,LoRa RAK4630 Test,0.0000000,0.0000000,Y,15"

- CALLSIGN = Replace with your Valid Ham Callsign
- digiMode = 1 for WIDE1-1, 2 for WIDE2-1
- symbol = #
- overlay = L
- comment = LoRa RAK4630 Test (donde use coma in comment)
- latitude = in degrees and better to have 7 decimals
- longitude = in degrees and better to have 7 decimals
- sendBatteryTelemetry = Y for yes, N for no.
- beaconInterval = 15 (minutes)

B) prepare LoRa Configuration info

"Frequency,SpreadingFactor,SignalBandwidth,CodingRate4,Power"

example: "433.775,12,125.0,5,22"

- Frequency = your QRG for LoRa APRS as per your Country Settings
- SpreadingFactor = 7 to 12 as per your Country Settings
- SignalBandwidth = 125.0 is stardard for all countries.
- CodingRate4 = 5 to 7 as per your Country Settings
- Power = 22 (dBm) is max for SX1262 in Rak 4630 Module



2) press two times reset button to enter Virtual Disk bootloader mode: RAK4630 or RAK4631 external disc should appear in your PC/MAC/Linux OS

3) drag "firmware.uf2" file into the folder/external disk. It should reboot right away and you should get into any app that let you enter serial commands (Arduino IDE, VSCODE ...)

4) The initial setup will ask you to paste the string sentences created in (A) first and then on another line (B).

5) After the sucess in writing configuration , the station will reboot and start right away.

   
if you want to delete previous configuration , drag "NRF52840_DeleteConfig.uf2" into the folder/virtual disk when boards is in boot loader mode.

- 2024.09.18 Battery Calculations Fix and full Configuration for Station and LoRa settings added.
- 2024.09.17 Battery Pins correction proposal
- 2024.09.15 Alpha
