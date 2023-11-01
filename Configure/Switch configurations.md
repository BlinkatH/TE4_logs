
R1(config)# no ip domain-lookup

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


S1#erase startup-config
S1#delete vlan.dat

S2(config)# interface ___
S2(config-if)# switchport mode access
S2(config-if)# switchport access vlan ___

S3(config)# interface ___
S3(config-if)# mls qos trust cos
S3(config-if)# switchport voice vlan ___


S1(config)# interface range g0/1 - 2 (Eller bara porten som ska användas)
S1(config-if)# switchport mode trunk
S1(config-if)# switchport trunk native vlan ___

(Exempel till hur man stänger ner alla onödiga ports)
S1(config)# **interface range f0/2-5, f0/7-24, g0/1-2**
S1(config-if-range)# **shutdown**
S1(config-if-range)# **exit**

S1# **clock set 15:30:00 19 August 2021**

switch: SWITCH_IGNORE_STARTUP_CFG=1
switch: boot flash:packages.conf


S1(config)# **interface range FastEthernet 0/1 - 2**
S1(config-if-range)# **channel-group 1 mode active** 
S1(config-if-range)# **exit** 
S1(config)# **interface port-channel 1** 
S1(config-if)# **switchport mode trunk** 
S1(config-if)# **switchport trunk allowed vlan 1,2,20**


<H3>Port Security</H3>
S1(config)# **interface f0/1**
S1(config-if)# **switchport mode access**
S1(config-if)# **switchport port-security**
S1(config-if)# **end**

----------------------------------------------------------------------------

<H3>Limit and Learn MAC Addresses</H3>

1. **Manually Configured**
 Switch(config-if)# **switchport port-security mac-address** _mac-address_

2. **Dynamically Learned**
 Switch(config-if)# **switchport port-security

3. **Dynamically Learned – Sticky**
 Switch(config-if)# **switchport port-security mac-address sticky**

-------------------------------------------------------------------------------

<H3>Port Security Aging</H3>

Switch(config-if)# **switchport port-security aging** { **static** | **time** _time_ | **type** {**absolute** | **inactivity**}}

exempel:
S1(config-if)# **switchport port-security aging time 10** 
S1(config-if)# **switchport port-security aging type inactivity**

![[Pasted image 20231003095627.png]]

-------------------------------------------------------------------------------

<H3>Port Security Violation Modes</H3>

Switch(config-if)# **switchport port-security violation** { **protect** | **restrict** | **shutdown**}

![[Pasted image 20231003100343.png]]

-------------------------------------------------------------------------------

<H3>DAI Configuration</H3>
S1(config)# **ip dhcp snooping**
S1(config)# **ip dhcp snooping vlan 10**
S1(config)# **ip arp inspection vlan 10**
S1(config)# **interface __**
S1(config-if)# **ip dhcp snooping trust**
S1(config-if)# **ip arp inspection trust**


S1(config)# **ip arp inspection validate ?**
  ip       Validate IP addresses
  src-mac  Validate source MAC address
