sudo openvpn --config vpnbook-us1-tcp443.ovpn --script-security 2 --up /etc/openvpn/update-resolv-conf.sh --down /etc/openvpn/update-resolv-conf.sh

Begin Here:
Open http://www.vpnbook.com/howto
Then download the attached zip and replace the file /etc/resolv.conf with the one from the zip.
Then download any zip from openvpn tab of http://www.vpnbook.com/
Extract the zip and open a terminal in it and paste the command on top of me after replacing "us1" with the one matching from the downloaded zip.
Hoo yeah!!


No need to read this!
OpenVPN Update resolvconf
-------------------------

### Description

This is a script to update your /etc/resolv.conf with DNS settings that
come from the received push dhcp-options. Since network management is out
of OpenVPN client scope, this script adds and removes the provided from
those settings.

This script was found on the [OpenVPN page of the Archlinux Wiki](https://wiki.archlinux.org/index.php/Openvpn#DNS)

### Usage

Install [openresolv](http://roy.marples.name/projects/openresolv)

Place the script in ``/etc/openvpn/update-resolv-conf.sh`` or anywhere the
OpenVPN client can acess.

Add the following lines to your client configuration:
```
# This updates the resolvconf with dns settings
script-security 2
up /etc/openvpn/update-resolv-conf.sh
down /etc/openvpn/update-resolv-conf.sh
```

Just start your openvpn client with the command you used to do.

Alternatively, if you don't want to edit your client configuration, you can add the following options to your openvpn command:
```
--script-security 2 --up /etc/openvpn/update-resolv-conf.sh --down /etc/openvpn/update-resolv-conf.sh
```

### Support

For bugs and another questions open a ticket in the [Isssues Page](https://github.com/masterkorp/openvpn-update-resolv-conf/issues).

You can find me on irc.freenode.org and in last case mail me through the email that is on my [Github Profile](https://github.com/masterkorp)

### License

Licenced under GNU GPL.

### Credits

2016 - WGH Added modified script to support systemd-networkd

2014 - Alfredo Palhares <masterkorp@masterkorp.net>

2013 - colin@daedrum.net Fixed intet name

2006 - chlauber@bnc.ch
