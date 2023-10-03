S1(config)# no ip domain-lookup

Router# **configure terminal**
Enter configuration commands, one per line. End with CNTL/Z. 
Router(config)# **hostname R1** 
R1(config)# **enable secret class** 
R1(config)# **line console 0** 
R1(config-line)# **password cisco** 
R1(config-line)# **login** 
R1(config-line)# **exit** 
R1(config)# **line vty 0 4** 
R1(config-line)# **password cisco** 
R1(config-line)# **login** 
R1(config-line)# **exit** 
R1(config)# **service password-encryption** 


R1(config)# **banner motd #Authorized Access Only!#**

(Save!)
R1# **copy running-config startup-config**


R1(config)# **interface gigabitethernet 0/0/0** 
R1(config-if)# **ip address 192.168.10.1 255.255.255.0** 
R1(config-if)# **ipv6 address 2001:db8:acad:1::1/64** 
R1(config-if)# **description Link to LAN 1** 
R1(config-if)# **no shutdown** 
R1(config-if)# **exit** 
R1(config)# **interface gigabitethernet 0/0/1** 
R1(config-if)# **ip address 192.168.11.1 255.255.255.0** 
R1(config-if)# **ipv6 address 2001:db8:acad:2::1/64** 
R1(config-if)# **description Link to LAN 2** 
R1(config-if)# **no shutdown** 
R1(config-if)# **exit** 
R1(config)# **interface serial 0/0/0** 
R1(config-if)# **ip address 209.165.200.225 255.255.255.252** 
R1(config-if)# **ipv6 address 2001:db8:acad:3::225/64** 
R1(config-if)# **description Link to R2** 
R1(config-if)# **no shutdown** 
R1(config-if)# **exit** 


R1(config)# **interface loopback 0** 
R1(config-if)# **ip address 10.0.0.1 255.255.255.0** 
R1(config-if)# **exit**


rommon 2 > confreg 0x2142
rommon 2 > reset
Router# erase startup-config
Router# Reload

R1(config)#no ip domain-lookup (eller) no ip domain lookup

R1(config)# int g0/0.10
R1(config-subif)# encapsulation dot1Q 10
R1(config-subif)# ip address ___


Router(config)# **ip dhcp excluded-address** _low-address_ [_high-address_]

Router(config)# **ip dhcp pool** _pool-name_  
Router(dhcp-config)#

R1(config)# **ip dhcp excluded-address 192.168.10.1 192.168.10.9**
R1(config)# **ip dhcp excluded-address 192.168.10.254** 
R1(config)# **ip dhcp pool LAN-POOL-1** 
R1(dhcp-config)# **network 192.168.10.0 255.255.255.0** 
R1(dhcp-config)# **default-router 192.168.10.1** 
R1(dhcp-config)# **dns-server 192.168.11.5** 
R1(dhcp-config)# **domain-name example.com** 
R1(dhcp-config)# **end** 
R1#

R1(config)# interface ___
R1(config-if)# ip helper-address ___

<H3>Configure a Stateless DHCPv6 Server</H3>
R1(config)# **ipv6 unicast-routing**
R1(config)# **ipv6 dhcp pool IPV6-STATELESS** 
R1(config-dhcpv6)# **dns-server 2001:db8:acad:1::254** 
R1(config-dhcpv6)# **domain-name example.com** 
R1(config-dhcpv6)# **exit** 
R1(config)# **interface GigabitEthernet0/0/1** 
R1(config-if)# **description Link to LAN** 
R1(config-if)# **ipv6 address fe80::1 link-local** 
R1(config-if)# **ipv6 address 2001:db8:acad:1::1/64** 
R1(config-if)# **ipv6 nd other-config-flag** 
R1(config-if)# **ipv6 dhcp server IPV6-STATELESS** 
R1(config-if)# **no shut** 
R1(config-if)# **end**

-------------------------------------------------------------------------------
<H3>Configure a Stateless DHCPv6 Client</H3>
R3(config)# **ipv6 unicast-routing**
R3(config)# **interface g0/0/1** 
R3(config-if)# **ipv6 enable**
R3(config-if)# **ipv6 address autoconfig** 
R3(config-if)# **end**
R3# **show ipv6 interface brief**
R3# **show ipv6 dhcp interface g0/0/1**

-------------------------------------------------------------------------------
<H3>Configure a Stateful DHCPv6 Server</H3>
R1(config)# **ipv6 unicast-routing**
R1(config)# **ipv6 dhcp pool IPV6-STATEFUL**
R1(config-dhcpv6)# **address prefix 2001:db8:acad:1::/64** 
R1(config-dhcpv6)# **dns-server 2001:4860:4860::8888** 
R1(config-dhcpv6)# **domain-name example.com**
R1(config)# **interface GigabitEthernet0/0/1** 
R1(config-if)# **description Link to LAN** 
R1(config-if)# **ipv6 address fe80::1 link-local** 
R1(config-if)# **ipv6 address 2001:db8:acad:1::1/64** 
R1(config-if)# **ipv6 nd managed-config-flag** 
R1(config-if)# **ipv6 nd prefix default no-autoconfig** 
R1(config-if)# **ipv6 dhcp server IPV6-STATEFUL** 
R1(config-if)# **no shut** 
R1(config-if)# **end**
C:\PC1> **ipconfig /all**

-------------------------------------------------------------------------------
<H3>Configure a Stateful DHCPv6 Client</H3>
R3(config)# **ipv6 unicast-routing**
R3(config)# **interface g0/0/1** 
R3(config-if)# **ipv6 enable**
R3(config-if)# **ipv6 address dhcp** 
R3(config-if)# **end**
R3# **show ipv6 interface brief**
R3# **show ipv6 dhcp interface g0/0/1**

-------------------------------------------------------------------------------

R1(config-if)# **ipv6 nd other-config-flag** 
R1(config-if)# **end**

R1(config)# **int g0/0/1** 
R1(config-if)# **ipv6 nd managed-config-flag** 
R1(config-if)# **ipv6 nd prefix default no-autoconfig** 
R1(config-if)# **end**

R1(config)# **interface gigabitethernet 0/0/1** 
R1(config-if)# **ipv6 dhcp relay destination 2001:db8:acad:1::2 G0/0/0** 
R1(config-if)# **exit**

R1# **show ipv6 dhcp interface**
R3# **show ipv6 dhcp binding**
C:\PC1> **ipconfig /all**

R1(config)# ipv6 route (Ipv6 address) gigabitEthernet/FastEthernet







[[Switch configurations]]