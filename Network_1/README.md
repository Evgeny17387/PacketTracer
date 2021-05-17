# Network
![](Network.PNG)
# Description
Network Components</br>
1. 3 Host PCs</br>
2. Switch</br>
# Configuation
1. Host PCs PC1, PC2 and PC3 configured with IPs 10.0.0.1, 10.0.0.2 and 10.0.0.3 respectively, SubNetMask is 255.255.255.0</br>
2. Switch configured to 2 VLANs, for each simulation we change the mapping of the port-VLAN for each pc</br>
# Simulations 1 - PCs on the same VLAN
![](Simulation_1_test_1.PNG)
1. Configure Switch ports of all PCs be VLAN1
2. Run PING from PC1 to PC2, make sure it replieas</br>
3. In this scenarion ping message should arrive since the two PCs are on the same VLAN
4. Since ARP Table at PC1 is empty, it first sends ARP to find PC2, switch sends ARP message to all PCs since it doesn't understand IP address
5. Only PC2 replies
6. PC1 now sends PING message direcrtly to mac address of PC2
![](Simulation_1_test_2.PNG)
1. Sending PING again, doesn't trigger ARP since table is already filled with PC2 MAC address
# Simulations 2 - PCs on the same VLAN