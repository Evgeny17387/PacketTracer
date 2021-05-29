# Network
![](network.PNG)</br>

# Description
Network Components</br>
1. 3 Router</br>
1. 3 Host PCs</br>

# Configuation
1. All Routers and Hosts are configured with the show IPs and respective Subnets</br>

# Simulations 1 - Can't send PING to other subnet
1. Send PING message from 10.0.0.2 to 192.168.0.2</br>
![](simulation_1.PNG)</br>
2. The message can't be sent since the router doesn't now how to reach the desired network</br>

# Simulations 1 - Can't send PING to other subnet
1. Send PING message from 10.0.0.2 to 192.168.0.2</br>
![](simulation_1.PNG)</br>
2. The message can't be sent since the router doesn't now how to reach the desired network</br>

# Simulations 2 - Setting OSPF
1. First we set the OSPF for bith Routers</br>
1. Send PING message from 10.0.0.2 to 192.168.0.2</br>
![](simulation_2.PNG)</br>
2. The message reaches the destination since Routers are build up dynamic routing to all networks, after OSPF </br>
![](simulation_3.PNG)</br>

# Config OSPF Commands
1. enable</br>
2. config terminal</br>
3. router ospf 10</br>
4. network 10.0.0.0 0.0.0.255 area 0(example)</br>
5. passive-interface f0/0 (example)</br>
6. exit</br>

# Usefull Commands
1. show ip route</br>
2. show ip protocols</br>
3. show ip ospf neighbor</br>
4. show ip ospf database</br>
5. show ip ospf database router</br>
