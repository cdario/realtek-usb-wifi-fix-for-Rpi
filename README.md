### Basic commands

\#detect the device
sudo lsusb 

\#look for your wifi network, assuming wlan0 interface
sudo iwlist wlan0 scan

### Working file setup

> cat /etc/network/interfaces

```
auto lo
 
iface lo inet loopback
iface eth0 inet dhcp
 
allow-hotplug wlan0
auto wlan0
iface wlan0 inet dhcp
wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf
``` 

> cat /etc/wpa_supplicant/wpa_supplicant.conf

```
network={
ssid="SSID-GOES-HERE"
proto=RSN
key_mgmt=WPA-PSK
pairwise=CCMP TKIP
group=CCMP TKIP
psk="WIFI-PASSWORD-GOES-HERE"
}
``` 

source: 
**http://pingbin.com/2012/12/setup-wifi-raspberry-pi/**

## Fix for  RTL8188CUS based wifi adapters

###Script version 
- 8192cu-20120701

source 
**http://www.raspberrypi.org/forums/viewtopic.php?f=26&t=6256&p=128069**