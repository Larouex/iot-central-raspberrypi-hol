# ![alt text](./Assets/azure_iot_central_super_sml.png "Getting to Know the Raspberry Pi") IoT Central Basic Bootcamp 
# Hands on Lab

![alt text](./Assets/Raspberry-Pi-4-hero-shot-removebg.png "Hero Shot")

# Overview
Welcome to the Azure IoT Central Basic Bootcamp and Hand On Lab. We will be settign up and end to end scenario using the Raspberry Pi as our IoT "Device" and connect all the way through to IoT Central to demostrate the power of Azure IoT Central Telemetry, Programming, Data Modeling and Data Export and Integration.

## Contents
- [IoT Central Basic Bootcamp](#iot-central-basic-bootcamp)
  - [Contents](#contents)
  - [Bill of Materials for IoT Central Bootcamp](#bill-of-materials-for-iot-central-bootcamp)
      - [Components](#components)
      - [Tools](#tools)
      - [Optional](#optional)
    - [Raspberry Pi Model 4 B](#raspberry-pi-model-4-b)
    - [AM2315 Temperature and Humidity Sensor](#am2315-temperature-and-humidity-sensor)
    - [Ultra Compact RS232 to TTL Converter with Female DB9](#ultra-compact-rs232-to-ttl-converter-with-female-db9)
    - [Screw Terminal Block Breakout Module for Raspberry Pi](#screw-terminal-block-breakout-module-for-raspberry-pi)
    - [SanDisk Ultra microSD Card](#sandisk-ultra-microsd-card)
    - [USB to RS232 Serial Cable with Prolific PL2303 Chip](#usb-to-rs232-serial-cable-with-prolific-pl2303-chip)
    - [RGB LED 10mm (Optional Status Indicator)](#rgb-led-10mm-optional-status-indicator)
  - [Assembling the Raspberry Pi and the Components](#assembling-the-raspberry-pi-and-the-components)
    - [Soldering the Connection to the TTL Converter](#soldering-the-connection-to-the-ttl-converter)
    - [Soldering and Wiring the LED](#soldering-and-wiring-the-led)
    - [Shrink Wrap the LED](#shrink-wrap-the-led)
    - [Attach the Sensors](#attach-the-sensors)
    - [Connections](#connections)
    - [Device Assembly Overview](#device-assembly-overview)
  - [Setting up your Raspberry Pi OS](#setting-up-your-raspberry-pi-os)
    - [Setting up Raspberry Pi Imager](#setting-up-raspberry-pi-imager)
    - [Enabling Options for Connectivity (NO DISPLAY OR KEYBOARD/MOUSE)](#enabling-options-for-connectivity-no-display-or-keyboardmouse)
      - [Enable ssh to allow remote login](#enable-ssh-to-allow-remote-login)
        - [Mac instructions (enable ssh)](#mac-instructions-enable-ssh)
        - [Windows instructions (ssh)](#windows-instructions-ssh)
      - [Add your WiFi network info](#add-your-wifi-network-info)
        - [Mac instructions (wifi settings)](#mac-instructions-wifi-settings)
        - [Windows instructions (wifi settings)](#windows-instructions-wifi-settings)
    - [Eject the Micro SD card](#eject-the-micro-sd-card)
    - [Install the Micro SD card in the Raspberry Pi](#install-the-micro-sd-card-in-the-raspberry-pi)
  - [Setting up the Development Toolchain for your Workstation](#setting-up-the-development-toolchain-for-your-workstation)
    - [Install Git](#install-git)
    - [Install Visual Studio Code](#install-visual-studio-code)
    - [Install Python](#install-python)
    - [Upgrading pip](#upgrading-pip)
    - [Install all the Tools for Visual Studio Code](#install-all-the-tools-for-visual-studio-code)
  - [Connecting to the the Raspberry Pi (SSH)](#connecting-to-the-the-raspberry-pi-ssh)
    - [Connecting the Pi with a Monitor, Keyboard and Mouse](#connecting-the-pi-with-a-monitor-keyboard-and-mouse)
    - [Connecting Headless (no display)](#connecting-headless-no-display)
    - [Connecting to the Raspberry Pi using SSH](#connecting-to-the-raspberry-pi-using-ssh)
  - [Modules](#modules)
    - [Module01](#module-01)
  

## Bill of Materials for IoT Central Bootcamp
The following are needed for this workshop...
#### Components
* One(1) Raspberry Pi Board (version 4) Canakit
* One(1) Breadboard Kit
* One(1) Network Cable
#### Optional
* Monitor or Raspberry Pi Touchscreen
* HDMI Mini to HDMI Standard Cable
* Keyboard
* Mouse
### Raspberry Pi Model 4 B
![alt text](./Assets/rpi-model-4-b-board.jpg "Raspberry Pi Model 4")

The speed and performance of the new Raspberry Pi 4 is a step up from earlier models. For the first time, we've built a complete desktop experience. Whether you're editing documents, browsing the web with a bunch of tabs open, juggling spreadsheets or drafting a presentation, you'll find the experience smooth and very recognisable — but on a smaller, more energy-efficient and much more cost-effective machine.
### SanDisk Ultra microSD Card
![alt text](./Assets/san-disk-16.png "SanDisk Ultra microSD Card")

This is the SD card you will load the Raspberry Pi operating system onto and place into the Raspberry Pi board.

# Setting up your Raspberry Pi OS
It is now time to set up the Raspbian image on the SD card that you load will into the MicroSD cart slot on the Raspberry Pi. Recently the Raspberry Pi Organization published an Operating System imaging tool that is excellent.

## Setting up Raspberry Pi Imager
Let's get started with the Raspberry Pi Imaging Tool. First watch the short video on using the tool...

### Step #1 - Setup the Imager Tool
[LINK: How to use Raspberry Pi Imager | Install Raspberry Pi OS to your Raspberry Pi (Raspbian)](https://www.youtube.com/watch?v=ntaXWS8Lk34)

Install the Imager tool for your Desktop operating system...

[LINK: Raspberry Pi OS Installation Page](https://www.raspberrypi.org/software/)

![alt text](./Assets/pi-os-installer.png "Install the Raspberry Pi Imager")

Scroll the section, "Install Raspberry Pi OS using Raspberry Pi Imager" and install the software.


### Step #2 - Choose the OS and SD Card

Install the Raspbian OS Image on the SD card.

Install the MicroSD card into the SD writer connected to your desktop or Laptop.

Choose the "Raspberry Pi OS (32 Bit)" to install the whole OS and Desktop.

![alt text](./Assets/pi-os-installer-choose-os.png "Raspberry Pi OS (32 Bit)")

Choose the SD card connected to your computer.

![alt text](./Assets/pi-os-installer-choose-os-card-selected.png "Choose SD")


### Step #3 - Write the OS

Click on the "WRITE" button and allow the process to copy, verify and complete.

![alt text](./Assets/pi-os-installer-completed.png "Pi SD Card Completed")

### Step 4 - Eject the Micro SD card
Right-click on boot (on your desktop or File Explorer) and select the Eject option.

### Step 5 - Install the Micro SD card in the Raspberry Pi
<b>Note:</b> Turn off your Raspberry Pi!

Looking from the top of the RPi, install the SD card (the slot is on the bottom of the board) as shown in the picture below...

![alt text](./Assets/pi-sd.png "Pi SD Card Insert")

<b>CONGRATULATIONS</b> You have installed the Raspbian Operating System for the Raspberry Pi and are now ready to start setting things up for our ColdPack Monitoring Device.

## Configure the Raspberry Pi
Now that we have our SD card loaded with the Raspbian Operating System, we need to boot the Raspberry Pi and using the touchscreen, configure the system and the interfaces. After setting these things up we will be able to log into the Raspbery Pi from another computer and make it easier to program and run applications.

### Step 1 - Plug in a Keyboard and Mouse (or we can use the touchscreen)
We are going to configure the Raspberry Pi using a keyboard and mouse and this is the easiest way to get everything working well and verified.

### Step 2 - Open the Raspberry Pi Configuration
Open "References->Raspberry Pi Configuration"....

![alt text](./Assets/rpi-configuration-step-1.png "Open Pi Config")

On the initial screen, set you password and the name of the instance. I like to use some numbering for my ColdHub pi's so that I can keep track as I test multiple devices...

![alt text](./Assets/rpi-configuration-step-1-open-config.png "Opened Pi Config")

Next, click the "Interfaces" tab and I set all of these to "Enable"...

![alt text](./Assets/rpi-configuration-step-1-set-interfaces.png "Pi Config Set Interfaces")

Click "OK" and respond with "Yes" to reboot the Raspberry Pi and apply the configuration...

![alt text](./Assets/rpi-configuration-step-1-save-reboot.png "Pi Config Save and Reboot")



### Step 3 - Clone the "IoT Central Basic Bootcamp Code and Configuration" Repository
In this step we will clone the code and configuration scripts to the Raspberry Pi. The code and scripts make setting up the Pi for communication, reading sensors and device provisioning in IoT Central... a fully automated process. 

What the scripts and code enable...

* Bring all of the needed application code and configuration scripts to the Pi
* Installation of the Raspberry Pi to use the latest version of Python
* Installation of the Azure IoT SDK for Python
* Installation of the applications that support provisioing of the device and monotoring with telemetry to Azure IoT Central

#### Next we will create our Project folder and clone this repository. 

Let's get started by opening up a terminal window on the Raspberry Pi by clicking the terminal window icon (outlined in the red box at the top menu bar) and then typing "ls" followed by Enter to see list of files and directories.

![alt text](./Assets/rpi-setup-script-1.png "Pi Clone and Setup 1")

Before we can pull the files from GitHub we need to setup our profile. Type the following commands into the terminal window to configure our Git Profile...

``` bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
# Verify
git config --global --list
```


Type the following commands into the terminal window to clone the repository...

``` bash
mkdir Projects
cd Projects
git clone https://github.com/Larouex/iot-central-raspberrypi-hol.git
```

Now we have all we need to configure the Pi for the sessions. Next we will run a setup script and it will automatically confgure everything. Type the following commands into the terminal window...

### Step 4 - Run the Configuration Script

``` bash
# assuming you are still in the Projects folder...
cd iot-central-raspberrypi-hol
git clone https://github.com/Larouex/cold-hub-azure-iot-central.git
```

# Setting up the Development Toolchain for your Workstation
I used the generic term "Workstation" as a way to differentiate that this is the main computer (workstation, laptop, etc.) that you use to do your primary development work. We assume it exists on the same network (if using an ethernet connection) and you can install the tools that will allow you to connect and develop code remotely on the Raspberry Pi.
### Install Git
Git is the tool we use for version control and management of software assets. Our workshop will use it to clone the modules and also to save anything if you want

[LINK: Git Installation Page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Install Visual Studio Code
This is the IDE we will use to write code, deploy to the RPi, etc.

[LINK: Visual Studio Code Installation Page](https://code.visualstudio.com/download)

### Install Python
Pyhon is the language we will use to build applications for the Raspberry Pi

From the Python Org:
* Python is powerful... and fast;
* plays well with others;
* runs everywhere;
* is friendly & easy to learn;
* is Open.

[LINK: Python 3 Installation Page](https://www.python.org/downloads/)

### Upgrading pip
Pip is the package manager we will use to download packages

On Linux or macOS (Open Terminal):
```
    pip install -U pip
```
On Windows (from a CMD window or Powershell):
```
    python -m pip install -U pip
```
### Install all the Tools for Visual Studio Code
These are a set of tools we will use to develop our apps on the Raspberry Pi. You can open the Extensions sidebar with "Shift+Ctrl+X) or click the icon in the side navigator bar.

![alt text](./Assets/vs-code-python-sml.png "VS Code Python")

![alt text](./Assets/vs-code-remote-ssh-sml.png "VS Code Remote SSH")

![alt text](./Assets/vs-code-remote-edit-sml.png "VS Code Remote SSH Edit")

## Connecting to the the Raspberry Pi (SSH)
The requirement in order to connect to your Pi from your computer can be accomplished via Wireless or with an ethernet cable connected to the RPi ethernet port.
### Connecting the Pi with a Monitor, Keyboard and Mouse

If you boot to the command line instead of the desktop, your IP address should be shown in the last few messages before the login prompt.

Using the terminal (boot to the command line or open a Terminal window from the desktop), simply type ...

```bash
hostname -I
```

Which will reveal your Pi's IP address.

### Connecting Headless (no display)
This is the documentation from the Raspberry Pi Foundation and you have a number of options...
https://www.raspberrypi.org/documentation/remote-access/ip-address.md

### Connecting to the Raspberry Pi using SSH
We will be connecting to the Raspberry Pi using the remote SSH capability of Visual Studio Code that we installed as part of our development toolchain. When you set the RPi up, we enabled the device to connect to our Wifi network. 

Now we want to find the IP address of our RPi and connect to via VS Code's Remote SSH tools. This will let us develop our code and test our application working remotely connected to the device.

Here is the documetnation on the extension for VS Code...
[LINK: Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

Here is how we will connect to the Raspberry Pi...
[LINK: Remote development over SSH](https://code.visualstudio.com/remote-tutorials/ssh/getting-started)

## Configuring the Raspberry Pi
Let's get started by making sure our Raspberry Pi (Operating System) is up to date...
``` bash
sudo apt-get update
sudo apt-get upgrade
sudo pip3 install --upgrade setuptools
```
# Modules

## Module 01 - Setting up your Raspberry Pi
[LINK: Module 01 - Setting up your Raspberry Pi](./src/Module01/README.md)

### Video for Module 01 - Setting up your Raspberry Pi
[![](http://img.youtube.com/vi/Bb5ookAZsjI/0.jpg)](http://www.youtube.com/watch?v=Bb5ookAZsjI "Module 01 - Setting up your Raspberry Pi")

## Module 02 - Getting to Know the Raspberry Pi
[LINK: Module 02 - Getting to Know the Raspberry Pi](./src/Module02/README.md)

## Module 03 - Setting up your Development Toolchain
[LINK: Module 03 - Setting up your Development Toolchain](./src/Module03/README.md)

## Module 04 - Enabling Capabilities on the Raspberry Pi
[LINK: Module 04 - Enabling Capabilities on the RPi](./src/Module04/README.md)

## Module 05 - Connecting using SSH to your Raspberry Pi
[LINK: Module 05 - Connecting using SSH to your Raspberry Pi](./src//Module05/README.md)

## Module 06 - Introduction to Breadboarding
[LINK: Module 06 - Introduction to Breadboarding](./src/Module06/README.md)

## Module 07 - Setting up the Raspberry Pi for Running Python Applications
[LINK: Module 07 - Setting up the Raspberry Pi for Running Python Applications](./src/Module07/README.md)

## Module 08 - Communicating with Sensors, LED, etc
[LINK: Module 08 - Communicating with Sensors, LED, etc](./src/Module08/README.md)

## Module 09 - Create your Azure IoT Central Application
[LINK: Module 09 - Create your Azure IoT Central Application](./src/Module09/README.md)

## Module 10 - Connecting to Azure IoT Central (Python SDK)
[LINK: Module 10 - Connecting to Azure IoT Central (Python SDK)](./src/Module10/README.md)

## Module 11 - Device Authentication Types (SaS, Certs, TPM and IR Certs)
[LINK: Module 11 -  Device Authentication Types (SaS, Certs, TPM and IR Certs)](./src/Module11/README.md)

## Module 12 - Sending Telemetry from your Raspberry Pi to IoT Central
[LINK: Module 12 - Sending Telemetry from your Raspberry Pi to IoT Central](./src/Module12/README.md)

## Module 13 - Writing Device Commands and Executing on your Raspberry Pi to/from IoT Central
[LINK: Module 13 - Writing Device Commands and Executing on your Raspberry Pi to/from IoT Central](./src/Module13/README.md)

## Module 14 - Twin Updates and Notifications of Cloud Desired Properties
[LINK: Module 14 - Twin Updates and Notifications of Cloud Desired Properties](./src/Module14/README.md)

## Module 15 - Working with other Cloud Systems (Things Network)
[LINK: Module 15 - Working with other Cloud Systems (Things Network)](./src/Module15/README.md)

## Module 16 - Connecting the Things Network to Azure IoT Central Via Device Bridge
[LINK: Module 16 - Connecting the Things Network to Azure IoT Central Via Device Bridge](./src/Module16/README.md)

## Module 17 - Azure IoT Central Continuous Data Export Scenarios
[LINK: Module 17 - Azure IoT Central Continuous Data Export Scenarios](./src/Module17/README.md)
