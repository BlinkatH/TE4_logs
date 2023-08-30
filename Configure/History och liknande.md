
R1# **terminal history size 200**
R1# **show history** 
show ip int brief 
show interface g0/0/0 
show ip route 
show running-config 
show history 
terminal history size 200

R1# **show running-config | section line vty** line vty 0 4 password 7 110A1016141D login transport input all

R1# **show ip interface brief** Interface IP-Address OK? Method Status Protocol GigabitEthernet0/0/0 192.168.10.1 YES manual up up GigabitEthernet0/0/1 192.168.11.1 YES manual up up Serial0/1/0 209.165.200.225 YES manual up up Serial0/1/1 unassigned NO unset down down R1# R1# **show ip interface brief | include up** GigabitEthernet0/0/0 192.168.10.1 YES manual up up GigabitEthernet0/0/1 192.168.11.1 YES manual up up Serial0/1/0 209.165.200.225 YES manual up up

R1# **show ip interface brief** Interface IP-Address OK? Method Status Protocol GigabitEthernet0/0/0 192.168.10.1 YES manual up up GigabitEthernet0/0/1 192.168.11.1 YES manual up up Serial0/1/0 209.165.200.225 YES manual up up Serial0/1/1 unassigned NO unset down down R1# R1# **show ip interface brief | exclude unassigned** Interface IP-Address OK? Method Status Protocol GigabitEthernet0/0/0 192.168.10.1 YES manual up up GigabitEthernet0/0/1 192.168.11.1 YES manual up up Serial0/1/0 209.165.200.225 YES manual up up

```
R1# show ip route | begin Gateway
Gateway of last resort is not set
      192.168.10.0/24 is variably subnetted, 2 subnets, 2 masks
C        192.168.10.0/24 is directly connected, GigabitEthernet0/0/0
L        192.168.10.1/32 is directly connected, GigabitEthernet0/0/0
      192.168.11.0/24 is variably subnetted, 2 subnets, 2 masks
C        192.168.11.0/24 is directly connected, GigabitEthernet0/0/1
L        192.168.11.1/32 is directly connected, GigabitEthernet0/0/1
      209.165.200.0/24 is variably subnetted, 2 subnets, 2 masks
C        209.165.200.224/30 is directly connected, Serial0/1/0
L        209.165.200.225/32 is directly connected, Serial0/1/0
```