#!/bin/bash
# Purpose: Config ubuntu DHCP server
# https://ubuntu.com/server/docs/network-dhcp
# Author: Jose Maria Madronal GPL v2.0+
# ------------------------------------------
#
#
# declare STRING variable
STRING="Scripts examples"
f_dchpd_conf="https://raw.githubusercontent.com/AlexGomila/dhcp/53bff192c10beb2880d8a809eea60b419971a9aa/dhcp_config"
#print variable on a screen
echo $STRING

#Install DHCP
apt-get install isc-dhcp-server
rm  /etc/dhcp/dhcpd.conf
# download githup configuration file
wget $f_dchpd_conf

# copy configuration file to etc directory
mv dhcpd.conf /etc/dhcp

systemctl restart isc-dhcp-server
