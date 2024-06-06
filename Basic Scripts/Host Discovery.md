1. nmap <IP Address> -sL
#### List <IP Address> without scanning

2. nmap <IP Address> -sn       
#### Disable port scanning

3. nmap <IP Address> -pn 
#### Port scans only and no host discovery

4. nmap <IP Address> -PS22-25,80
#### TCP SYN discovery on specified ports

5. nmap <IP Address> -PU53
#### UDP discovery on specified port 

6. nmap <IP Address> PA22-25,80
#### TCP ACK discovery on specified port

7. nmap <IP Address> -PR   
#### ARP discovery within local network

8. nmap <IP Address> -n 
#### no DNS resolution

s