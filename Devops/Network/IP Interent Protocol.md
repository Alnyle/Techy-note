IP like phone numbers devices use them to communicate with each

#### How device get their IP address
every time your device connect to the **Router** give your device IP address through protocol call DHCP

#### IP address looks like
IPv4 address is 32 binary digits (or bits)  split into four octets_. These are called octets because they are 8-bit numbers, in decimal ranging from 0–255, or in hexadecimal.

- example for IP address: 192.158.1.38
- 
Every IP address has two parts. The first part indicates which network the address belongs to. The second part specifies the device within that network. However, the length of the "first part" changes depending on the network's class.

###### But how do you know what part is for the network and what part is for the hosts?

To distinguish between the network portion and the host portion of an IP address, you use a subnet mask or CIDR (Classless Inter-Domain Routing) notation. The subnet mask defines which part of the IP address is designated for the network and which part is for the hosts within that network. Here's how it works:

### **Subnet Mask:**

- **Subnet Mask**: A subnet mask is a 32-bit number that masks an IP address and divides the IP address into network and host portions. It's written in decimal format like an IP address (e.g., 255.255.255.0).
- The bits in the subnet mask that are set to `1` represent the network portion of the address, while the bits set to `0` represent the host portion.
    - For example, with a subnet mask of `255.255.255.0`, the first 24 bits (255.255.255) are for the network, and the last 8 bits (.0) are for hosts which mean we  there there **256** IP address for host but actually there 253 IP address for host because there IP address reserved for (192.128.1.23)
	    - Network address which always take : 192.128.1.0
	    - Gate Way (Router) address: 192.128.1.1 
	    - Broadcast address: 192.128.1.255 (if router send package on this route it's mean it arrive to all device in the network) 




### how 


