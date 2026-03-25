## Overview
Designed a home network using a star topology and implemented it in my home network. There are six personal desktops that need to utilize the 1 gigabyte of upload and download speed, and a smart TV that can only have a wired connection. Everything else can be connected wirelessly, but I am tasked with prioritizing the desktop PC's upload and download speeds and bringing a network connection to the Smart TV. 

My internet connection is through my ISP, Verizon. The network uses a fiber connection that requires an ONT (Optical Network Terminal) to convert optical signals into Ethernet. The ONT connects to the Verizon G1300 Router, providing my network with a default gateway and internet access. The Router is then connected to my Netgear 8-Port Gigabit Ethernet(GS308E) Layer 2 switch, which acts as a central point for my wired device connections. 

Everything not connected to the layer 2 switch, such as smartphones or IoT devices, connects wirelessly at either 2.4 GHz or 5 GHz.

## Network Topology

![Home Network Topology](image/Home%20Network%20Topology.png)

## Service Provider

- ISP: Verizon FiOS

## Hardware

- ONT (ISP provided)
- Router: Verizon G1300
- Switch: Netgear GS308E (Layer 2)
- Cabling: Cat6 Ethernet
- Devices: 6 Desktop PCs, 1 Smart TV

## Network Configuration

- DHCP Enabled
- Private IP Range: 192.168.1.0/24
- Default Gateway: 192.168.1.1
- Wired Connections: 1 Gbps (Cat6 Ethernet)

## Troubleshooting

### Issue: Limited Network Speed (100 Mbps instead of 1 Gbps)

One of my desktop PCs was only receiving 100/100 Mbps instead of the expected 1 Gbps.

---

### Step 1: Identified the issue in Windows settings  
![100 Mbps Link Speed](image/100mbps-transmit.png)

---

### Step 2: Opened Device Manager using Run  
![Run Dialog](image/rundialog.png)

---

### Step 3: Navigated to Network Adapters  
![Device Manager](image/devicemanagement.png)

---

### Step 4: Found incorrect Speed & Duplex setting  
![Speed & Duplex 100 Mbps](image/100mbps.png)

---

### Step 5: Changed to Auto Negotiation  
![Auto Negotiation](image/autonegotiation.png)

---

### Step 6: Verified 1 Gbps link speed  
![1 Gbps Link Speed](image/1gbps-transmit-update.png)

---

### Step 7: Verified with speed test (~900+ Mbps)  
![Speed Test](image/speedtest.png)

### Root Cause
The network adapter's Speed & Duplex setting was set to 100 Mbps Full Duplex, which limited the link speed and did not meet expectations.

### Resolution
Changing the setting to Auto Negotiation allowed the adapter to negotiate the correct speed of 1 Gbps.

### Result
The link speed was updated to 1000/1000 Mbps, and performance was verified with a speed test (~900+ Mbps).

The importance of checking the NIC configuration settings is important when diagnosing network speed, especially if the speed does not meet expectations.

### Ticket Summary (Simulated)

Issue: User Network speed is limited to 100 Mbps  
Cause: Incorrect NIC Speed & Duplex setting  
Resolution: Set to Auto Negotiation ww 
Status: Resolved

## Skills Demonstrated

- Network architecture planning
- TCP/IP fundamentals
- DHCP configuration
- Layer 2 switching
- Network troubleshooting
- NIC configuration (Speed & Duplex)
- Structured cabling
- Network documentation
