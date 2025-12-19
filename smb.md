## SMB Enumeration – Commands Used and Their Functions

In this lab, I explored SMB (Server Message Block) enumeration using enum4linux on a controlled virtual environment.
SMB is a protocol used by Windows systems to share files, printers, and other resources over a network.
Understanding and testing SMB vulnerabilities is crucial for ethical hackers to identify misconfigurations and weak security policies on target machines.

I also used smbclient to interact with SMB shares, simulating file transfers to understand the risks of misconfigured SMB services.

### 1. `sudo su`
**Function:**  
Switches the current user to the root account.

**Explanation:**  
Most SMB enumeration and file‑sharing tools require administrative privileges. This command was used to gain persistent root access before running Enum4Linux and smbclient.

---

### 2. `enum4linux --help`
**Function:**  
Displays the Enum4Linux help menu.

**Explanation:**  
This command was used to review the available options and understand how Enum4Linux leverages Samba utilities to gather SMB information.

---

### 3. `nmap -sN 172.17.0.0/24`
**Function:**  
Scans the subnet to identify hosts and running services.

**Explanation:**  
This scan helped identify systems exposing SMB‑related ports, making them potential targets for enumeration.

---

### 4. `nmap -sN 10.6.6.0/24`
**Function:**  
Performs a network scan on the internal lab subnet.

**Explanation:**  
This command was used to confirm whether any internal machines were running SMB services that could be further investigated.

---

### 5. `enum4linux -U 172.17.0.2`
**Function:**  
Enumerates user accounts on the target system.

**Explanation:**  
This command attempts to retrieve a list of valid usernames via SMB, which is useful for understanding how much user information is exposed.

---

### 6. `enum4linux -Sv 172.17.0.2`
**Function:**  
Lists shared folders with verbose output.

**Explanation:**  
The verbose option shows how Enum4Linux collects share information using Samba tools, providing insight into the enumeration process.

---

### 7. `enum4linux -P 172.17.0.2`
**Function:**  
Retrieves the password policy of the target system.

**Explanation:**  
Password policy details help assess how resistant the system is to brute‑force or password‑guessing attacks.

---

### 8. `enum4linux -a 10.6.6.23`
**Function:**  
Performs a comprehensive SMB enumeration scan.

**Explanation:**  
This option combines several enumeration techniques into one command, making it useful for quickly gathering extensive SMB information.

---

### 9. `cat >> badfile.txt`
**Function:**  
Creates and writes content to a text file.

**Explanation:**  
This command was used to create a sample file that simulated a malicious file for testing SMB file upload functionality.

---

### 10. `smbclient --help`
**Function:**  
Displays available smbclient options.

**Explanation:**  
This command was used to understand how to connect to SMB shares and perform file operations.

---

### 11. `smbclient -L //172.17.0.2/`
**Function:**  
Lists SMB shares on the target system.

**Explanation:**  
This command checks which shared resources are accessible, including those that allow anonymous access.

---

### 12. `smbclient //172.17.0.2/tmp`
**Function:**  
Connects to a specific SMB share.

**Explanation:**  
An interactive session was opened with the target share to allow directory listing and file transfer.

---

### 13. `dir`
**Function:**  
Lists files within the connected SMB share.

**Explanation:**  
This command verified the contents of the share and confirmed successful file upload.

---

### 14. `put badfile.txt badfile.txt`
**Function:**  
Uploads a file to the SMB share.

**Explanation:**  
This command demonstrated how files can be placed on a remote system through SMB when permissions are misconfigured.

---

### 15. `quit`
**Function:**  
Exits the smbclient session.

**Explanation:**  
This command safely closed the SMB connection and returned control to the terminal.

**Conclusion**
This lab reinforced the importance of SMB enumeration in ethical hacking.
By using enum4linux and smbclient, we learned how to identify potential vulnerabilities in Windows networks and understand the configuration of SMB services.
Properly documenting findings helps security professionals recommend mitigations and improve network security.
