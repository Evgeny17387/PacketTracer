# Network
![](network.PNG)</br>

# Description
Network Components</br>
1. Router</br>
1. 2 Swtiches, one for earch subnet</br>
1. 4 Host PCs, 2 for each sunet</br>

# Configuation
1. Host PC0 and PC1 configured with IPs 10.0.0.2 and 10.0.0.3, SubNetMask is 255.255.255.0, Default GW is 10.0.0.1</br>
2. Host PC2 and PC3 configured with IPs 192.168.0.2 and 192.168.0.3, SubNetMask is 255.255.255.0, Default GW is 192.168.0.1</br>
3. Router with 2 IPs for ports with PC1 and PC2 - 10.0.0.1 and 192.168.0.1 respectively, SubNetMask is 255.255.255.0</br>

# Simulations 1 - Same VNET
1. Send PING message from PC0 to PC1</br>
![](simulation_1.PNG)</br>
2. The message performs the following steps:</br>
	a. PC indentify the destination IP is on the same VNET with source, so it sends ARP message
	b. Switch broadcast the ARP message to all IPs on the same VNET
	c. PC1 respondes to ARP message</br>
	d. PING message is sent from PC0 to PC1</br>
	e. PC1 respondes to PING message</br>

# Simulations 2 - Different VNET - First Ping Fail
1. Send PING message from PC0 to PC2</br>
![](simulation_2.PNG)</br>
2. The message performs the following steps:</br>
	a. ARP is sent to indentify the DefaultGateway since the destination IP address doesn't belong to the current local network</br>
	b. PING message is forwarded to the Router</br>
	c. ARP message is send to indentify PC2</br>
	d. PING Failes due to time out</br>

# Simulations 3 - Different VNET - Second Ping Success
1. Send PING message from PC0 to PC2</br>
![](simulation_3.PNG)</br>
2. The message performs the following steps:</br>
	a. no need for ARP since ARP table of PC0 is already filled with Default GW Mac Address</br>
	![](simulation_4.PNG)</br>
	b. PING message is forwarded to the Router</br>
	c. no need for ARP since ARP table of the router is already filled with PC2 Mac Address</br>
	d. PING Success</br>
