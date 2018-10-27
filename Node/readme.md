# Configure your LoRa Node
Note: Download and extract this repository on your windows machine before proceeding.<br>
![Credentials](download.png)
For convinience
## Step 1: Node Registration
- Follow this tutorial to register your node
https://www.thethingsnetwork.org/docs/devices/registration.html
<br>Make sure your device in OTAA mode not as ABP

## Step 2: Setting up the environment
- Install [Arduino](https://www.arduino.cc/download_handler.php?f=/arduino-1.8.7-windows.exe)
- On you system, Navigate to LocalD 
## Step 3: Entering your Credentials
You can find your credentials on Applications->Your Application<br>
![Credentials](navigate.png)

On Devices tab. Navigate into your node and find your below shown credentials
![Credentials](credentials.png)
- Device EUI
 ```
 static const u1_t DEVEUI[8]  = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,  0x00 }; //Replace your DEVEUI -LSB->MSB
 ```
 