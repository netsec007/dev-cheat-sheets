<head>
<style>
Body  {  background-color:thistle;  }
P  {  font-size:20px;  color:mediumblue;  }
</style>
</head>

## NMAP Scan Types

| Scan Type	| Details |
| --------------- | ---------- |
| TCP | Used to ensure that a three-way handshake has been completed between you and a selected target system. Even though it is very noisy, a TCP scan can be detected with little to no effort. This is because the services may log the sender's IP address and may trigger an intrusion detection system |
| UDP | The UDP scan checks whether there is any UDP port open and listens for incoming connections on the target machine. Contrary to TCP, UDP does not offer any way to cure a positive result by sending a response with a positive acknowledgment. As a result, UDP scans may sometimes produce false positives. This type of scan is usually quite slow because computers, in general, slow down their responses to this kind of traffic in order to be on the safe side |
| SYN	| In a SYN scan, a TCP connection is established by first creating a SYN packet and sending it to the server. This is unlike a normal TCP scan, which just generates a SYN packet. The response to these specially crafted packets is also analyzed by Nmap to produce scan results |
| ACK |	To be able to monitor whether a particular port is filtered or not, ACK scans are employed. This guarantees to be very valuable when trying to spy on firewalls or their existing protocols. Simple packet filtering allows established connections, whereas a more complex firewall might not |
| FIN | The FIN scan is a stealthy TCP connection scan that sends a TCP FIN packet instead of a SYN packet. The computer may either send an RST packet (reset packet) back if it receives this input or send a FIN scan (finishing process) that may falsely generate positives and negatives, but it may elude some IDS systems and other countermeasures |
| NULL |	A null scan is exactly what it sounds like: It leaves all of the header fields blank. Null packets are usually not valid and a few targets may not be able to handle them, but it is possible for them to be. Against a specific type of windows target, also known as null packet scanning, it is possible to produce unreliable results. On the other hand, as an effective way to get through windows, it is usually possible |
| XMAS	| XMAS scans are very covert in nature. Because of the way their TCP protocol operates, computers running Windows will not react to Xmas scans in any way. The scan's name comes from the set of flags that are turned on within the packet that is being sent out for scanning. XMAS scans are used to manipulate the PSH, URG, and FIN flags found in the TCP header |
| RPC | RPC scans are used to discover remote procedure calls (RPC) machines that respond to Remote Procedure Call services (RPC). RPC services can be run on a variety of ports, making it hard to identify from a normal scan whether RPC services are running or not. It is generally a good idea to conduct an RPC scan periodically to learn where they are operating |
| IDLE |	IDLE Scan is one of the less popular types of scans because it requires the host to be controlled. The packets are bounced off an external host in order to conceal their origins. Malicious attacks are limited to only those packets that are bounced off the internal host. It is one of the more controversial choices in Nmap because it is primarily used for malicious attacks |

## Target Specification

| Option |	Example	| Description |
| --- | --- | --- |
| | nmap 192.168.1.3	| Scan a specific IP address |
|	| nmap 192.168.1.2 192.168.2.3	| Scan specific IP addresses |
|	| nmap 192.168.1.7-254	| Scan specific range of IP addresses |
|	| nmap ramdom.doman.org	| Scans a domain |
|	| nmap 192.168.1.1/29	| Scans a single IP using CIDR notation |
| -iL	| nmap -iL text.txt	| Scans a target from a file |
| -iR	| nmap -iR 200	| Scans random 200 hosts |
| –exclude	| nmap -exclude 192.168.1.2	| Exclude the listed hosts |

## Scan Technique

| Option	| Example	| Description |
| --- | --- | --- |
| -sS	| nmap 192.167.1.2 -sS	| TCP SYN Scan |
| -sT	| nmap 192.168.1.1 -sT	| TCP Connect Scan |
| -sU	| nmap 192.168.1.1 -sU	| UDP scan |
| -sA	| nmap 192.168.1.1 -sA	| TCP ACK Scan |
| -sW	| nmap 192.168.1.1 -sW	| TCP Window scan |
| -sM	| nmap 192.168.1.1 -sM	| TCP Maimon scan |

## Host Discovery

| Option	| Example	| Description |
| --- | --- | --- |
| -sL	| nmap 192.168.1.6-9 -sL	| Creates targets List only |
| -sn	| nmap 192.168.1.2/29 -sn	| This disables port scans and does host discovery only |
| -Pn	| nmap 192.168.1.2-5 -Pn	| This disables host discovery and allows port scan only |
| -PS	| nmap 192.168.1.2-5 -PS22-25,80	| TCP SYN ping on port x - Port 80 is default |
| -PA	| nmap 192.168.1.2-5 -PA22-25,80 |	TCP ACK ping on port x - Port 80 is default |
| -PU	| nmap 192.168.1.3-7 -PU53 | 	Enables UDP ping on port x - Port 40125 is by default |
| -PR	| nmap 192.168.1.2-3/24 -PR	| ARP ping on the local network |
| -n	| nmap 192.168.1.2 -n	| Disables DNS resolution |

## Port Specification

| Option	| Example	| Description |
| --- | --- | --- |
| -p	| nmap 192.168.1.9 -p 27	| Scan a specific port |
| -p	| nmap 192.168.1.9 -p 27-100	| Scan a port range |
| -p	| nmap 192.168.1.9 -p U:53,T:27-40,80	| Scans multiple TCP and UDP ports |
| -p-	| nmap 192.168.1.9 -p- | Scan all ports |
| -p	| nmap 192.168.1.9 -p http,https	| Scans based on the service name |
| -F	| nmap 192.168.1.9 -F	| Scan 100 ports in fast manner |
| –top-ports	| nmap 192.168.1.9 -top-ports 1015	| Scans the top “x” ports |
| -p-65535	| nmap 192.168.1.8 -p-65535	| Skips the initial port in the range and starts the scan from port 1 |
| -p0-	| nmap 192.168.1.9 -p0-	| Skips end port in the range and starts the scan to go through to the port 65535 |

## Service and Version Detection

| Option	| Example	| Description |
| --- | --- | --- |
| -sV	| nmap 192.168.1.9 -sV	| Helps in determining the version of the service  |
| -sV –version-intensity	| nmap 192.168.1.9 -sV -version-intensity 9	| To increase the Intensity level between 0 to 9. The higher the number higher is possibility of correctness |
| -sV –version-light	| nmap 192.168.1.9 -sV -version-light	| This enables light mode. This has a lower possibility of correctness but is faster |
| -sV –version-all	| nmap 192.168.1.9 -sV -version-all	| This enables an intensity level  of 9. This has a higher possibility of correctness but is slower |
| -A	| nmap 192.168.1.8 -A	| This enables OS detection, version detection, and script scanning |

## OS Detection

| Option	| Example	| Description |
| --- | --- | --- |
| -O	| nmap 192.168.1.8 -O	| TCP/IP stack fingerprinting is used for remote OS detection |
| -O –osscan-limit	| nmap 192.168.1.8 -O -osscan-limit	| The TCP port scan will not attempt OS detection on those hosts that do not have at least one open and one closed port |
| -O –osscan-guess	| nmap 192.168.1.8 -O -osscan-guess	| Makes Nmap guess more competently |
| -O –max-os-tries	| nmap 192.168.1.8 -O -max-os-tries 1	| This set the maximum number “x” of OS detection attempts against a target |

## Timing and Performance

| Option	| Example	| Description |
| --- | --- | ---|
| -T0	| nmap 192.168.1.8 -T0	| Paranoid (0) Timing |
| -T1	| nmap 192.168.1.8 -T1	| Sneaky (1) Timing |
| -T2	| nmap 192.168.1.8 -T2	| Polite (2) Timing |
| -T3	| nmap 192.168.1.8 -T3	| Normal (3) Timing |
| -T4	| nmap 192.168.1.8 -T4	| Aggressive (4) Timing |
| -T5	| nmap 192.168.1.8 -T5	| Insane (5) Timing |

| Option	| Example input	| Description |
| --- | --- | --- |
| –host-timeout <time>	| 5s; 10m; 5h	| After this long, give up on the target |
| –min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>	| 5s; 10m; 5h	| How long it takes to return a probe round trip |
| –min-hostgroup/max-hostgroup <size<size>	| 20; 512	| Specifies host scan group sizes for parallelization |
| –min-parallelism/max-parallelism <numprobes>	| 10; 1	| This probes parallelization |
| –scan-delay/–max-scan-delay <time>	| 10ms; 5s; 10m; 3h	| This adjusts the delay between probes |
| –max-retries <tries>	| 5	| Specifies the maximum number retries for port scan probe retransmissions |
| –min-rate <number>	| 10	| This sends packets at a minimum speed of <number> per second |
| –max-rate <number>	| 250	| This sends packets at a maximum speed of <number> per second |

## NSE Scripts

| Option	| Example	| Description |
| --- | --- | --- |
| -sC	| nmap 192.168.1.9 -sC	| Default NSE scripts are used to scan |
| –script default	| nmap 192.168.1.9 -script default	| This scans with default NSE scripts |
| –script	| nmap 192.168.1.9 -script=banner	| Single script scanning |
| –script	| nmap 192.168.1.9 -script=http*	| Wildcard scanning |
| –script	| nmap 192.168.1.9 -script=http,banner	| Two scripts scanning |
| –script	| nmap 192.168.1.9 -script "not intrusive"	| Default scanning without intrusive scripts |
| –script-args	| nmap -script snmp-sysdescr -script-args snmpcommunity=admin 192.168.1.9	| NSE script scanning with scipts |

## NSE Script Examples

| Command	| Description |
| --- | --- |
| nmap -Pn -script=http-sitemap-generator interviewbit.com 	| Map generator for HTTP site |
| nmap -n -Pn -p 80 -open -sV -vvv -script banner,http-title -iR 1000	| Search random web servers |
| nmap -Pn -script=dns-brute interviewbit.com	| This guesses sub-domains by brute forcing on DNS hostnames |
| nmap -n -Pn -vv -O -sV -script smb-enum*,smb-ls,smb-mbenum,smb-os-discovery,smb-s*,smb-vuln*,smbv2* -vv 192.168.1.1	| Run safe SMB scripts |
| nmap -script whois* interviewbit.com	| Query for whois |
| nmap -p80 -script http-unsafe-output-escaping interviewbit.com	| Vulnerabilities detection on cross websites |
| nmap -p80 -script http-sql-injection interviewbit.com	| SQL injections detection |

## Firewall / IDS Evasion

| Option	| Example	| Description |
| --- | --- | --- |
| -f | nmap 192.168.1.9 -f	| Small fragmented IP packets are used in requested scans (including ping scans). More difficult for packet filters |
| –mtu	| nmap 192.168.1.9 -mtu 32	| Set the offset size yourself |
| -D	| nmap -D 192.168.9.102, 192.168.9.103, 192.168.9.104, 192.168.9.523	| Scans from the spoofed IPs are send via this |
| -S	| nmap -S www.interviewbit.com www.scaler.com 	| Scans Scaler from InterviewBit |
| -g	| nmap -g 53 192.168.1.9	| Uses the given port number |
| –proxies	| nmap -proxies http://192.168.1.9:8080, http://192.168.9.2:8080 192.168.1.9	| This relays connections via HTTP or SOCKS4 proxy |
| –data-length	| nmap -data-length 200 192.168.1.9	| This adds random data to the sent packets |

## Output Options

| Option	| Example |	Description |
| --- | --- | --- |
| -oN	| nmap 192.168.1.9 -oN result.file	| Adds the output to the result.file that is in normal format |
| -oX	| nmap 192.168.1.9 -oX result.file	| Adds the output to the result.file that is in XML format |
| -oG	| nmap 192.168.1.9 -oG result.file	| Adds the output to the result.file that can be grepable |
| -oA	| nmap 192.168.1.9 -oA results	| All three major formats are displayed via this |
| -oG –	| nmap 192.168.1.9 -oG -	| Shows grepable output on the screen |
| –append-output	| nmap 192.168.1.9 -oN file.file -append-output	| Adds a scan to the previous scanned file |
| -v	| nmap 192.168.1.9 -v	| Verbosity level is increase via this |
| -d	| nmap 192.168.1.9 -d	| Debugging level is increase via this |
| –reason	| nmap 192.168.1.9 -reason	| Shows the reason for the given state of the port |
| –open	| nmap 192.168.1.9 -open	O| pen ports are shown |
| –packet-trace	| nmap 192.168.1.9 -T4 -packet-trace	| Packets sent and received are shown |
| –iflist	| nmap -iflist	| Host interfaces and routes are shown |
| –resume	| nmap -resume scaler.file	| Scan is resumed |


## Other Useful Commands

| Command	| Description |
| --- | --- |
| nmap -iR 10 -PS22-25,80,113,1050,35000 -v -sn	| Only ports x are scanned, no ports are discovered |
| nmap 192.168.1.9-1/25 -PR -sn -vv	| Only show ARP discovery on the local network, no port scan |
| nmap -iR 20 -sn -traceroute	| No port scan - just traceroute to specific targets |
| nmap 192.168.1.9-40 -sL -dns-server 192.168.1.9	| Queries the Internal DNS for detecting hosts and then lists targets |
