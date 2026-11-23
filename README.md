**Introduction**

Wireshark is an open-source network protocol analyzer used to capture, inspect, and analyze network traffic. It helps users understand communication between devices, troubleshoot network problems, and investigate unusual network activities.

**1. IP Address Filters**
<img width="1574" height="606" alt="Screenshot 2026-11-23 144037" src="https://github.com/user-attachments/assets/9b0095fd-cc0d-405f-8786-840626c6bbdc" />

<img src="./assets/media/image1.png" style="width:6.26042in;height:2.84375in" />

IP address filters help identify packets based on their source and destination IP addresses.

\| Filter \| Description \|

\|---\|---\|

\| \`ip.addr == 192.168.1.10\` \| Displays packets involving a specific IP address \|

\| \`ip.src == 192.168.1.10\` \| Displays packets originating from a specific IP \|

\| \`ip.dst == 192.168.1.20\` \| Displays packets sent to a specific destination IP \|

**2. Protocol Filters**

<img src="./assets/media/image2.png" style="width:6.26806in;height:3.49653in" />

Protocol filters identify packets belonging to specific network protocols.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp\` \| Displays TCP packets \|

\| \`udp\` \| Displays UDP packets \|

\| \`dns\` \| Displays DNS queries and responses \|

**3. Port Filters**

Port filters identify network traffic associated with specific services and applications.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.port == 80\` \| Displays TCP traffic involving HTTP port 80 \|

\| \`tcp.port == 443\` \| Displays TCP traffic involving HTTPS port 443 \|

\| \`udp.port == 53\` \| Displays UDP traffic involving DNS port 53 \|

4\. Time-Based Filters

<img src="./assets/media/image3.png" style="width:6.26042in;height:2.41667in" />

Time-based filters help analyze packets according to their arrival time and capture timestamps.

\| Filter \| Description \|

\|---\|---\|

\| \`frame.time \>= "Nov 23, 2026 10:00:00"\` \| Displays packets captured at or after the specified time \|

\| \`frame.time \<= "Nov 23, 2026 10:30:00"\` \| Displays packets captured at or before the specified time \|

\| \`frame.time_delta \> 1\` \| Displays packets arriving more than one second after the previous packet in the capture \|

\*\*Note:\*\* The date and time in the first two examples are illustrative. Use a timestamp format compatible with your Wireshark version and capture settings. \`frame.time_delta\` measures the interval from the previous captured frame, not necessarily the previous packet in the same conversation.

5\. Error and Anomaly-Based Filters

<img src="./assets/media/image4.png" style="width:6.26042in;height:2.42708in" />

These filters help identify retransmissions, duplicate acknowledgments, and malformed packets.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.analysis.retransmission\` \| Displays TCP retransmitted packets \|

\| \`tcp.analysis.duplicate_ack\` \| Displays duplicate TCP acknowledgment packets \|

\| \`malformed\` \| Displays packets identified by Wireshark as malformed \|

**6. TCP Flags Filters**

<img src="./assets/media/image5.png" style="width:6.26042in;height:2.41667in" />

TCP flags control connection establishment, communication, and termination.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.flags.syn == 1\` \| Displays packets with the SYN flag enabled \|

\| \`tcp.flags.ack == 1\` \| Displays packets with the ACK flag enabled \|

\| \`tcp.flags.fin == 1\` \| Displays packets with the FIN flag enabled \|

**7. Combination Filters**

<img src="./assets/media/image6.png" style="width:6.26042in;height:2.4375in" />Combination filters use multiple conditions to identify specific network traffic.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp && ip.addr == 192.168.1.10\` \| Displays TCP traffic involving a specific IP \|

\| \`ip.src == 192.168.1.10 && tcp.port == 80\` \| Displays TCP port 80 traffic originating from a specific IP \|

\| \`tcp.flags.syn == 1 && tcp.flags.ack == 0\` \| Displays initial TCP connection requests \|

**8. Field-Based Filters**

Field-based filters inspect specific fields within packet headers and protocol information.

\| Filter \| Description \|

\|---\|---\|

\| \`<img src="./assets/media/image7.png" style="width:6.27083in;height:3.25in" />\` \| Displays packets larger than 1000 bytes \|

\| \`ip.ttl \< 64\` \| Displays IPv4 packets with a TTL value below 64 \|

\| \`tcp.window_size \< 1000\` \| Displays TCP packets with an advertised window size below 1000 \|

**9. Advanced Filters**<img src="./assets/media/image8.png" style="width:6.26042in;height:2.70833in" />

Advanced filters combine multiple protocol fields and conditions for more specific network investigations.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.flags.syn == 1 && tcp.flags.ack == 0 && tcp.dstport == 80\` \| Identifies initial TCP connection requests targeting port 80 \|

\| \`dns.flags.response == 0 && dns.qry.name contains "example"\` \| Displays DNS queries containing the text example \|

\| \`tcp.analysis.retransmission && ip.addr == 192.168.1.10\` \| Displays TCP retransmissions involving a specific IP address \|

**Conclusion**

Wireshark display filters provide an effective way to inspect and analyze network communication.

IP address filters identify communicating devices, protocol filters identify network protocols, port filters identify application services, and time-based filters help examine packet timing.

TCP flag filters reveal connection behavior, while error and anomaly filters help identify potential communication problems. Combination, field-based, and advanced filters allow users to perform more detailed packet investigations.

Understanding these filters provides a strong foundation for network troubleshooting, cybersecurity monitoring, and packet analysis.

References

Wireshark Official Website: https://www.wireshark.org/

Wireshark Display Filter Reference: https://www.wireshark.org/docs/dfref/

Wireshark Filter Manual: https://www.wireshark.org/docs/man-pages/wireshark-filter.html

Tool Used: Wireshark

Purpose: Learning and practicing network packet analysis.
