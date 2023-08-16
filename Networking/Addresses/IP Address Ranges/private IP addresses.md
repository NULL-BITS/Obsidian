## Private IP Addresses

Within each network class, there are designated IP address that is reserved specifically for private/internal use only. This IP address cannot be used on Internet-facing devices as that are non-routable. For example, web servers and FTP servers must use non-private IP addresses. However, within your own home or business network, private IP addresses are assigned to your devices (such as workstations, printers, and file servers).

- [[Class A]] Private Range: 10.0.0.0 to 10.255.255.255
- [[Class B]] Private APIPA Range: 169.254.0.0 to 169.254.255.255
    - _Automatic Private IP Addressing_ (APIPA) is a feature with _Microsoft Windows_-based computers to automatically assign itself an IP address within this range if a _Dynamic Host Configuration Protocol_ (DHCP) server is not available on the network. A DHCP server is a network device that is responsible for assigning IP addresses to devices on the network.  
          
        At your home, your Internet modem or router likely provides this functionality. In your work place, a _Microsoft Windows Server_, a network firewall, or some other specialized network device likely provides this functionality for the computer at your work environment.
- [[Class B]] Private Range: 172.16.0.0 to 172.31.255.255
- [[Class C]] Private Range: 192.168.0.0 to 192.168.255.255

## Summary of IPv4 Classes

||Public IP Range|Private IP Range|Subnet Mask|# of Networks|# of Hosts per Network|
|---|---|---|---|---|---|
|Class A|1.0.0.0 to  <br>127.0.0.0|10.0.0.0 to  <br>10.255.255.255|255.0.0.0|126|16,777,214|
|Class B|128.0.0.0 to  <br>191.255.0.0|172.16.0.0 to  <br>172.31.255.255|255.255.0.0|16,382|65,534|
|Class C|192.0.0.0 to  <br>223.255.255.0|192.168.0.0 to  <br>192.168.255.255|255.255.255.0|2,097,150|254|