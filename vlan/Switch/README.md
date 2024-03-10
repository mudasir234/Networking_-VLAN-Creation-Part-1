SW1>en
SW1#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
SW1(config)#int range g01,f3/1,f4,1
                         ^
% Invalid input detected at '^' marker.
	
SW1(config)#int range g0/1, f3,1, f4,1
                              ^
% Invalid input detected at '^' marker.
	
SW1(config)#int range g0/1, f3/1, f4/1
SW1(config-if-range)#switchport mode access
SW1(config-if-range)#switchport access Vlan 10
% Access VLAN does not exist. Creating vlan 10
SW1(config-if-range)#int range g1/1, f5/1, f6/1
SW1(config-if-range)#switchport mode access
SW1(config-if-range)#switchport access Vlan 20
% Access VLAN does not exist. Creating vlan 20
SW1(config-if-range)#int range g2/1, f7/1, f8/1
SW1(config-if-range)#switchport mode access
SW1(config-if-range)#switchport access Vlan 30
% Access VLAN does not exist. Creating vlan 30
SW1(config-if-range)#do sh ip int br
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/1     unassigned      YES manual up                    up 
GigabitEthernet1/1     unassigned      YES manual up                    up 
GigabitEthernet2/1     unassigned      YES manual up                    up 
FastEthernet3/1        unassigned      YES manual up                    up 
FastEthernet4/1        unassigned      YES manual up                    up 
FastEthernet5/1        unassigned      YES manual up                    up 
FastEthernet6/1        unassigned      YES manual up                    up 
FastEthernet7/1        unassigned      YES manual up                    up 
FastEthernet8/1        unassigned      YES manual up                    up 
FastEthernet9/1        unassigned      YES manual down                  down 
Vlan1                  unassigned      YES manual administratively down down
SW1(config-if-range)#do sh vlan

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa9/1
10   VLAN0010                         active    Gig0/1, Fa3/1, Fa4/1
20   VLAN0020                         active    Gig1/1, Fa5/1, Fa6/1
30   VLAN0030                         active    Gig2/1, Fa7/1, Fa8/1
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    

VLAN Type  SAID       MTU   Parent RingNo BridgeNo Stp  BrdgMode Trans1 Trans2
---- ----- ---------- ----- ------ ------ -------- ---- -------- ------ ------
1    enet  100001     1500  -      -      -        -    -        0      0
10   enet  100010     1500  -      -      -        -    -        0      0
20   enet  100020     1500  -      -      -        -    -        0      0
30   enet  100030     1500  -      -      -        -    -        0      0
1002 fddi  101002     1500  -      -      -        -    -        0      0   
1003 tr    101003     1500  -      -      -        -    -        0      0   
1004 fdnet 101004     1500  -      -      -        ieee -        0      0   
1005 trnet 101005     1500  -      -      -        ibm  -        0      0   

VLAN Type  SAID       MTU   Parent RingNo BridgeNo Stp  BrdgMode Trans1 Trans2
---- ----- ---------- ----- ------ ------ -------- ---- -------- ------ ------

Remote SPAN VLANs
------------------------------------------------------------------------------

Primary Secondary Type              Ports
------- --------- ----------------- ------------------------------------------
SW1(config-if-range)#
SW1(config-if-range)#vlan 10
SW1(config-vlan)#name ENGINEERING
SW1(config-vlan)#vlan 20
SW1(config-vlan)#name HR
SW1(config-vlan)#vlan 30
SW1(config-vlan)#name sales
SW1(config-vlan)#do shvaln
Translating "shvaln"...domain server (255.255.255.255)
% Unknown command or computer name, or unable to find computer address

SW1(config-vlan)#do sh vlan br

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa9/1
10   ENGINEERING                      active    Gig0/1, Fa3/1, Fa4/1
20   HR                               active    Gig1/1, Fa5/1, Fa6/1
30   sales                            active    Gig2/1, Fa7/1, Fa8/1
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    
SW1(config-vlan)#



