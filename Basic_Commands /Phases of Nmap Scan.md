1. Script pre-scanning
( Script pre-scanning uses a collection of special purpose scripts to gain more information about remote systems)

Examples: 
 - dhcp-discover
 - broadcast-dns-service-discovery


 2. Target Enumeration
 ( Target Enumeration researches the host of specifiers provided by the user, which may be a combination of host DNS names, IP Addresses, CIDR network notations, and more.)

 Examples: 
  - nmap -iR <IP Address>
  - nmap -sL <IP Address>

  3. Host Discovery (Ping Scanning)
  (  Network scans usually begin by discovering which targets on the network are online and thus worth deeper investigation. This process is called host discovery or ping scanning. Nmap offers many host discovery techniques, ranging from quick ARP requests to elaborate combinations of TCP, ICMP, and other types of probes)

  Examples: 
  - nmap -Pn <IP Address>
  - nmap -sn <IP Address>
  - nmap -n <IP Address>

  4. Reverse DNS Resolution
  ( Once Nmap has determined which hosts to scan, it looks up the reverse-DNS names of all hosts found online by the ping scan. Sometimes a host's name provides clues to its function, and names make reports more readable than providing only IP numbers)

  Examples: 
  - nmap -n <IP Address>

  5. Port Scanning
  ( This is Nmap's core operation. Probes are sent, and the responses (or non-responses) to those probes are used to classify remote ports into states such as open, closed, or filtered. That brief description doesn't begin to encompass Nmap's many scan types, configurability of scans, and algorithms for improving speed and accuracy)

  Examples: 
  - nmap -sn <IP Address>

  6. Version Detection
  ( If any ports are found to be open, Nmap may be able to determine what server software is running on the remote system. It does this by sending a variety of probes to the open ports and matching any responses against a database of thousands of more than 6,500 known service signatures)

  Examples: 
  - nmpa -sV <IP Address>

  7. OS Dection
  ( If requested with the -O option, Nmap proceeds to OS detection. Different operating systems implement network standards in subtly different ways. By measuring these differences it is often possible to determine the operating system running on a remote host)

  Examples: 
  - nmap -o <IP Address>

  8. Traceroute
  ( Nmap contains an optimized traceroute implementation, enabled by the --traceroute option. It can find the network routes to many hosts in parallel, using the best available probe packets as determined by Nmap's previous discovery phases. Traceroute usually involves another round of reverse-DNS resolution for the intermediate hosts)

  Example: 
  - sudo nmap <IP Address> --traceroute

  9. Script Scanning
  ( Most Nmap Scripting Engine (NSE) scripts run during this main script scanning phase, rather than the prescan and postscan phases. NSE is powered by the Lua programming language and a standard library designed for network information gathering. Scripts running during this phase generally run once for each target host and port number that they interact with)

  Examples: 
  - sudo nmap <IP Address> --script
  - sudo nmap <IP Address> -sC 

  


