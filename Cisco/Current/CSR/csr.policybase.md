to-az-pb-vpn01#sh runn
Building configuration...

Current configuration : 4278 bytes
!
! Last configuration change at 06:50:39 UTC Sun Mar 22 2020 by i500994
!
version 16.9
service timestamps debug datetime msec
service timestamps log datetime msec
platform qfp utilization monitor load 80
no platform punt-keepalive disable-kernel-core
platform console virtual
!
hostname to-az-pb-vpn01
!
boot-start-marker
boot-end-marker
!
!
logging persistent size 1000000 filesize 8192 immediate
!
aaa new-model
!
!
aaa authentication login default local
aaa authorization exec default local none
!
!
!
!
!
aaa session-id common
!
!
!
!
!
!
!
ip domain name to-az-pb-vpn01.cloudapp.net
ip admission watch-list expiry-time 0
!
!
!
!
!
!
!
!
!
!
subscriber templating
!
!
!
!
!
multilink bundle-name authenticated
!
!
!
!
!
crypto pki trustpoint TP-self-signed-294591619
 enrollment selfsigned
 subject-name cn=IOS-Self-Signed-Certificate-294591619
 revocation-check none
 rsakeypair TP-self-signed-294591619
!
!
crypto pki certificate chain TP-self-signed-294591619
 certificate self-signed 01
  3082032E 30820216 A0030201 02020101 300D0609 2A864886 F70D0101 05050030
  30312E30 2C060355 04031325 494F532D 53656C66 2D536967 6E65642D 43657274
  69666963 6174652D 32393435 39313631 39301E17 0D323030 33323230 36343034
  385A170D 33303031 30313030 30303030 5A303031 2E302C06 03550403 1325494F
  532D5365 6C662D53 69676E65 642D4365 72746966 69636174 652D3239 34353931
  36313930 82012230 0D06092A 864886F7 0D010101 05000382 010F0030 82010A02
  82010100 9CDA91F5 D81114C3 9DC018CD E0ACDB41 C44B63A7 98EE3692 A127E946
  BEF8F59B B3A76145 9242172A B8DBFE0F 5AF71C33 D7254DE4 2B5132D2 89C24060
  1A7BD98B DBDBDF8A 67E63C92 32CEFAA2 091128F8 35BFE4A9 2DE5C9B9 894F62BD
  BDDD54C3 88DF802F 036F75C3 64B98DE4 017FAB61 C36924CA CAE72B78 5F40C8F1
  A7165BE6 EC1E7517 BE5D0FE6 B539C206 23D7622E 31CA3565 AC55D51F 9AB3CD0E
  62C2A441 5AB9C466 5B3BF957 56E09180 A044E898 4237444D 435F3DE6 079A9AE6
  798E8F00 A68A86D9 2C04AD16 D426827F 8C86D44E A0337FD9 2BAC027C 46494387
  5F25F022 A7621AD2 2E2DE4C8 39DEF648 C323DBC6 5814C815 C226D361 2CC9D4FC
  DE17015F 02030100 01A35330 51300F06 03551D13 0101FF04 05300301 01FF301F
  0603551D 23041830 16801404 D0AFA298 54FC4B81 84A0543E 6C9FC225 CD13CF30
  1D060355 1D0E0416 041404D0 AFA29854 FC4B8184 A0543E6C 9FC225CD 13CF300D
  06092A86 4886F70D 01010505 00038201 010015BA 9F11FDE4 C8F5A7A0 533E8D11
  A03C781B 873248D5 FAB3134C 0B680E5B 49021972 E024CB24 5160825D CDA3FFDD
  820498DA E7890EF6 9B4141C0 E9721D22 9633629E 8067CFD0 9724C72D 015A307C
  1C54C49B C3E1BFAD 7CDA290B AC31558C F6216521 DF6AF6A4 8AEBAAC5 97C7467B
  532FBC6C 285D5E9B F9E72116 B4518BA0 15F1ACBA 71E7DA46 B05F58B6 450CBD88
  191AE2F5 C9317968 3E606C45 DC4E7653 9460444E BF3351A9 B751B3B8 CEF4A6DA
  8280818E 26E224DF FE57EA9D 87008CE5 7CD1C0A9 9C5FDBD7 560D85E0 04E19FD2
  0E2B5CBB B44C950F B54C4FFF 22952D78 5856ED47 C018E447 3097E55E F7000EA8
  443DE3F8 3B796834 ACCA7EE6 1991D158 7306
        quit
!
!
!
!
!
!
!
!
license udi pid CSR1000V sn 9ONALFI5UYV
no license smart enable
diagnostic bootup level minimal
!
spanning-tree extend system-id
!
!
!
username i500994 privilege 15 secret 5 $1$Wi5I$ppttQ/LhX5YiS71SUQKMn0
!
redundancy
!
!
!
!
!
!
!
crypto keyring VPN
  pre-shared-key address 40.85.191.161 key 123456
!
!
!
!
!
!
crypto isakmp policy 10
 encr aes 256
 authentication pre-share
 group 2
!
!
crypto ipsec transform-set ESP-AES256-SHA1 esp-aes 256 esp-sha-hmac
 mode tunnel
!
!
!
crypto map Policy_VPN 10 ipsec-isakmp
 set peer 40.85.191.161
 set transform-set ESP-AES256-SHA1
 set reverse-route distance 10
 match address GCP_AZ
 reverse-route static
!
!
!
!
!
!
!
!
interface Loopback101
 ip address 192.168.101.1 255.255.255.0
!
interface GigabitEthernet1
 ip address dhcp
 negotiation auto
 no mop enabled
 no mop sysid
 crypto map Policy_VPN
!
ip forward-protocol nd
ip http server
ip http authentication local
ip http secure-server
!
ip ssh rsa keypair-name sshkeys
ip ssh pubkey-chain
  username i500994
   key-hash ssh-rsa 7763441598D7DDE7191049C82A3A61EF i500994@C02XD376JGH5
ip scp server enable
!
!
ip access-list extended GCP_AZ
 permit ip 192.168.101.0 0.0.0.255 10.2.0.0 0.0.0.255
!
!
!
!
!
!
control-plane
!
!
!
!
!
!
line con 0
 stopbits 1
line aux 0
 stopbits 1
line vty 0 4
 transport input ssh
!
!
!
!
!
!
end

