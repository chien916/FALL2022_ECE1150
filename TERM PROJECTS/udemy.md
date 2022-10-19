 

## Radio Basics

Inverse Square Law

Nodes -> Networks 

ZigBee - WPAN
WIFI - WLAN
LTE - WWAN

## What is ZigBee

Wireless -> WIFI 802.11 -> ZigBee 802.15.4 -> Bluetooth 802.15.1 -> Cellular
Low-Data Rate

### Reliabilities

- Mesh Networking
- IEEE 802.15.4
- 16 bits frame checks for error checking
- Transmission tried for 4 times
- Notification to sending nodes after 4 failures

### Cost-Effective

- Multiple silicon and stack vendors
- Many ZigBee modules
- Many resources
- Low development costs
- No patents

### Low Power  Consumption

- Can run for years on a pair of AA batteries
- With sleep modes and proper power management, long battery life is guaranteed in ZigBee

### Security

- Uses AES 128 bit encryption
- Uses advanced authentication mechanisms
- Any listening node in a secure ZigBee network should have the key and should be authenticated
- Malicious nodes cannot inject false packets into a secured ZigBee network

### Open Global Standard

- Uses IEEE802.15.4 MAC and PHY Layers
- Specification developed and managed by over 250 member companies of ZigBee Alliance
- Application profiles enable interoperability between devices of different vendors

Choices of Radio Vendors, Stack Vendors, Tool Vendors 

## ZigBee vs Bluetooth vs WIFI

###  IEEE 802.11B - WIFI

- High data rate up to 100Mbps
- Typical application is to provide high speed internet access
- The indoor range is from 30 meters to 100 meters
- Used commonly in WIFI routers

### IEEE 802.15.1 - Bluetooth

- Lower data rate of less than 3 Mbps
- The indoor range is form 2 to 10 meters
- Used in Bluetooth headsets

### IEEE 802.15.4 - ZigBee

- Lowest data rate, under 250 Kbps
- Significantly higher battery life
- Ideal for IoT applications
- Most power-efficient and cost-efficient solution for IoT

### Coexistence

- 4% Colliding possibility with Bluetooth
- Coexist with WIFI and Bluetooth

### Disadvantages

- Requires knowledge of the system and experience operating ZigBee devices 
- Not as secure as WIFI
- Replacement cost is high
- Prone to attacks
- Coverage is limited

## Real-world Applications

### Toys and games

Consoles, portables, educational

### Personal health care

Monitors, diagnostics, sensors

### Industrial and commercial

Monitors, sensors, automation controls

### Consumer electronics

TV VCR, DVD/CD, Remote control

### Home automations

security, HVAC, lighting

### PCs and peripherals

mouse, keyboard, joystick

## ZigBee Protocol Stack

### Application (APL) layer - Specified by ZigBee

- ZigBee upper layers

#### Application Support Layer (APS)

- Providing data services and device profiles
- Filtering out duplicate messages sent by network layer
- Keeping and Updating a local binding table which keeps track of nodes the current node wishes to speak to

#### ZigBee Device Object (ZDO)

- Defining device roles within a network
- Handling local & over the air network management
- Providing services for node discovery

#### Application Framework

- Providing a framework for building and running applications
- Defining the description to build a ZigBee profile
- Providing different end points for different applications

### Network (NWK) layer - Specified by ZigBee

- IEEE 802.15.4 LLC, IEEE 802.2 LLC Type1
- Responsible for mesh networking, broadcasting, routing, reliable data transmission
- Handling authentication, secure joining and graceful disconnection
- Handling payload encryption for the network frame

### Medium Access Control (MAC) layer - Specified by IEEE

- IEEE 802.15.4 MAC
- Responsible for reliable communication between nodes
- Manage collision of signals
- Improve efficiency of communication
- Assembling data packets and frames
- Decomposing data packets and frames
- Managing data transaction between neighboring nodes only
- Handling network discovery, identification, packet sync
- Handling acknowledgement and implementing collision avoidance techniques

### Physical (PHY) layer - Specified by IEEE

- IEEE 802.15.4 868 (EU) / 915 MHz (US/AU) PHY
- IEEE 802.15.4 2400 MHz PHY (Worldwide)
- Provides interface to physical transmission medium - Radio
- Defines receiver sensitivity
- Handling channel rejection
- Optimizing output power
- Managing channels
- Defining transmission rate specifications
- Modulation of transmitted signal
- Demodulation of received signal

### *Security Service Provider*

- Talking to APS Sublayer and NWK Layer
- Defining methods for implementing security services
  - Cryptographic key establishment
  - Key transport
  - Frame protection
  - Device management

## Device roles and Network Topologies

### Device Types Pattern

#### Full function devices (FFD)

- Being able to do all operations in the protocol
- Being always powered on
- Being active and listening on the network

#### Reduced function devices (RFD)

- Limited version of FFD
- Doesn't manage discovery and device management in the network
- Performs basic message transfer and control operations
- Have limited memory and will be running on battery
- Sleep most of the time to save battery

### Device  Types in ZigBee

#### Coordinator (FFD)

- Forming network
- Assigning dynamic addresses
- Securing the network
- Maintaining network health
- Buffering data packets for sleeping and devices.

A ZigBee network can only have 1 coordinator and it will be always powered.

#### Router (FFD)

- Joining existing networks and handle connection
- Intelligently route the packets from end devices
- Extends the range of the network using multi hopping techniques
- All routers must be always powered on

A ZigBee network can have multiple or no routers.

#### End Device (RFD)

- Have low processing capabilities and memory to reduce power consumption.
- Essentially a router with sleep mode enabled
- Used in place of routers when power consumption of routers are excessive.
- Can only join a network and communicate with each other nodes
- Have the capacity to power itself town.

### Types of Coordinators

#### ZigBee Gateways (ESP32)

#### ZigBee Trust Center

### Device Addressing

#### 64 Bit Serial Number (MAC)

- Each radio has a unique and permanently assigned 64-bit serial number
- Up to the OEM making the board to write to flash

#### Coordinator-assigned 16 Bit Address (NWK)

- Assigned by the network layer of ZigBee in addition to MAC address
- A look-up table is used to map each of the MAC address to the 16-bit address.
- Unique only within a given network.
- This reduced address enables ZigBee chips to work on low-memory sized chip.

#### Node Identifier Name

- Short string of text which allows the radio to be addressed with a more human-friendly name.
- Allows for easy management of devices if there are hundreds of them

#### Personal Area Network ID (PAN)

- Used to differentiate identical NWK address from different networks.

#### Communication Channel

- The radios need to be on same channel
- The radios must have the same PAN ID
- The transmitting radio should know either 64 bit address, 16 bit address, or node identifier String for receiving radio addresses
- The radios must exchange encryption keys if the security is enabled

## ZigBee Application Profiles

- Each profile defines the type of devices and device functionalities
- Application profiles allows further interoperability
- Cross compatibility between products produced by different vendors.
- Collection of common definitions and protocols that allow different devices to work together under a particular application

### Clusters

### Endpoints

### Public Application Profiles

### Manufacturer Specific Application Profiles
