sa-vpn-softether
================

[![Build Status](https://travis-ci.org/softasap/sa-vpn-softether.svg?branch=master)](https://travis-ci.org/softasap/sa-vpn-softether)


Example of use: check box-example

Configuration:
```YAML

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
