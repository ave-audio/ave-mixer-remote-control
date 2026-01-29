# AVE Digital Mixer Andante V2.0 - Remote Control - User Manual

**AVE Mixer Remote Control** from [AVE GmbH](https://ave-audio.de/en) is a versatile and user-friendly web application designed to manage and control the settings of your AVE Digital Mixer Andante V2.0. This powerful application runs on a Raspberry Pi 4B and is easily accessible via any standard web browser, allowing the mixer’s end-user to seamlessly manage audio configurations.

This manual provides an overview of the user interface (UI) for controlling the **AVE Digital Mixer Andante V2.0** series via the Node-RED platform running on a Raspberry Pi 4B (RPI 4B).

## Main Features

- Web-based access (browser-based, no special client required)
- Access over LAN network
- Intuitive user interface with sliders, buttons, and switches
- Real-time control without technical expertise
- Real-time monitoring and remote control
- Input/Output level adjustment
- Preset selection
- Channel activation/deactivation
- Controllable from any device on the network (Android, macOS, Windows, etc.)
- Supports multiple devices simultaneously
- Very easy to integrate into existing systems

## Typical Applications:
- Conference rooms
- Multi-zone audio systems
- Events & installations
- Remote support / technical assistance
- Multimedia productions

## Overview & Requirements

The UI is structured into various tabs and sections that allow the user to control the inputs, outputs, and presets of the AVE Digital Mixer Andante V2.0, with specific sliders, buttons, and switches for different parameters. The system also **periodically monitors the input/output levels and the currently selected preset**.

### What You’ll Need

- **Router + Access Point**: A standard home router with LAN ports.
- **Raspberry Pi 4B**: Connected to the network via an Ethernet cable.
- **USB to RS232 Adapter (FTDI or Prolific chip recommended)**: For reliable serial communication between the Raspberry Pi and the mixer.
- **AVE Digital Mixer Andante V2.0**: Connected to the Raspberry Pi 4B via the USB to RS232 converter.
- **Ethernet Cable**: To connect the Raspberry Pi 4B to the router.

## System Setup

To get started, follow these steps in order:

### 1. Download the Preconfigured Image

The AVE Mixer Remote Control is distributed as a **preconfigured Raspberry Pi 4B system image**, which includes:

- Operating system
- Node-RED runtime
- Required Node-RED flows
- All necessary dependencies for Andante V2.0 remote control

#### Download Location

Download the ZIP file from the following Dropbox link:

[Download the Raspberry Pi 4B system image (Dropbox)](https://www.dropbox.com/scl/fi/ygcqzvo4ys8bq5b24k0k8/mediaAVE_V1.1_08-10-2024.zip?rlkey=hem2p9laiwqhjms1pz432l38j&dl=0)

### 2. Flash the Image to a microSD Card

1. Extract the downloaded ZIP file to get the `.img` file.
2. Use a tool such as [Raspberry Pi Imager](https://www.raspberrypi.com/software/) or [balenaEtcher](https://etcher.io/) to write the image to a **32 GB or larger microSD card**.
3. Insert the programmed microSD card into your Raspberry Pi 4B.

### 3. Hardware Connections

- Connect a **USB–RS232 adapter** to any USB port on the Raspberry Pi 4B.
- Plug the **DB9 connector** (the other end of the adapter) into the **RS232 serial port** on the rear of the AVE Digital Mixer Andante V2.0.
- Power on both the Raspberry Pi and the mixer.

> 💡 We recommend using an RS232 adapter based on the **FTDI** or **Prolific** chip for best compatibility and performance.

This setup enables direct communication between the Raspberry Pi and the mixer for real-time remote control.

## Setting Up a Minimal LAN Network

This section explains how to set up a basic LAN (Local Area Network) using a common router and connecting your Raspberry Pi 4B to the network via Ethernet.

**Note**: Connecting the Raspberry Pi 4B to the router via Wi-Fi is not recommended. Always use a wired Ethernet connection for stability.

### Step-by-Step Instructions

1. **Connect the Router to Power:**
   - Plug your router into a power outlet and ensure it is switched on. Most routers have LEDs that indicate power and network connectivity.

2. **Set Up the Router's Network:**
   - Connect the router to your modem (if needed) to provide internet access, or simply use it to create a local area network without internet.
   - The router will automatically assign IP addresses to connected devices using DHCP.

3. **Connect the Raspberry Pi 4B via Ethernet:**
   - Connect one end of an Ethernet cable to one of the LAN ports on your router.
   - Connect the other end of the cable to the Ethernet port on your Raspberry Pi 4B.
   - The Raspberry Pi will automatically receive an IP address from the router.

4. **Reserve a Fixed IP Address for the Raspberry Pi 4B:**
   - It is recommended to reserve a **fixed IP address** for the Raspberry Pi 4B to avoid changes in its IP address when reconnecting to the network.
   - To do this, access your router’s admin settings (usually done through a web browser by entering the router's IP address, like `192.168.1.1` or `192.168.0.1`).
   - Look for the **DHCP settings** or **LAN settings** section.
   - Find the Raspberry Pi 4B listed in the **connected devices** section, and reserve its current IP address as static.

5. **Obtain the Raspberry Pi 4B's IP Address:**
   - To access the user interface, you need to know the IP address assigned to the Raspberry Pi. This IP can usually be found in the router's admin page under "connected devices."

6. **Connect Other Devices to the Same Network:**
   - Ensure that any other device (computer, tablet, smartphone) you want to use for accessing the control interface is connected to the same router via LAN or Wi-Fi.

7. **Accessing the User Interface:**
   - Once the Raspberry Pi 4B is connected to the network, open a web browser on any device connected to the same LAN.
   - In the browser's address bar, enter the following URL:
     ```
     http://<RPI4B_IP_address>:1880/ui
     ```
     Replace `<RPI4B_IP_address>` with the actual IP address of the Raspberry Pi. For example:
     ```
     http://192.168.1.100:1880/ui
     ```
   - You will now have access to the remote control UI for the AVE Digital Mixer Andante V2.0.
