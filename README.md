sa-vpn-softether
================

[![Build Status](https://travis-ci.org/softasap/sa-vpn-softether.svg?branch=master)](https://travis-ci.org/softasap/sa-vpn-softether)


Example of use: check box-example

Configuration supported by role:
```YAML

#SecureNAT is a combination of Virtual NAT and DHCP Server function. You can enable SecureNAT using the command below:
softether_option_securenat: false

softether_location: /opt
softether_home: "{{softether_location}}/vpnserver"
softether_lang: en
softether_fqdn: "{{ansible_host}}"


# ============== IPSEC ===================
softether_option_ipsec: true
softether_ipsec_l2tp: yes
softether_ipsec_l2tpraw: yes
softether_ipsec_etherip: no
softether_ipsec_presharedkey: "[1KH;+r-X#cvhpv7Y6=#;[{u"
# /============== IPSEC ===================


# ============== OPENVPN ===================
softether_option_openvpn: true
softether_openvpn_port: 1194
softether_openvpn_config: "{{softether_home}}/generated/openvpn_config.zip"
# /============== OPENVPN ===================



# ============== Bridge ===================
softether_bridge_device: soft
softether_bridge_tap: no
# ============== /Bridge ===================


# ============== Users ===================
softether_vpn_users:
  - {
      name: "vpn",
      password: "verysecurepasswordyeah"
    }
# ============== /Users ===================

softether_sysctl_conf_lines:
  - {
      name: 'net.ipv4.ip_forward',
      value: '1'
    }



```

Simple:

```YAML


     - {
         role: "sa-vpn-softether"
       }

```


Advanced:

```YAML


     - {
         role: "sa-vpn-softether"
       }

```


Connecting to OpenVPN from client box
=====================================

If you executed last step of play, you have now cer file for ipsec + zip with openvpn configuration.

Once unpacked, ensure you have GUI ready for openvpn. If menu "Import saved vpn configuration" missing, proceed with


```bash
sudo apt install network-manager-openvpn network-manager-openvpn-gnome network-manager-pptp network-manager-vpnc
```

After logout/login or reboot you will have menu option "Import saved vpn configuration".


Connecting to OpenVPN full story
================================




Copyright and license
---------------------

Copyright - Vyacheslav Voronenko

Code licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) or the [MIT License] (http://opensource.org/licenses/MIT).

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)
