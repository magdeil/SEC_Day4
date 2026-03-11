!Switch/Router
config t
ip domain-name rivanit.com
username admin privilege 15 secret pass
username ~~~~~ privilege 15 secret pass
 crypto key generate rsa modulus 2048 
ip ssh version 2
line vty 0 14
login local
transport input all
end


!@NetOps
nmcli connection add \
type ethernet \
con-name VMNET2 \
ifname ens192 \
ipv4.method manual \
ipv4.addresses 192.168.102.6/24 \
autoconnect yes

nmcli connection up VMNET2


nmcli connection add \
type ethernet \
con-name VMNET3 \
ifname ens224 \
ipv4.method manual \
ipv4.addresses 11.11.11.100/27 \
autoconnect yes

nmcli connection up VMNET3


nmcli connection add \
type ethernet \
con-name BRIDGED \
ifname ens256 \
ipv4.method manual \
ipv4.addresses 10.#$34T#.1.6/24 \
autoconnect yes

nmcli connection up BRIDGED


ip route add 10.0.0.0/8 via 10.#$34T#.1.4 dev ens256
ip route add 200.0.0.0/24 via 10.#$34T#.1.4 dev ens256
ip route add 0.0.0.0/0 via 11.11.11.113 dev ens224
