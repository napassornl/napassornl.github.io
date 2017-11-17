---
layout: post
title: "Network Security Program"
author: "Napassorn Lerdsudwichai"
categories: resources
tags: [resources]
image:
  feature: security.jpg
---

[**Network Monitoring Github**](https://github.com/napassornl/Network-Security)

# Program Components
## IP packets
When two host are communicating with each other via the Internet, the source host send a message to the destination host through a stack of layers aka. the Protocol Stack.
![Alt](https://networklessons.com/wp-content/uploads/2015/07/ip-packet-header-fields.png)

## White List
A white list is a register of items that are granted access to a certain system or protocol. When it is used, all entities are denied access except those included in the whitelist. In our project, the whitelist is a list of IPv4 address objects that stores the IP address and other information such as subnet mask, etc. The IPv4 objects are from the Python ipaddress module. The ipaddress module has a method to generate the IP address from the IPv4 Network.   

To get more information besides the IP address, I have written a Python script that parses through the raw data packets received from the socket or application-transport interface. Thus, using the struct method, we are able to get and display the information of the IP packet as shown above: 

# Program Run Down
The whitelist program lets the user specify the whitelist in the CIDR (Classless Inter-Domain Routing) format and writes the list as a text file to be uploaded when network monitor program is intialized.    

The network monitor program then opens the text file and makes each element in the file a IPv4 Network which consists of IPv4 address objects. There may be many IPv4 Network objects so they are all stored in an array.  

When our host receives a data packet from the internet, the network sniffer program intercepts the packet from the socket and checks whether the IPv4 address matches those generated from the whitelist. If there is a match, the data packet is allowed to proceed otherwise the program blocks the packet and prints an error message.   

As packets keep coming in, the program records the statistics of packets being accepted or dropped and then writes them into a file or displays it in the user interface.

# Deliverables and Conclusion

This project is still ongoing so stay tune for updates!

[Photo Credits](https://blog.equinix.com/blog/2017/08/24/how-to-create-a-security-inspection-zone-at-the-digital-edge/)
