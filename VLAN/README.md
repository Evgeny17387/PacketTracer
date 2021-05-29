# Network 1
![](network_1.PNG)</br>

## Description
Network Components</br>
1. 2 Switches</br>
2. 4 Host PCs</br>

## Configuation
1. All Host PCs are configured with the show IPs and respective Subnets</br>
2. Subnets 10.0.0.0 and 192.168.0.0 are indicated as VLANs 10 and 192 respectively
3. Then interface between 2 Switches configures as Trunk enablined for both virtual networks - 10.0.0.0 and 192.168.0.0</br>

## Simulation - Send ping through VLAN Trunk Link
1. Send PING message from 10.0.0.1 to 10.0.0.2</br>
![](simulation_1_1.PNG)</br>
2. The message goes trough the Trunk interface between 2 switches</br>
3. When the frames passes throgh the Trunk interface, it looks like:
![](simulation_1_2.PNG)</br>
3. Where the Type is 0x8100 indicating that this is Tag frame, and the VLAN is indicated as 0xa which is the VLAN number of the appropriate VLAN (10)

# Network 2
![](network_2.PNG)</br>

## Description
Network Components</br>
1. 1 Router</br>
2. 1 Switch</br>
3. 2 Host PCs</br>

## Configuation
1. All Host PCs are configured with the show IPs and respective Subnets</br>
2. Subnets 10.0.0.0 and 192.168.0.0 are indicated as VLANs 10 and 192 respectively
3. Then interface between the Router and the Switche configures as Trunk enablined for both virtual networks - 10.0.0.0 and 192.168.0.0</br>

## Simulation
1. Send PING message from 10.0.0.2 to 192.168.0.2</br>
![](simulation_2_1.PNG)</br>
2. The message goes trough the Trunk interface between the Switch and the Router and than goes back to the Switch</br>
3. When it leaves the Swtich it has th VLAN of 10</br>
![](simulation_2_2.PNG)</br>
3. When it enters back to the Swtich it has th VLAN of 192</br>
![](simulation_2_3.PNG)</br>

# Config SubInterfaces for f0/0
1. int f0/0.10</br>
2. encapsulation dot1q 10</br>
3. ip address 10.0.0.1 255.255.255.0</br>

# Usefull Commands
1. copy run start</br>
2. show ip route</br>
3. show ip int bri</br>
