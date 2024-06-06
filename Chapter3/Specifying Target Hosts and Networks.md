1. Nmap accepts multiple host specifications on the command line, and they don't need to be the same type. The command nmap scanme.nmap.org 192.168.0.0/8 10.0.0,1,3-7.- does what you would expect.

2. Input From List (-iL)
Passing a huge list of hosts is often awkward on the command line, yet it is a common need. For example, your DHCP server might export a list of 10,000 current leases that you wish to scan. Or maybe you want to scan all IP addresses except for those ones to locate hosts using unauthorized static IP addresses. Simply generate the list of hosts to scan and pass that filename to Nmap as an argument to the -iL option. Entries can be in any of the formats accepted by Nmap on the command line (IP address, hostname, CIDR, IPv6, or octet ranges). Each entry must be separated by one or more spaces, tabs, or newlines. You can specify a hyphen (-) as the filename if you want Nmap to read hosts from standard input rather than an actual file.

3. Choose Targets at Random (-iR <numtargets>)
For Internet-wide surveys and other research, you may want to choose targets at random. This is done with the -iR option, which takes as an argument the number of IPs to generate. Nmap automatically skips certain undesirable IPs, such as those in private, multicast, or unallocated address ranges. The argument 0 can be specified for a never-ending scan. Keep in mind that some network administrators bristle at unauthorized scans of their networks. Carefully read the section called “Legal Issues” before using -iR.

If you find yourself really bored one rainy afternoon, try the command nmap -sS -PS80 -iR 0 -p 80 to locate random web servers for browsing.

4. Excluding Targets (--exclude, --excludefile <filename>)
It is common to have machines which you don't want to scan under any circumstances. Machines can be so critical that you won't take any risk of an adverse reaction. You might be blamed for a coincidental outage even if the Nmap scan had nothing to do with it. Or perhaps you have legacy hardware that is known to crash when scanned, but you haven't been able to fix or replace it yet. Or maybe certain IP ranges represent subsidiary companies, customers, or partners that you aren't authorized to scan. Consultants often don't want their own machine included in a scan of their client's networks. Whatever the reason, you can exclude hosts or entire networks with the --exclude option. Simply pass the option a comma-separated list of excluded targets and netblocks using the normal Nmap syntax. Alternatively, you can create a file of excluded hosts/networks and pass that to Nmap with the --excludefile option. The --exclude option doesn't mix with IP ranges that use commas (192.168.0.10,20,30) because --exclude itself uses commas. Use --excludefile in these cases.

5. Practical Examples
While some tools have simple interfaces that only allow a list of hosts or maybe let you specify the start and end IP addresses for a range, Nmap is much more powerful and flexible. But Nmap can also be more difficult to learn—and scanning the wrong IP addresses is occasionally disastrous. Fortunately, Nmap offers a dry run using the list scan (-sL option). Simply execute nmap -sL -n <targets> to see which IPs would be scanned before you actually do it.

Examples may be the most effective way to teach the Nmap host specification syntax. This section provides some, starting with the simplest.

 - nmap scanme.nmap.org, nmap scanme.nmap.org/32
 - nmap 64.13.134.52
 
These three commands all do the same thing, assuming that scanme.nmap.org resolves to 64.13.134.52. They scan that one IP and then exit.

 - nmap scanme.nmap.org/24
 - nmap 64.13.134.52/24
 - nmap 64.13.134.- 
 - nmap 64.13.134.0-255

These four commands all ask Nmap to scan the 256 IP addresses from 64.13.134.0 through 64.13.134.255. In other words, they ask to scan the class C sized address space surrounding scanme.nmap.org.

 - nmap 64.13.134.52/24 
 - --exclude scanme.nmap.org,insecure.org

Tells Nmap to scan the class C around 64.13.134.52, but to skip scanme.nmap.org and insecure.org if they are found within that address range.

 - nmap 10.0.0.0/8 --exclude 10.6.0.0/16,
 - ultra-sensitive-host.company.com

Tells Nmap to scan the whole private 10 range except that it must skip anything starting with 10.6 as well as ultra-sensitive-host.company.com.

egrep '^lease' /var/lib/dhcp/dhcpd.leases | awk '{print $2}' | nmap -iL -
Obtain the list of assigned DHCP IP addresses and feed them directly to Nmap for scanning. Note that a hyphen is passed to -iL to read from standard input.

 - nmap -6 2001:800:40:2a03::3

Scans the IPv6 host at address 2001:800:40:2a03::3.