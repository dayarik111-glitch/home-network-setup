## Overview
Designed a home network using a star topology and implemented it in my home network. There are six personal desktops that need to utilize the 1 gigabyte of upload and download speed, and a smart TV that can only have a wired connection. Everything else can be connected wirelessly, but I am tasked with prioritizing the desktop PC's upload and download speeds and bringing a network connection to the Smart TV. My internet connection is through my ISP, Verizon. The network uses a fiber connection that requires an ONT to convert optical signals into Ethernet. ONT would be connected to the Verizon G1300 Router, providing my network with a default gateway and internet access. The Router is then connected to my Netgear 8-Port Gigabit Ethernet(GS308E) Layer 2 switch, which acts as a central point for my wired device connections. Everything not connected to the layer 2 switch, such as smartphones or IoT devices, connects wirelessly at either 2.4 GHz or 5 GHz.

## Network Topology

![Home Network Topology](topology.png)
