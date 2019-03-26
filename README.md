# RaspberryPi3BPlus_universitywifi
Had issues connecting to school wifi but was able to access guest wifi --fix
- This was on a raspberry pi 3 b plus newly setup on raspbian

In terminal type the following. You won't be able to edit the file unless you are in terminal using "sudo".
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
then copy and paste the following
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=US

network={
	ssid="[NAME OF SCHOOL WIFI"
	priority=1
	proto=RSN
	key_mgmt=WPA-EAP
	pairwise=CCMP
	auth_alg=OPEN
	eap=PEAP
	identity="[YOUR LOGIN ID]"
	password="[YOUR LOGIN PASSWORD]"
	phase1="peaplabel=0"
	phase2="auth=MSCHAPV2"
	}
```
save then close and you should notice your wifi is connected.

