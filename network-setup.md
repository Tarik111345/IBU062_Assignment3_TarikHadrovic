# Network setup

## Devices in the Network

### Router:
- Model: Cisco 1841
- IP Address (FastEthernet0/0)**: 168.90.0.1
- IP Address (FastEthernet0/1)**: 210.3.14.1 

### Switch1:
- Model:2960-24TT
 

### Switch2:
- Model: 2960-24TT

### PC1:
- Model: PC
- IP Address: 168.90.0.2 
- Default Gateway: 168.90.0.1

### PC2
- Model:PC
- IP Address: 168.90.0.3
- Default Gateway: 168.90.0.1

### Laptop0:
- Model: Laptop
- IP Address: 168.90.0.4
- Default Gateway: 168.90.0.1

### Server:
- Model: Server
- IP Address: 168.90.0.5
- Default Gateway: 168.90.0.1

### Server1:
- Model: Server
- IP Address: 210.3.14.2
- Default Gateway: 210.3.14.1

### Server2:
- Model: Server
- IP Address: 210.3.14.3
- Default Gateway: 210.3.14.1

### PC
- Model: PC
- IP Address: 210.3.14.4
- Default Gateway: 210.3.14.1

### PC3:
- Model: PC
- IP Address: 168.90.0.6
- Default Gateway: 168.90.0.1

### PC4:
- Model: PC
- IP Address: 210.3.14.5
- Default Gateway: 210.3.14.1



### DHCP Configuration on Router
To configure the router to assign IP addresses dynamically to the devices in the network, follow these steps.

1. Enter Global Configuration Mode
To begin, access the global configuration mode on the router:

configure terminal

2. Define the DHCP Pool
Create a DHCP pool named DHCP_POOL for the network 168.90.0.0:

ip dhcp pool DHCP_POOL
3. Set the Network for the DHCP Pool
Define the network and subnet mask from which the router will assign IP addresses:

network 168.90.0.0 255.255.255.0
4. Set the Default Gateway for DHCP Clients
Define the default gateway (router's IP) to be assigned to the DHCP clients:

default-router 168.90.0.1
5. Set the DNS Server for DHCP Clients (Optional)
You can also specify the DNS server to be used by the clients:

dns-server 168.90.0.1
6. Exclude the Router’s IP Address from the DHCP Pool
Ensure that the router’s own IP address (168.90.0.1) is not assigned to any client. This can be done by excluding the address from the DHCP pool:

ip dhcp excluded-address 168.90.0.1
7. Exit Configuration Mode
After completing the DHCP setup, exit from global configuration mode:

exit

Save the configuration on the router: After making all the changes, don't forget to save the configuration on the router to prevent it from being lost after a reboot:

write memory

