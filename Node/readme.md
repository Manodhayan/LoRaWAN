# Configure your LoRa Node
## Step 0: Download and extract this repository on your windows machine before proceeding.<br>

<img src="download.png" class="img-responsive" alt="download">
Extract the downloaded zip.For convinience, Extract the zip folder into desktop.

## Step 1: Setting up the environment
- Install [Arduino](https://www.arduino.cc/download_handler.php?f=/arduino-1.8.7-windows.exe)
- Open the download zip folder and navigate to LoRaWAN->libraries. Copy all files in this folder.
- Now, Open Documents->Arduino->libraries, paste the copied files into this folder.
<br><br>
Great Work!. Environment is ready to use.

## Step 2: Node Registration
- Follow this tutorial to register your node
https://www.thethingsnetwork.org/docs/devices/registration.html
.<br>Make sure you register in OTAA(Over the Air Activation) mode not as ABP (Active by Personalisation)

## Step 4: Entering your Credentials
You can find your credentials on Applications->Your Application<br>
![Credentials](navigate.png)

On Devices tab. Navigate into your device and find your credentials
![Credentials](credentials.png)
- Device EUI
<br>
Click on <> to get formatted HEX address and then click on double arrow so that the hex formatted arrange as LSB to MSB. Click on Clipborad icon to copy the address.
<br><br>Find this line of code 
    ```
    static const u1_t DEVEUI[8]  = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00 }; //Replace your DEVEUI -LSB->MSB
     ```
- Application EUI
<br>
Click on <> to get formatted HEX address and then click on double arrow so that the hex formatted arrange as LSB to MSB. Click on Clipborad icon to copy the address.
<br><br>Find this line of code 
    ```
    static const u1_t DEVEUI[8]  = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00 }; //Replace your DEVEUI -LSB->MSB
     ```
 