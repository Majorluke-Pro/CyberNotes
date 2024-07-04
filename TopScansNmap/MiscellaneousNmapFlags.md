Miscellaneous Nmap Flags
SWITCH	EXAMPLE	DESCRIPTION
-6	nmap -6 2607:f0d0:1002:51::4	Enable IPv6 scanning
-h	nmap -h	nmap help screen
Other Useful Nmap Commands
COMMAND	DESCRIPTION
nmap -iR 10 -PS22-25,80,113,1050,35000 -v -sn	Discovery only on ports x, no port scan
nmap 192.168.1.1-1/24 -PR -sn -vv	Arp discovery only on local network, no port scan
nmap -iR 10 -sn -traceroute	Traceroute to random targets, no port scan
nmap 192.168.1.1-50 -sL -dns-server 192.168.1.1	Query the Internal DNS for hosts, list targets only
nmap 192.168.1.1 --packet-trace	Show the details of the packets that are sent and received during a scan and capture the traffic.