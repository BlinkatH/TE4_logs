
S1# **configure terminal**
S1(config)# **interface vlan 99**
S1(config-if)# **ip address 172.17.99.11 255.255.255.0**
S1(config-if)# **ipv6 address 2001:db8:acad:99::11/64**
S1(config-if)# **no shutdown**
S1(config-if)# **end**
S1# **copy running-config startup-config**


S1# **configure terminal**
S1(config)# **ip default-gateway 172.17.99.1**
S1(config)# **end**
S1# **copy running-config startup-config**


S1# **configure terminal**
S1(config)# **interface FastEthernet 0/1**
S1(config-if)# **duplex full**
S1(config-if)# **speed 100**
S1(config-if)# **end**
S1# **copy running-config startup-config**

S1(config-if)# **mdix auto**


S1# **show interfaces** [_interface-id_]
S1# **show startup-config**
S1# **show running-config**
S1# **show flash**
S1# **show version**
S1# **show history**
S1# **show ip interface** [_interface-id_]<br><br>OR<br><br>S1# **show ipv6 interface** [_interface-id_]
S1# **show mac-address-table**<br><br>OR<br><br>S1# **show mac address-table**


S1#configure terminal
S1(config)#line vty 0 15
S1(config-line)#password ___
S1(config-line)#login
S1(config-line)#exit

S1# **show ip ssh**
S1(config)# **ip domain-name** [domain-name]
S1(config)# **crypto key generate rsa** [ex. 1024]
S1(config)# **username** [username] **secret** [secret]
S1(config)# **line vty 0 15** 
S1(config-line)# **transport input ssh** 
S1(config-line)# **login local** 
S1(config-line)# **exit**
S1(config)# **ip ssh version 2**


