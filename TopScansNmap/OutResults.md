Output
SWITCH	EXAMPLE	DESCRIPTION
-oN	nmap 192.168.1.1 -oN normal.file	Normal output to the file normal.file
-oX	nmap 192.168.1.1 -oX xml.file	XML output to the file xml.file
-oG	nmap 192.168.1.1 -oG grep.file	Grepable output to the file grep.file
-oA	nmap 192.168.1.1 -oA results	Output in the three major formats at once
-oG -	nmap 192.168.1.1 -oG -	Grepable output to screen. -oN -, -oX - also usable
-append-output	nmap 192.168.1.1 -oN file.file -append-output	Append a scan to a previous scan file
-v	nmap 192.168.1.1 -v	Increase the verbosity level (use -vv or more for greater effect)
-d	nmap 192.168.1.1 -d	Increase debugging level (use -dd or more for greater effect)
-reason	nmap 192.168.1.1 -reason	Display the reason a port is in a particular state, same output as -vv
-open	nmap 192.168.1.1 -open	Only show open (or possibly open) ports
-packet-trace	nmap 192.168.1.1 -T4 -packet-trace	Show all packets sent and received
-iflist	nmap -iflist	Shows the host interfaces and routes
-resume	nmap -resume results.file	Resume a scan