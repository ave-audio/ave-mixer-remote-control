# AVE Digital Mixer Andante V2.0 - Remote Control - User Manual

<p align="center">
  <img src="PATH_TO_IMAGE" alt="AVE Mixer Remote Control - Connection Diagram" width="85%" />
</p>

**AVE Mixer Remote Control** from [AVE GmbH](https://ave-audio.de/en) is a versatile and user-friendly web application designed to manage and control the settings of your AVE Digital Mixer Andante V2.0. This powerful application runs on a Raspberry Pi 4B and is easily accessible via any standard web browser, allowing the mixer’s end-user to seamlessly manage audio configurations.

This manual provides an overview of the user interface (UI) for controlling the **AVE Digital Mixer Andante V2.0** series via the Node-RED platform running on a Raspberry Pi 4B (RPI 4B).

## Overview

The UI is structured into various tabs and sections that allow the user to control the inputs, outputs, and presets of the AVE Digital Mixer Andante V2.0, with specific sliders, buttons, and switches for different parameters. The system also **periodically monitors the input/output levels and the currently selected preset**.

### System Setup

- **Platform**: The Node-RED code is pre-installed on a custom image designed to run on a Raspberry Pi 4B.
- **Hardware Requirements**:
   - A **USB to RS232 converter** must be connected to one of the USB ports of the Raspberry Pi 4B.
   - The **DB9 connector** of the USB to RS232 cable must be connected to the rear serial port of the **AVE Digital Mixer Andante V2.0** devices.

## Raspberry Pi 4B Image Download

The AVE Mixer Remote Control is distributed as a **preconfigured Raspberry Pi 4B system image**, which already includes:

- Operating system
- Node-RED runtime
- Required Node-RED flows
- All necessary dependencies for Andante V2.0 remote control

### Download Location

The Raspberry Pi 4B image can be downloaded from the following Dropbox link:

[Download the Raspberry Pi 4B system image (Dropbox)](https://www.dropbox.com/scl/fi/ygcqzvo4ys8bq5b24k0k8/mediaAVE_V1.1_08-10-2024.zip?rlkey=hem2p9laiwqhjms1pz432l38j&dl=0)

## Setting Up a Minimal LAN Network

This section explains how to set up a basic LAN (Local Area Network) using a common router and connecting your Raspberry Pi 4B to the network via Ethernet.

**Note**: Connecting the Raspberry Pi 4B to the router via Wi-Fi is not recommended. Always use a wired Ethernet connection for stability.

### What You’ll Need

- **Router + Access Point**: A standard home router with LAN ports.
- **Raspberry Pi 4B**: Connected to the network via an Ethernet cable.
- **AVE Digital Mixer Andante V2.0**: Connected to the Raspberry Pi 4B via the USB to RS232 converter.
- **Ethernet Cable**: To connect the Raspberry Pi 4B to the router.

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
   
   **Note**: A common user typically does not have direct access to the Raspberry Pi’s terminal, so IP reservation should be done via the router's interface.

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

### Notes

- Using an Ethernet cable is the recommended and most stable method of connecting the Raspberry Pi 4B to the network.
- Ensure that a fixed IP is reserved for the Raspberry Pi 4B to make future connections consistent.

## Tabs Overview

1. **Presets Tab** (`PRESETS`)
   
   <p align="center">
     <img src="https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Presets%20Panel.jpg" alt="Snapshot 1" width="75%" />
   </p>

   - Switch between different preset configurations using buttons. Each preset button is dynamically labeled with its name.
   - The buttons also change color based on the currently selected preset.
   - **Note**: The remote control system periodically monitors the currently selected preset.

2. **Inputs Tab** (`INPUTS`)

   <p align="center">
     <img src="https://github.com/ave-audio/ave-mixer-remote-control/blob/7a6c2350dd967b06446d3150658b27d24e57101b/images/Andante%20Remote%20Control%20V2.0%20-%20Setup%20Diagram.jpg" alt="Snapshot 2" width="75%" />   
   </p>

   - Manage different audio inputs via sliders and text fields that show percentage levels for each input.
   - Each input has a fader control for volume adjustment and a display of the current percentage level.
   - Each input channel also includes a **switch** to enable or disable the channel, allowing the user to easily control the active status of the input channels.

3. **Outputs Tab** (`OUTPUTS`)

   <p align="center">
     <img src="https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Outputs%20Panel.jpg" alt="Snapshot 3" width="75%" />   
   </p>

   - Adjust audio outputs, with faders for controlling the master level and individual output levels.
   - Each output has controls similar to the input interface (fader and percentage display).
   - Each output channel also includes a **switch** to enable or disable the output channel, giving full control over the active status of each output.

4. **Info Tab** (`INFO`)

   <p align="center">
     <img src="https://github.com/ave-audio/ave-mixer-remote-control/blob/9e37db7ad3867cccc6f01de6082015b047c4b849/images/Andante%20Remote%20Control%20V2.0%20-%20Info%20Panel.jpg" alt="Snapshot 4" width="75%" />   
   </p>

   - Provides information about the device, such as the device name, firmware versions (MCU and DSP), and other status-related information.
   - No control elements, only for displaying read-only data.

## Main Functional Elements

### Presets

- **Preset Buttons**: Switch between preset configurations using labeled buttons. Each button reflects the preset name and changes its background color to indicate which preset is currently active.

### Input Control

Each input has the following controls:

- **Fader**: Adjust the volume level from 0 to 140.
- **Percentage Level**: Shows the current level as a percentage, based on the fader position.
- **Switch**: Toggle each input between active and inactive states.
- **Note**: The system periodically monitors the input levels.

### Output Control

Each output has:

- **Master Level Control**: A fader to adjust the global output level.
- **Individual Output Faders**: Adjust the level of each output channel.
- **Percentage Display**: Shows the current output level in percentage format.
- **Note**: The system periodically monitors the output levels.

## Additional Notes

- The system allows real-time adjustments, meaning changes made via the UI immediately affect the mixer settings.
- Ensure that the **USB to RS232 converter** is correctly plugged into the Raspberry Pi 4B and that the DB9 connector is securely attached to the Andante mixer’s serial port.

## License

This application is the property of AVE GmbH and all rights are reserved. Unauthorized copying, modification, or distribution of this software is strictly prohibited.
Contact

For any questions or suggestions, please open an issue on GitHub or contact us at info@ave-stuttgart.de.

## Manufacturer

**AVE GmbH**  
Gustav-Rau-Str. 6  
74321 - Bietigheim-Bissingen  
Deutschland  
Tel.: +49 7142-78879-0  
Fax: +49 7142-78879-18  
Email: info@ave-stuttgart.de

**All rights reserved 2026.**
