# Cybersecurity Incident Report

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

## Section 1: Identify the type of attack that may have caused this network interruption

The website connections are timing out because the server is being overwhelmed by SYN packets during the TCP handshake. The logs show that a single IP address (203.0.113.0) is sending many SYN packets each second. This event could be a DOS attack, specifically a SYN flood attack, originating from a single source. This is preventing legitimate connections from being established since the server is being overwhelmed by SYN packets from a single IP address.

## Section 2: Explain how the attack is causing the website to malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. First, the connecting device sends a SYN packet to the server. The server then responds with a SYN/ACK packet and opens a port for the final part of the handshake. When the server receives the final ACK packet back from the device, the TCP connection is established. If more SYN packets are received than there are ports on the server, the server becomes overwhelmed and cannot function, so subsequent requests fail (devices cannot connect as they cannot complete the 3-way handshake). The logs indicate that a large number of SYN packets are originating from a single IP address and overwhelming the server. This is likely a DOS attack, which is resulting in user connections timing out. The travel agency cannot sell its services during this time, and users cannot review their purchases.

To prevent this, we should configure the firewall to deny requests from IP addresses sending excessive numbers of SYN packets. We could also install a next generation firewall.
