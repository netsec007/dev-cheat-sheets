### NMAP Scan Types

| Scan Type	| Details |
| __________ | __________ |
| TCP SCAN | Data |


A TCP scan is used to ensure that a three-way handshake has been completed between you and a selected target system. Even though it is very noisy, a TCP scan can be detected with little to no effort. This is because the services may log the sender's IP address and may trigger an intrusion detection system

UDP SCAN	| The UDP scan checks whether there is any UDP port open and listens for incoming connections on the target machine. Contrary to TCP, UDP does not offer any way to cure a positive result by sending a response with a positive acknowledgment. As a result, UDP scans may sometimes produce false positives. This type of scan is usually quite slow because computers, in general, slow down their responses to this kind of traffic in order to be on the safe side.

SYN SCAN	In a SYN scan, a TCP connection is established by first creating a SYN packet and sending it to the server. This is unlike a normal TCP scan, which just generates a SYN packet. The response to these specially crafted packets is also analyzed by Nmap to produce scan results.
ACK SCAN	To be able to monitor whether a particular port is filtered or not, ACK scans are employed. This guarantees to be very valuable when trying to spy on firewalls or their existing protocols. Simple packet filtering allows established connections, whereas a more complex firewall might not.
FIN SCAN	The FIN scan is a stealthy TCP connection scan that sends a TCP FIN packet instead of a SYN packet. The computer may either send an RST packet (reset packet) back if it receives this input or send a FIN scan (finishing process) that may falsely generate positives and negatives, but it may elude some IDS systems and other countermeasures.
NULL SCAN	A null scan is exactly what it sounds like: It leaves all of the header fields blank. Null packets are usually not valid and a few targets may not be able to handle them, but it is possible for them to be. Against a specific type of windows target, also known as null packet scanning, it is possible to produce unreliable results. On the other hand, as an effective way to get through windows, it is usually possible.
XMAS SCAN	XMAS scans are very covert in nature. Because of the way their TCP protocol operates, computers running Windows will not react to Xmas scans in any way. The scan's name comes from the set of flags that are turned on within the packet that is being sent out for scanning. XMAS scans are used to manipulate the PSH, URG, and FIN flags found in the TCP header.
RPC SCAN	RPC scans are used to discover remote procedure calls (RPC) machines that respond to Remote Procedure Call services (RPC). RPC services can be run on a variety of ports, making it hard to identify from a normal scan whether RPC services are running or not. It is generally a good idea to conduct an RPC scan periodically to learn where they are operating.
IDLE SCAN	IDLE Scan is one of the less popular types of scans because it requires the host to be controlled. The packets are bounced off an external host in order to conceal their origins. Malicious attacks are limited to only those packets that are bounced off the internal host. It is one of the more controversial choices in Nmap because it is primarily used for malicious attacks.
