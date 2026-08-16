Controlled Lab: Windows Endpoint Attack Lifecycle & Mitigation
Objective
To understand the fundamentals of network reconnaissance, payload generation using Msfvenom, listener configuration with Msfconsole, and post-exploitation on controlled Windows 10 target machine within a secure, isolated home lab environment.

Lab Environment & Topology
Attacker Machine: Kali Linux (192.168.100.109)
Target Machine: Windows 10 (192.168.100.12)
Tools Used: Ping, Nmap, Msfvenom, Msfconsole, Apache2
Step-by-Step Procedure
Step 1: Network Reconnaissance
Verified network connectivity between the attacker machine and the Windows 10 target using ICMP echo requests (ping).

Step 2: Payload Generation (Msfvenom)
Created a custom Windows Meterpreter reverse TCP payload disguised as a system update (windowsupadate.exe), pointing to the attacker's IP and listener port (4444).

Step 3: Payload Hosting
Copied the generated binary into the Apache web server directory (/var/www/html) and initiated the apache2 service on Kali Linux.

Step 4: Exploit Listener Configuration (Msfconsole)
Launched Metasploit, selected the exploit/multi/handler module, matched the payload type, configured the LHOST and LPORT, and initiated the listener.

Step 5: Delivery & Execution
Downloaded and executed the payload on the target machine to establish a reverse TCP connection back to the handler.

Step 6: Post-Exploitation
Interacted with the established Meterpreter session to demonstrate system visibility, remote diagnostics, and post-exploitation capabilities.

Key Takeaways & Defense Recommendations
Endpoint Protection: Keep host-based firewalls and modern antivirus solutions active and updated.
Software Restrictions: Implement AppLocker or Software Restriction Policies (SRP) to prevent execution from untrusted or writable directories.
Disclaimer: This documentation is strictly for educational purposes, defensive awareness, and authorized testing in a secure home lab environment.
