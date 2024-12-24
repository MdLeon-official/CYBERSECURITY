### **Nmap Command Cheatsheet with Examples**

---

### **1. `nmap -sn <ip>`**
Performs a ping scan to determine if the host is up without scanning ports.

**Example**:  
```bash
nmap -sn 192.168.1.1
```
- Checks if the host at `192.168.1.1` is reachable.

---

### **2. `nmap <ip>`**
Performs a default scan (Top 1,000 TCP ports).

**Example**:  
```bash
nmap 192.168.1.1
```
- Scans the top 1,000 ports on `192.168.1.1`.

---

### **3. `nmap -p <specificPort> <ip>`**
Scans a specific port on the target.

**Example**:  
```bash
nmap -p 22 192.168.1.1
```
- Scans port `22` (SSH) on `192.168.1.1`.

---

### **4. `nmap -sV <ip>`**
Detects the version of services running on open ports.

**Example**:  
```bash
nmap -sV 192.168.1.1
```
- Identifies versions of services on `192.168.1.1`.

---

### **5. `nmap -O <ip>`**
Detects the target's operating system.

**Example**:  
```bash
nmap -O 192.168.1.1
```
- Attempts to determine the OS on `192.168.1.1`.

---

### **6. `nmap <ip/subnet_range>`**
Scans all devices in a given subnet.

**Example**:  
```bash
nmap 192.168.1.0/24
```
- Scans all hosts in the `192.168.1.0/24` subnet.

---

### **7. `nmap -p 1-1000 <ip>`**
Scans a range of ports.

**Example**:  
```bash
nmap -p 1-1000 192.168.1.1
```
- Scans ports 1 through 1,000 on `192.168.1.1`.

---

### **8. `nmap -T<0-5> <ip>`**
Sets the scan speed (0 = slowest, 5 = fastest).

**Example**:  
```bash
nmap -T4 192.168.1.1
```
- Scans `192.168.1.1` with a fast speed (`T4`).

---

### **9. `nmap -f <ip>`**
Performs a fragmented packet scan to evade firewalls.

**Example**:  
```bash
nmap -f 192.168.1.1
```
- Scans `192.168.1.1` using fragmented packets.

---

### **10. `nmap -scanflags <flags> <ip>`**
Customizes TCP flags for the scan.

**Example**:  
```bash
nmap -scanflags SYN 192.168.1.1
```
- Uses SYN flags for a custom scan.

---

### **11. `sudo nmap -sA <ip>`**
Performs an ACK scan to map firewall rules.

**Example**:  
```bash
sudo nmap -sA 192.168.1.1
```
- Checks if a firewall is filtering traffic to `192.168.1.1`.

---

### **12. `nmap --script vuln <ip>`**
Runs vulnerability scripts on the target.

**Example**:  
```bash
nmap --script vuln 192.168.1.1
```
- Runs vulnerability detection scripts on `192.168.1.1`.

---

### **13. `nmap --script http-enum <ip>`**
Enumerates directories and files on a web server.

**Example**:  
```bash
nmap --script http-enum 192.168.1.1
```
- Attempts to list files/directories on `192.168.1.1`.

---

### **14. `nmap --script ssh-brute -p 22 <ip>`**
Performs brute force attacks on SSH.

**Example**:  
```bash
nmap --script ssh-brute -p 22 192.168.1.1
```
- Attempts SSH brute force on port `22` of `192.168.1.1`.

---

### **15. `nmap --script ssl-heartbleed`**
Checks for the Heartbleed vulnerability.

**Example**:  
```bash
nmap --script ssl-heartbleed 192.168.1.1
```
- Scans `192.168.1.1` for the Heartbleed bug.

---

### **16. `nmap -sT -sU <ip>`**
Performs both TCP and UDP scans.

**Example**:  
```bash
nmap -sT -sU 192.168.1.1
```
- Scans TCP and UDP ports on `192.168.1.1`.

---

### **17. `nmap -oN <file.txt> <ip>`**
Saves scan results in normal format to a file.

**Example**:  
```bash
nmap -oN output.txt 192.168.1.1
```
- Saves the results to `output.txt`.

---

### **18. `nmap -oX <scan.xml> <ip>`**
Saves scan results in XML format.

**Example**:  
```bash
nmap -oX scan.xml 192.168.1.1
```
- Saves the results to `scan.xml`.

---

### **19. `nmap -oG <grep.txt> <ip>`**
Saves scan results in grepable format.

**Example**:  
```bash
nmap -oG grep.txt 192.168.1.1
```
- Saves the results to `grep.txt`.

---

### **20. `nmap -sV --script=banner <ip>`**
Fetches banners of services on open ports.

**Example**:  
```bash
nmap -sV --script=banner 192.168.1.1
```
- Retrieves service banners from `192.168.1.1`.

---

### **21. `nmap --script http-vuln-cve2014-3704 -p 80 <ip>`**
Scans for a specific vulnerability (e.g., CVE-2014-3704).

**Example**:  
```bash
nmap --script http-vuln-cve2014-3704 -p 80 192.168.1.1
```
- Checks `192.168.1.1` for the CVE-2014-3704 vulnerability on port `80`.

---

### **22. `nmap -sS -Pn <ip>`**
Performs a stealth SYN scan while skipping host discovery.

**Example**:  
```bash
nmap -sS -Pn 192.168.1.1
```
- Conducts a stealth SYN scan, assuming the host is up.

---

### **23. `nmap -sC <ip>`**
Runs default scripts on the target.

**Example**:  
```bash
nmap -sC 192.168.1.1
```
- Executes a set of standard Nmap scripts against `192.168.1.1`.

---

### **24. `nmap -sU --top-ports <number> <ip>`**
Scans the top `<number>` UDP ports.

**Example**:  
```bash
nmap -sU --top-ports 100 192.168.1.1
```
- Scans the top 100 UDP ports on `192.168.1.1`.

---

### **25. `nmap --script smb-enum-shares <ip>`**
Enumerates SMB shares on a target.

**Example**:  
```bash
nmap --script smb-enum-shares 192.168.1.1
```
- Lists SMB shared folders on `192.168.1.1`.

---

### **26. `nmap --script smtp-open-relay -p 25 <ip>`**
Tests an SMTP server for open relay configuration.

**Example**:  
```bash
nmap --script smtp-open-relay -p 25 192.168.1.1
```
- Checks if `192.168.1.1` allows open email relays on port 25.

---

### **27. `nmap --script dns-brute <ip>`**
Performs DNS subdomain brute-forcing.

**Example**:  
```bash
nmap --script dns-brute 192.168.1.1
```
- Attempts to discover subdomains of `192.168.1.1`.

---

### **28. `nmap -D RND:10 <ip>`**
Uses decoys to obscure your IP.

**Example**:  
```bash
nmap -D RND:10 192.168.1.1
```
- Sends scans from 10 random decoy IPs to `192.168.1.1`.

---

### **29. `nmap -sV --version-all <ip>`**
Performs a detailed service version scan.

**Example**:  
```bash
nmap -sV --version-all 192.168.1.1
```
- Retrieves extended version details of services on `192.168.1.1`.

---

### **30. `nmap --script ftp-anon -p 21 <ip>`**
Tests for anonymous FTP login.

**Example**:  
```bash
nmap --script ftp-anon -p 21 192.168.1.1
```
- Checks if `192.168.1.1` allows anonymous FTP login on port 21.

---

### **31. `nmap --traceroute <ip>`**
Performs a traceroute to the target during the scan.

**Example**:  
```bash
nmap --traceroute 192.168.1.1
```
- Maps the path to `192.168.1.1`.

---

### **32. `nmap -sW <ip>`**
Performs a Windows scan to determine firewall settings.

**Example**:  
```bash
nmap -sW 192.168.1.1
```
- Detects if `192.168.1.1` is filtering traffic.

---

### **33. `sudo nmap -PP <ip>`**
Uses ICMP Echo requests for host discovery.

**Example**:  
```bash
sudo nmap -PP 192.168.1.1
```
- Sends ICMP Echo requests to discover `192.168.1.1`.

---

### **34. `nmap --script http-sql-injection <ip>`**
Checks for SQL injection vulnerabilities in web servers.

**Example**:  
```bash
nmap --script http-sql-injection 192.168.1.1
```
- Tests for SQL injection on web services of `192.168.1.1`.

---

### **35. `nmap -sT -oA <base_name> <ip>`**
Saves results in all available formats.

**Example**:  
```bash
nmap -sT -oA scan_results 192.168.1.1
```
- Saves the output in Normal, XML, and Grepable formats.

---

### **36. `nmap -sR <ip>`**
Performs a scan to resolve RPC service information.

**Example**:  
```bash
nmap -sR 192.168.1.1
```
- Identifies RPC services running on `192.168.1.1`.

---

### **37. `sudo nmap --script broadcast-ping`**
Discovers live hosts on a network using broadcast pings.

**Example**:  
```bash
sudo nmap --script broadcast-ping
```
- Discovers live hosts on the local network.

---

### **38. `nmap -sZ -p <port> <ip>`**
Checks for OpenSSL vulnerabilities.

**Example**:  
```bash
nmap -sZ -p 443 192.168.1.1
```
- Scans port `443` on `192.168.1.1` for SSL vulnerabilities.

---

### **39. `sudo nmap -PE -PM -PP <ip>`**
Combines multiple host discovery techniques.

**Example**:  
```bash
sudo nmap -PE -PM -PP 192.168.1.1
```
- Uses ICMP Echo, Timestamp, and Address Mask requests.

---

### **40. `nmap -b <proxy> <ip>`**
Scans through a SOCKS5 proxy.

**Example**:  
```bash
nmap -b 192.168.1.100:1080 192.168.1.1
```
- Scans `192.168.1.1` through a proxy server at `192.168.1.100:1080`.

---
