# CCNA-projects
All the projects that helped me to learn the basic to advance of networking are listed in this repo.


hello there, this is my tenth day of learning CCNA and now i am doing my first project of CCNA i.e. creating Vlan and communicating within the VLANs.

VLAN stands for a virtual local area network, additionally referred to as a Logical Network VLAN can logically create many virtual networks to split network broadcast traffic. VLANs are primarily based totally on logical connections, So it facilitates minimizing broadcasting traffic, and management work could be accomplished quickly.

VLANs also can enhance the network’s overall performance due to the fact VLANs make organizations of devices that communicate very frequently.
Modes of Switch port: 
Administrative mode: 
This Switch Port mode is configured by the admin.
Types of Administrative mode: 
Static Access – (no negotiation of the trunk)
Static Trunk – (forces formation of the trunk)
Dynamic Desirable – (initiates negotiation of the trunk)
Dynamic Auto – (wait for the negotiation of the trunk)

Operational Mode: 
This is the resulting mode of the Switch Port after the negotiation (the result of the configuration done by the admin).
Types of Operational mode:
Access Mode – If the port is in access mode then the port can carry only one VLAN data. It is only configured on the ports connected to the end users.

switch(config)#int <interface_id>
switch(config-if)#Switch Port mode access
Trunk Mode -If the port is in Trunk mode then the port can carry multiple VLAN data using the Layer 2 encapsulation protocol (either Dot1Q or ISL).

switch(config)#int <interface_id>
switch(config-if)#Switch Port mode trunk



Steps to Configure and Verify the Normal Range VLAN Spanning Multiple Switches:
Step 1: Create a network topology with the help of two LAN networks, VLAN10 and VLAN20.Now configure and Verify the Normal range VLAN spanning multiple switches:

S.NO	Device 	Model Name	Quantity
1.	PC	PC	4
2.	Switch	PT-Switch	2
3.	cable	automatically chosen cable	None
IP Addressing Table:

S.No	Device	IPv4 Address	Subnet Mask(you can set the ip according to your choice)
1.	PC0	192.168.0.1	255.255.255.0
2.	PC1	192.168.0.2	255.255.255.0
3.	PC2	192.168.0.3	255.255.255.0
4.	PC3	192.168.0.4	255.255.255.0

In the above representation, we can see that we have created two Virtual LANs. We have not configured switches yet, So if we try two Send PDU from one host to another then it will respond and send replies because switches are multicast devices.

In this experiment, we have to create a logical network :

For example, we have created two Virtual LANs groups vlan10 and vlan20 so we have to configure switches in such a way that we can communicate with devices that come under the VLANs group In VLAN20 if we ping PC3 IP address in PC0 then we’ll surely getting replies but if we try to ping the IP address of the different VLAN group then we get an error because it belongs from different VLAN group.

Step 2: Configure Switches and Separate VLANs:

CLI commands for creation of VLAN on cisco Switch0:
switch> enable
switch# configure terminal
switch(config)# vlan {vlan-id}
switch(config-vlan)# name {VLAN name}
switch(config-vlan)#do wr
switch(config-vlan)#do sh vlan brief

Configuring and Verifying an Interface for a VLAN:
switch# interface {port_name}
switch# switchport mode access (for access vlan i.e assigned on the switch port connected to end device such as pc, printer,mobile etc).
switch# switchport access vlan {vlan id}

switch# interface {port_name}
switch# switchport mode trunk (for trunk vlan i.e assigned to switch to switch , etc)


After separating these two VLANs we need to verify the connection by pinging the IP address :






