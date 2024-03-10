R1>ena
R1#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#int g0/0
	
R1(config-if)#ip address 10.0.0.62 255.255.255.192
R1(config-if)#no shutdown

R1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

R1(config-if)#int g0/1
R1(config-if)#ip address 10.0.0.126 255.255.255.192
R1(config-if)#no shutdown

R1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

R1(config-if)#int g0/2
R1(config-if)#ip address 10.0.0.190 255.255.255.192
R1(config-if)#no shutdown

R1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

R1(config-if)#do sh ip int br
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     10.0.0.62       YES manual up                    up 
GigabitEthernet0/1     10.0.0.126      YES manual up                    up 
GigabitEthernet0/2     10.0.0.190      YES manual up                    up 
Vlan1                  unassigned      YES unset  administratively down down
R1(config-if)#











