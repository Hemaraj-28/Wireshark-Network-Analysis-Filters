**Introduction**

Wireshark is an open-source network protocol analyzer used to capture, inspect, and analyze network traffic. It helps users understand communication between devices, troubleshoot network problems, and investigate unusual network activities.

**1. IP Address Filters**
<img width="1564" height="712" alt="Screenshot 2026-11-23 143803" src="https://github.com/user-attachments/assets/10a83d6f-afbb-466b-9157-ac173e6d4275" />



IP address filters help identify packets based on their source and destination IP addresses.

\| Filter \| Description \|

\|---\|---\|

\| \`ip.addr == 192.168.1.10\` \| Displays packets involving a specific IP address \|

\| \`ip.src == 192.168.1.10\` \| Displays packets originating from a specific IP \|

\| \`ip.dst == 192.168.1.20\` \| Displays packets sent to a specific destination IP \|

**2. Protocol Filters**



Protocol filters identify packets belonging to specific network protocols.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp\` \| Displays TCP packets \|

\| \`udp\` \| Displays UDP packets \|

\| \`dns\` \| Displays DNS queries and responses \|

**3. Port Filters**

<img width="1097" height="612" alt="Screenshot 2026-11-23 143049" src="https://github.com/user-attachments/assets/8296a328-55f6-45ca-a227-a0e0d21619b0" />
Port filters identify network traffic associated with specific services and applications.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.port == 80\` \| Displays TCP traffic involving HTTP port 80 \|

\| \`tcp.port == 443\` \| Displays TCP traffic involving HTTPS port 443 \|

\| \`udp.port == 53\` \| Displays UDP traffic involving DNS port 53 \|

4\. Time-Based Filters
<img width="1568" height="606" alt="Screenshot 2026-11-23 143918" src="https://github.com/user-attachments/assets/7468bd9a-9f82-4d43-a486-98cd4a090eba" />


Time-based filters help analyze packets according to their arrival time and capture timestamps.

\| Filter \| Description \|

\|---\|---\|

\| \`frame.time \>= "Nov 23, 2026 10:00:00"\` \| Displays packets captured at or after the specified time \|

\| \`frame.time \<= "Nov 23, 2026 10:30:00"\` \| Displays packets captured at or before the specified time \|

\| \`frame.time_delta \> 1\` \| Displays packets arriving more than one second after the previous packet in the capture \|

\*\*Note:\*\* The date and time in the first two examples are illustrative. Use a timestamp format compatible with your Wireshark version and capture settings. \`frame.time_delta\` measures the interval from the previous captured frame, not necessarily the previous packet in the same conversation.

5\. Error and Anomaly-Based Filters

<img width="1568" height="609" alt="Screenshot 2026-11-23 144002" src="https://github.com/user-attachments/assets/f96a0fca-4603-4afd-a205-db673c0f2328" />


These filters help identify retransmissions, duplicate acknowledgments, and malformed packets.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.analysis.retransmission\` \| Displays TCP retransmitted packets \|

\| \`tcp.analysis.duplicate_ack\` \| Displays duplicate TCP acknowledgment packets \|

\| \`malformed\` \| Displays packets identified by Wireshark as malformed \|

**6. TCP Flags Filters**
<img width="1574" height="606" alt="Screenshot 2026-11-23 144037" src="https://github.com/user-attachments/assets/d2964e69-d022-4cd0-ada0-8f35ff951437" />



TCP flags control connection establishment, communication, and termination.

\| Filter \| Description \|

\|---\|---\|

\| \`tcp.flags.syn == 1\` \| Displays packets with the SYN flag enabled \|

\| \`tcp.flags.ack == 1\` \| Displays packets with the ACK flag enabled \|

\| \`tcp.flags.fin == 1\` \| Displays packets with the FIN flag enabled \|

**7. Combination Filters**
<img width="1560" height="608" alt="Screenshot 2026-11-23 144118" src="https://github.com/user-attachments/assets/3f12cb00-670f-4c7f-9f3f-e07f9a1d7473" />




\| Filter \| Description \|

\|---\|---\|

\| \`tcp && ip.addr == 192.168.1.10\` \| Displays TCP traffic involving a specific IP \|

\| \`ip.src == 192.168.1.10 && tcp.port == 80\` \| Displays TCP port 80 traffic originating from a specific IP \|

\| \`tcp.flags.syn == 1 && tcp.flags.ack == 0\` \| Displays initial TCP connection requests \|

**8. Field-Based Filters**
<img width="1514" height="728" alt="Screenshot 2026-11-23 154004" src="https://github.com/user-attachments/assets/254116b1-822e-4bb1-9cfb-ed146b613f9e" />

Field-based filters inspect specific fields within packet headers and protocol information.

\| Filter \| Description \|

\|---\|---\|



\| \`ip.ttl \< 64\` \| Displays IPv4 packets with a TTL value below 64 \|

\| \`tcp.window_size \< 1000\` \| Displays TCP packets with an advertised window size below 1000 \|

**9. Advanced Filters**
<img width="1502" height="649" alt="Screenshot 2026-11-23 150839" src="https://github.com/user-attachments/assets/502d8a57-5074-45aa-a392-13503918df45" />




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
