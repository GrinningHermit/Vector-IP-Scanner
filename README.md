# Vector-IP-Scanner
An ip scanner for Anki's robot Vector to alleviate a changing ip address on a roaming DHCP server.

This program helps scanning for a Vector on a roaming DHCP server. When running for the first time, it will prompt for the ip address and serial. Once a correct ip is given, the MAC address is saved. Every next time the program is run, it will search the ip range of the last known working ip address. If it has changed, it will use Anki's configure.py to set the new ip. 

Notes:
- Make sure the file 'vector_ip_scanner.py' is in the same directory as Anki's SDK configure.py
- Only the first 50 ip's are scanned by default. Change the value of ip_range_max if more range or speed is needed.
- This program does not make things easier when changing to a different network, like changing from 192.168.0.XXX to 10.178.0.XXX Delete ipscanner_config.json if you do, then run this program again.
- Tested on Mac with SDK 0.5.0, untested on Linux and Windows.
- Some error messages can occur during scanning ('ping: sendto: No route to host'), they have no effect on the result.
