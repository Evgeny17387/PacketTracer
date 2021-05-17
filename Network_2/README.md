# Network
![](network.PNG)</br>
# Description
Network Components</br>
1. 2 Host PCs</br>
2. Router</br>
# Configuation
1. Host PC1 and PC2 configured with IPs 10.0.0.2 and 192.168.0.2 respectively, SubNetMask is 255.255.255.0</br>
2. Router with 2 IPs for ports with PC1 and PC2 - 10.0.0.1 and 192.168.0.1 respectively, SubNetMask is 255.255.255.0</br>
3. Host PC1 and PC2 configured with DefaultGateway IPs 10.0.0.1 and 192.168.0.1 respectively</br>
# Simulations
1. Send PING message from PC1 to PC2</br>
![](simulation_before_static_routing.PNG)</br>
2. Sending PING message shouldn't work since ARP message won't be sent to another subnet</br>
3. Adding static routing for both directions helps solving this issue</br>
![](simulation_static_routing.PNG)</br>
![](simulation_after_static_routing.PNG)</br>
4. The message performs the following steps:</br>
	a. ARP is sent to indentify the DefaultGateway since the destination IP address doesn't belong to the current local network</br>
	b. PING message is forwarded to the Router</br>
	c. ARP message is send to indentify PC2</br>
	d. PING message is forwarded to the PC</br>
	e. PING response doesn all the way back to PC1</br>
