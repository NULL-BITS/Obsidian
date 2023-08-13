## What is a MAC address?

Each device that is integrated into a computer network requires a network adaptor. This adapter receives a worldwide unique identification number from the manufacturer: the MAC address. This enables devices like desktop computers, tablets, or mobile phones to be identified in the network and addressed as required. If a device has several network adapters (for example, for several LAN connections or different communication standards like Ethernet, WiFi, FDDI, Bluetooth, or Token Ring), a different address is available for each standard.

Definition

The MAC address (short for media access control address) is the worldwide unique hardware address of a single network adapter. The physical address is used to identify a device in computer networks.

Since MAC addresses are assigned directly by the hardware manufacturer, they are also referred to as hardware addresses. With Microsoft Windows, the MAC address is referred to as the physical address. Apple uses the terms Ethernet ID, Airport ID, or WiFi address, depending on the communication standard. The term device address, on the other hand, is fuzzy, since a device can have several network adapters and therefore different MAC addresses.

### The MAC address in practice

Conflicting MAC addresses are a basic requirement for error-free network communication.

Data transmission in computer networks is a complex communication process in which different requirements including reliability, security, and efficiency must be met. This can be illustrated using the [OSI models](https://www.ionos.com/digitalguide/server/know-how/the-osi-model-a-reference-for-standards-and-protocols/ "The OSI model: a reference for standards and protocols") (abbreviation for open systems interconnection) – a reference model developed by the ISO (International Organization for Standardization) that maps network communication to 7 layers. During data transmission, each layer of the OSI model is run through on both the sender and receiver sides.

MAC addresses are used on the backup layer (layer 2) of the OSI model – actually, the media access control sublayer introduced by the Institute of Electrical and Electronics Engineers (IEEE).

Note

In the extension of the OSI model designed by the IEEE, the backup layer (layer 2) is divided into the sublayers media access control (2a) and logical link control (2b).

The backup layer is located between the bit transfer layer (layer 1) and the switching layer (layer 3). While the bit transmission layer provides protocols and tools responsible for maintaining the physical connection, protocols on the backup layer control how different systems share the available transmission medium. Secure system connections are abstracted from the physical connection. The actual transmission of data packets takes place at the switching level via IP.

For example, if you want to send an IP packet over Ethernet, your computer transmits a data frame that is addressed to the target computer’s MAC address on the backup layer, according to the OSI model.

Note

If the target computer is not in the local network, a router is addressed and instructed to forward it to the internet. Routers integrated into a social network also have a unique MAC address.

An Ethernet data frame contains information that is read out at different levels of the OSI model.

Data frames in IPv4 networks contain the following components:

- Destination address (destination computer MAC address)
- Source address (sender’s MAC address)
- Control information for data flow control
- User data (the data packet that needs to be transmitted later on the switching layer)
- Checksums that ensure data integrity

A target computer that receives a data frame first reads it on the backup layer and compares the target address of the frame with its own MAC address. If the addresses match, the target computer starts interpreting the frame at the next higher level.

Note

Network devices that are only used to forward data packets (repeaters) or manage parts of the network (bridges and switches) usually do not actively participate in network communication and so do not require their own MAC addresses.

To link the address assignment on the backup layer with the address assignment on the switching layer, the [address resolution protocol (ARP)](https://www.ionos.com/digitalguide/server/know-how/what-is-arp-address-resolution-in-networks/ "What is ARP? – Address resolution in networks") is used in IPv4 networks. Each computer in the local network maintains an ARP table whereby IP addresses are assigned to MAC addresses.

Tip

ARP is vulnerable to an attack pattern called [ARP spoofing](https://www.ionos.com/digitalguide/server/security/arp-spoofing-attacks-from-the-internal-network/ "ARP Spoofing: Attacks from the internal network"). The danger of ARP spoofing and the countermeasures you can take are discussed in the article above.

The new internet protocol standard IPv6 uses the [neighbor discovery protocol (NDP)](https://www.ionos.com/digitalguide/server/know-how/what-is-neighborhood-discovery-protocolndp/ "What is Neighborhood Discovery Protocol(NDP)?").

### MAC address syntax

MAC addresses in LAN or WLAN networks consist of 6 bytes (48 bits) and are written in hexadecimal notation. The use of separators such as hyphens or colons between two bytes increases readability.

The following example shows the MAC address of a desktop computer in binary and hexadecimal format:

```none
00110101 01101000 10110100 00000010 00010011 10011000 
```

```none
AC-16-2D-02-C8-19
```

Note

In our example, we use **canonical representation** of the bit sequence. This corresponds to the order in which MAC addresses are transmitted in Ethernet. Other communication standards like Token Ring provide for **bit-reversed transmission**, starting with the most significant bit.

The bit sequence of each MAC address is divided into 4 areas, each of which encodes different information.

- **Bit 1 (receiver):** The first bit of the MAC address specifies whether it is an individual or group address. This bit is called I/G (short for individual/group). If I/G = 0, it is a unicast address for a single network adapter. Multicast addresses are identified by I/G = 1 and are addressed to several receivers.
- **Bit 2 (registry):** The second bit of the MAC address indicates whether it is an address with global validity (universal) or whether the address has been assigned locally (local). The bit is called U/L. If U/L = 0, the address is valid worldwide as a universally administered address (UAA). Addresses that are only locally unique are called locally administered address (LAA) and are marked with U/L = 1.
- **Bit 3–24 (manufacturer identification):** Bits 3 to 24 encode an identifier (organizationally unique identifier, OUI), which is assigned exclusively to hardware manufacturers by [IEEE](https://www.ieee.org/ "IEEE Homepage"). The assignment of OUIs is usually public and can be determined via databases. A corresponding service is available, for example, on [aruljohn.com](https://aruljohn.com/mac.pl "query on aruljohn.com").
- **Bit 25-48 (network adapter identifier):** Bits 25 to 48 provide device manufacturers with 24 bits for assigning a unique hardware identifier (organizationally unique address, OUA). This means that 224 (= 16.777.216) unique OUAs can be assigned per OUI.

**Table: Subareas of an MAC address**

|   |   |   |   |   |
|---|---|---|---|---|
|**Label**|**I/G**|**U/L**|**OUI**|**OUA**|
|**Bit**|1.|2.|3.–24.|25.–48.|
|**Function**|Recipient group|Awarding office|Manufacturer code|Network adapter identification|

## Finding out your MAC address: a how-to guide

MAC addresses can be queried through the terminal in all modern operating systems with little effort – both on the local system and remotely in the network. The following table shows the corresponding command line commands for the most common operating systems.

**Table: MAC address read out**

|Operating system|Terminal command|Remote|
|---|---|---|
|FreeBSD|ifconfig|arp -a|
|NetBSD|ifconfig -a|arp -a|
|OpenBSD|ifconfig -a|arp -a|
|Linux|ip link|ip neigh|
|Mac OS X / macOS|ifconfig|arp -a|
|Solaris|ifconfig -a|arp -a|
|Windows XP Professional|getmac /v|arp -a|
|Windows (ab 2000)|ipconfig /all|arp -a|

On mobile devices, you can display the MAC address in the settings.

**Table: Get MAC addresses on mobile devices**

|Operating system|Local|
|---|---|
|Android|Settings > Phone Information > Hardware Information|
|Apple iOS|Settings > General > Info > WiFi address|
|Windows Phone 7|Settings > Info > More Information|

### Read MAC address locally

If you want to read out the MAC addresses of the LAN and WiFi adapters on your Windows computer, proceed as follows if using Windows 10.

**Step 1:** Open the terminal of your operating system. For example, use the keyboard shortcuts [Windows button]+[R]. Then enter “cmd” in the window “Run” and confirm with “OK.”

[![“Run” window on Windows](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address.png "“Run” window on Windows")](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address.png)

With the Windows program “Run” you open programs, folders, or documents through the respective file name, if the file is available through a standard path.

**Step 2:** From Windows 2000 onwards you can use the command line utility [ipconfig](https://www.ionos.com/digitalguide/server/configuration/ipconfig/ "Ipconfig") with the “/all” option to get the MAC address of all network adapters on your Windows computer.

```none
Ipconfig /all
```

[![The terminal on Windows 10 Enterprise](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address2.png "The terminal on Windows 10 Enterprise")](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address2.png)

Use the terminal command “ipconfig/ all” to read the address data of your local network. The terminal output contains information about the Windows IP configuration and all local system network adapters.

Tip

Alternatively get the MAC address with the command “getmac /v”

**Step 3**: With Windows, the MAC address is displayed under “physical address.”

[![An example of a terminal output after the command “ipconfig /all”](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address3.png "An example of a terminal output after the command “ipconfig /all”")](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address3.png)

The terminal output following the command “ipconfig /all” contains detailed information about the installed network adapters. Each adapter’s MAC address is output as physical address with Windows.

### Accessing your MAC address remotely

Thanks to ARP, in IPv4 networks it is possible to determine other devices’ MAC addresses in the same local network. With Windows and most unixoid operating systems, use the command line “arp” with the option to display you system’s ARP table in the terminal.

```none
arp -a 
```

You will receive a terminal output according to the following scheme:

```none
Serial interface: 172.24.0.113 --- 0x2
  Internetaddress      Physical. Adress         Type
  172.24.0.111            00-80-41-AE-FD-7E     dynamic
  172.24.0.112            12-34-56-78-9A-BC     dynamic
```

If you just want to read the MAC address of a specific network adapter remotely, use the command “arp –a” in a combination with the target adapter’s local IPv4 address.

```none
arp -a 172.24.0.112
```

## Assigning the MAC address using software

MAC addresses are invariably assigned by device manufacturers and are “burned” into the network adapter chip on the hardware side. However, numerous operating systems offer the option to overwrite hardware addresses on the software side. This is referred to as spoofing. In this case, a system does not send the addressed adapter’s real network hardware address in network communication, but instead a user-defined MAC address.

### Assigning an MAC address in Windows

With Windows, you can overwrite the MAC address through the device manager if the network adapter’s device driver supports this function.

**Step 1:** Open the network adapter settings. To do this, follow the click path: Start à Settings à Network and Internet à Ethernet à Change Adapter Options

**Step 2:** Right-click on the desired network adapter and select “Disable” in the context menu.

**Step 3:** Right-click on the desired network adapter and select “Properties” from the context menu. A pop-up window opens called “Network adapter properties.”

**Step 4:** Click on the “Configure” button in the pop-up window and select the “Locally Administered Address” property under “Advanced.” Enter your chosen software MAC address under “Value.”

[![Network adapter pop-up window](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address4.png "Network adapter pop-up window")](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Screenshots_2018/EN-mac-address4.png)

Not all network adapters support assigning MAC addresses with software.

### Assign MAC address in unixoid operating systems

Unix derivatives such as Linux, macOS, Solaris, and the BSD operating systems support the assignment of MAC addresses through the terminal on the software side.

**Table: Overwriting a MAC address**

|   |   |
|---|---|
|**Operating system**|**Terminal command**|
|Linux|_ip link set dev <Interface> addr XX:XX:XX:XX:XX:XX_<br><br>or<br><br>_ifconfig <Interface> promisc_<br><br>and finally<br><br>_ifconfig <Interface> hw ether XX:XX:XX:XX:XX:XX_|
|Mac OS X / macOS|_ifconfig <Interface> ether XX:XX:XX:XX:XX:XX_|
|Solaris|_ifconfig <Interface> ether XX:XX:XX:XX:XX:XX_|
|FreeBSD|_ifconfig <Interface> link XX:XX:XX:XX:XX:XX_|
|NetBSD|_ifconfig <Interface> link XX:XX:XX:XX:XX:XX activate_|
|OpenBSD|_ifconfig <Interface> lladdr XX:XX:XX:XX:XX:XX_|

We illustrate the procedure using the most commonly used Unix derivative: Linux. If you want to change your network adapter’s MAC address, proceed as follows.

**Step 1:** Open the operating system terminal – for example, with the key combination [CTRL]+[ALT]+[T].

**Step 2:** Determine the name and current MAC address of the desired network adapter. To do this, enter the following command in the command line:

```none
ip link
```

Tip

Note the hardware address assigned by the manufacturer in case you want to undo the change.

**Step 3:** Turn off the network adapter by entering the following command in the command line:

```none
ip link set dev <Interface> down
```

Note

Enter the name of the network adapter determined through “ip link” for <Interface>.

**Step 4:** Overwrite the network address assigned by the manufacturer with one of the options specified in the table.

```none
ip link set dev <Interface> addr XX:XX:XX:XX:XX:XX
```

Note

Enter the chosen MAC address instead of XX:XX:XX:XX:XX:XX

**Step 5:** Restart the network adapter. Use the following command line command:

```none
ip link set dev <Interface> up

```

To ensure that the selected network adapter is accessible at the MAC address you selected, re-read the network information with “ip link” (see step 1).