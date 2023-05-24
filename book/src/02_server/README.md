# The Server

Each server runs (or will run after updates) the latest available version of QTS available from QNAP. QTS is a heavily customized Linux operating system. The main software for use, Calibre-Web, is a web service running in a Docker container that serves as the library for managing published media.

## Tailnet

As part of this deployment, we will also connect the server to a Tailnet, which is a special kind of VPN based on the WireGuard protocol developed by Tailscale, to allow us to properly provide remote technical assistance in a secure manner. The URL for the Tailnet and login credentials will be provided separately from this document.

## First Connection

The units tested have very limited connectivity options upon boot-up, as they do not yet conform to the country's regulatory radio frequency settings.  As such, we recommend connecting to the server from a laptop using an Ethernet cable, to the port labelled LAN1. The port marked WAN is for connecting to the 5G modem, or to any gateway device.

Connecting via WiFi for setup is possible if the proper associated QNAP app is installed. Consult and follow the QNAP documentation for the most up-to-date set-up options if using their app.

Once connected, open a browser and navigate to the IP address: 192.168.100.1.

There, follow the first time setup options. Pay attention to the country settings. Accept the other default options.

## Connecting to the WiFi

The server contains its own wireless router, and is capable of routing network traffic from the Internet from the WAN port, to devices connected to the remaining Ethernet ports, and the WiFi. Details on the default WiFi SSID and password can be found in the sticker on the bottom of the server.

## Admin Account

The login screen for QTS, which is the main web admin interface for running web services is accessible via a web browser once you have connected your device to the WiFi SSID provided by the server, or via Ethernet. The IP address by default should be 192.168.100.100. The login details are:

Username: `admin` 

Password: Check the sticker on the bottom of your device.

We highly recommend you change the default admin account's password to something more secure. Since this is a networked device, there is a risk of your account being compromised if the password is weak. We will try our best to deploy the most hardened system we can to the user, however that will be for naught if the admin password is weak.

Click on the user drop-down arrow, selecting Options > Password Settings, and changing the default admin password to something else more secure. If you have problems with figuring out a secure but memorable passphrase, we recommend the Diceware method of passphrase generation. Afterwards, set up 2-Step Verification as an additional level of protection even if your passphrase is compromised.
