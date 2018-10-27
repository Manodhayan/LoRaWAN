# The Things Network: RAK831-based gateway

Reference setup for [The Things Network](https://www.thethingsnetwork.org/) gateways based on

- Hardware: Raspberry Pi with [RAK831](http://www.rakwireless.com/en/WisKeyOSH/RAK831) concentrator connected through [adapter board](http://docs.rakwireless.com/en/LoRa/RAK831-Lora-Gateway/Application-Notes/Interface-Panel-Installation-Instructions.pdf).
- Software: Semtech [gateway driver](https://github.com/Lora-net/lora_gateway) and [packet forwarder](https://github.com/Lora-net/packet_forwarder)
- Configuration: [The Things Network Master Gateway Configurations](https://github.com/TheThingsNetwork/gateway-conf)

## Step 1: Setup based on Raspbian image

-Download [Raspbian Stretch Lite](https://www.raspberrypi.org/downloads/raspbian/)
- Follow the [installation instruction](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to create the SD card
- [Enable one-time SSH](https://www.raspberrypi.org/blog/a-security-update-for-raspbian-pixel/)
- Use `raspi-config` utility to

    ```
    sudo raspi-config
    ```

    - **Enable SPI** (`5 Interfacing Options -> P4 SPI`)
    - **Enable SSH** (`5 Interfacing Options -> P2 SSH`)
    - Set hostname (`2 Network Options -> N1 Hostname`) (Optional)
    - Change locale (`4 Localisation Options -> I1 Change Locale`) (Optional)
    - Change timezone (`4 Localisation Options -> I2 Change Timezone`) (Optional)

## Step 2: Set your Raspberry Pi up to date
- Make sure you have an updated installation and install `git`:

        sudo apt update
        sudo apt dist-upgrade
        sudo apt install git
## Step 3: Download Neccessary Files
- Clone the installer, if you haven't downloaded this repository before
    ```
        sudo git clone https://github.com/Manodhayan/LoRaWAN.git
    ```
## Step 4: Install Gateway

- Move to the directory and start the installation
    ```
        cd LoRaWAN/Gateway
        sudo chmod +x install.sh start.sh uninstall.sh
        sudo ./install.sh
    ```
Congratulations! Your gateway has been successfuly established.<br>
Note: Copy the Gateway ID displayed and use it during gateway registration

 
- Register gateway [via Semtech UDP packet forwarder](https://www.thethingsnetwork.org/docs/gateways/registration.html#via-semtech-udp-packet-forwarder)

    - Gateway's EUI can be found in `/opt/ttn-gateway/conf/local_conf.json`

## Step 5: Configure Gateway ID (If your Gateway ID is already registerd)

If your gateway ID already exits in Things Network. Then do the following to change your Gateway ID.<br>
- In Terminal
```
cd /opt/ttn-gateway/bin
sudo nano update_gwid.sh
```

Find GWID_MIDFIX variable and change it any other 4 digit hexadecimal number. You might end-up changing few more time as this repository is public<br>
- Example:
    - GWID_MIDFIX=FEFE<br>
    - Change this to something like GWID_MIDFIX=FFFF<br>

After making changes press Ctrl+X to exit nano editor. <br>It will ask you to save modified buffer, Press Y to save your changes.<br>
And File Name to Write, don't rename the file. Just press ENTER

<br><br>
That's it your gateway ID has been reconfigured.
Then,

```
cd
cd LoRaWAN/Gateway
sudo ./install.sh
```
Congratulations! Your gateway has been successfuly established with your own configured ID.

Note: Copy the Gateway ID displayed and use it during gateway registration

    
    

## Update 

If you have a running gateway and want to update, simply run the installer again:

    $ cd ~/rak831-gateway
    $ git pull
    $ sudo ./install.sh
