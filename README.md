# fabric-home-assistant


 ![image](images/hass_plu_fabric_logo.png)

The "[Raspberry Pi All-In-One Installer](https://github.com/jbags81/fabric-home-assistant)" will deploy a complete Home Assistant server including support for MQTT with websocket support and Z-Wave, including the open-zwave-conrol-panel.

Requirements before installation:
  * You have a Raspberry Pi with a fresh installation of [Raspbian Jessie/Jessie Lite](https://www.raspberrypi.org/downloads/raspbian/) or Debian 8 connected to your network.
  * You are able to SSH into your Raspberry Pi.
  * You've completed all typical new raspberry pi install tasks:
   - Expanded the filesystem
   - Set proper locale and time
   - etc...


Installation instructions:

  1. SSH into your raspberry pi
  2. Run ``` wget -Nnv https://raw.githubusercontent.com/jbags81/fabric-home-assistant/master/hass_rpi_installer.sh && bash hass_rpi_installer.sh; ```
  3. Installation will take approx 1 hour running on a Raspberry Pi 3.


Once rebooted, your Raspberry Pi will be up and running with Home Assistant. You can access it at **http://your_raspberry_pi_ip:8123**.

The Home Assistant configuration is located at ```/home/hass```. The virtualenv with the Home Assistant installation is located at ```/srv/hass/hass_venv```.

Include ```-n``` at the end to install without Virtualenv.

 The All-In-One installer script will do the following automatically:
 *  Create all needed directories
 *  Create needed service accounts
 *  Install OS and Python dependencies
 *  Setup a virtualenv to run Home Assistant and components inside.
 *  Run as a service account
 *  Install Home Assistant
 *  Build and install Mosquitto from source with websocket support
 *  Build and Install Python-openzwave in the Home Assistant virtualenv
 *  Build openzwave-control-panel
 *  Add both Home Assistant and Mosquitto to systemd services to start at boot
