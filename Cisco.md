# Cisco packet tracer

## Opbouwen eigen Netwerk opstelling

Binnen deze opstelling wil ik mijn eigen netwerk
instellen.

* Switch van router 5 Moet voorzien worden van 128 netwerken en 16 netwerken voor medenwerkers afgeschermd van netwerk.
* Swich 6 moet 32 netwerken hebben acces point voor werknemers hun toestellen.
* Routers moeten wachtwoord hebben Cisco123
* Alle computers moeten een ipv4 address hebben.
* Routers moeten hun eigen IPV6 hebben & IPV4

* Username each `Admin` secret `Cisco123`

## Workspace

CLI Router 5 Bydgoszcz
```
$en
$conf t
$int ser 0/1/0
$no shutdown
$exit
Router5(config)#int g 0/0.20
Router5(config-subif)#en
Router5(config-subif)#encapsulation dot1Q  20
Router5(config-subif)#ip address 192.168.1.130 255.255.255.240 (16 addressen)
Router5(config-subif)#ex
Router5(config)#int g 0/0.1
Router5(config-subif)#encapsulation dot1Q 1 Native 
Router5(config-subif)#ip address 192.168.1.1 255.255.255.128 (32 addressen)
Router5(config-subif)#no shutdown
Router5(config-subif)#ex
Router5(config-subif)#int g 0/0
Router5(config-subif)#no shutdown
```
CLI Switch 0 Bydgoszcz
```  
Switch>en
Switch#conf t
Switch(config)#vlan 20
Switch(config-vlan)#name AP_VLAN
Switch(config-vlan)#ex
Switch(config)#int f 0/5
Switch(config-if)#switchport mode acces
Switch(config-if)#switchport access  vlan 20
Switch(config-if)#ex
Switch(config)#int g 0/1
Switch(config-if)#switchport mode trunk 
Switch(config-if)#ex
Switch(config)#int range f0/1 - 4
Switch(config-if-range)#switchport mode acces
Switch(config-if-range)#switchport access vlan 1
Switch(config-if-range)#ex
Switch(config)#int range f0/6 - 10
Switch(config-if-range)#switchport mode acces
Switch(config-if-range)#switchport access vlan 1
Switch(config-if-range)#ex
Switch(config-vlan)#int vlan 1
Switch(config-if)#ip address 192.168.1.2 255.255.255.128
Switch(config-if)#no shutdown
```
CLI Switch 2 Bydgoszcz
```
Switch#conf t
Switch(config)#int vlan 1
Switch(config-if)#ip address 192.168.1.7 255.255.255.128
Switch(config-if)#no shutdown
Switch(config-if)#ex

```

  ### Toestellen lijst Bydgoszcz Biuro pracy
  | Device | IPV4         |
  |--------|--------------|
  | Bydgoszcz | Pracownik |
  |  PC0   |  192.168.1.3 |
  |  PC1   |  192.168.1.4 |
  |  PC2   |  192.168.1.5 |
  |  PC3   |  192.168.1.6 |
  |        | IT-Bydgoszcz |
  |  PC5   |  192.168.1.10 |
  |  PC6   |  192.168.1.8 |
  |  PC7   |  192.168.1.9 |
  | Switch0 | 192.168.1.2 |
  | Swtich2 | 192.168.1.7 |
  | Roouter5 | 192.168.1.1 |
  | Access |  192.168.1.130 |

### Security
* Router cli *
```
Router5>en
Router5#conf t
Router5(config)#ip domain-name Addeco
Router5(config)#line console 0
Router5(config-line)#password Cisco123
Router5(config-line)#login
Router5(config-line)#exit
Router5(config)#enable secret Cisco123
Router5(config)#line vty 0 4
Router5(config-line)#transport input ssh
Router5(config-line)#login local 
Router5(config-line)#exit
Router5(config)#username Admin secret Cisco123
Router5(config-line)#line vty 0 4 
Router5(config-line)#login local
Router5(config-line)#exit
Router5(config)#crypto key gen
Router5(config)#crypto key generate rsa
Router5(config-line)#exit
```
* Switch cli *
```

Switch>en
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#line co
Switch(config)#line console 0
Switch(config-line)#password Cisco123
Switch(config-line)#login
Switch(config-line)#exit
Switch(config)#enable secret Cisco123
Switch(config)#line vty 0 4
Switch(config-line)#tra
Switch(config-line)#transport in
Switch(config-line)#transport input ssh
Switch(config-line)#login local
Switch(config-line)#ex
% Ambiguous command: "ex"
Switch(config-line)#exit
Switch(config)#username Admin secret Cisco123
Switch0(config)#ip domain-name Addeco
Switch0(config)#crypto key generate rsa

```

## Workspace IT-Service

CLI Router 6
```
Router>en
Router#conf t
Router(config)#int ser 0/1/0
Router(config-if)#no shutdown
Router(config)#int g 0/0
Router(config-if)#ip address 192.168.1.148 255.255.255.224
Router(config-if)#no shutdown
Router(config-if)#ex
```
CLI Switch1
```
Switch>en
Switch#conf t
Switch(config-vlan)#int vlan 1
Switch(config-if)#ip  address 192.168.1.149 255.255.255.224
Switch(config-if)#no shutdown
Switch(config-if)#
```
| Device| IPV4 |
|-|-|
| Laptop 0 | 192.168.1.150 |
| PC4 | 192.168.1.151 |
|Server 0 | 192.168.1.152 |
| Access | 192.168.1.153 |
