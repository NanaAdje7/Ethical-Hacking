# Social Engineering Toolkit (SET) Lab

## Overview
The Social-Engineer Toolkit (SET) is an open-source penetration testing framework used to simulate social engineering attacks such as phishing and credential harvesting.

This lab demonstrates how a website can be cloned and used to capture user credentials in a controlled environment.

---

## Lab Objectives
- Understand website cloning attacks
- Learn how credentials can be harvested
- Identify phishing-related security risks
- Apply ethical hacking principles

---

## Tools and Environment
- Kali Linux (Ethical Hacking Course VM)
- Social-Engineer Toolkit (SET)
- Internal virtual network

---

## Background
Website cloning is commonly used in phishing attacks. Attackers replicate legitimate websites to trick users into entering sensitive information.

This lab shows how such attacks work and why users must always verify URLs before submitting credentials.

---

## Commands Used and Their Functions (SET Lab)

### 1. `sudo -i`
**Function:**  
Grants persistent root (administrator) access.

**Explanation:**  
The Social-Engineer Toolkit requires administrative privileges to bind to network ports and manage system services. This command ensures SET can run without permission issues.

---

### 2. `setoolkit`
**Function:**  
Launches the Social-Engineer Toolkit framework.

**Explanation:**  
This command starts the SET menu-driven interface, providing access to social engineering attack simulations such as phishing and website cloning.

---

###  `1` – Social Engineering Attacks
**Function:**  
Selects the Social Engineering Attacks module.

**Explanation:**  
This module contains attacks that exploit human behavior, including phishing and credential harvesting techniques.

---

###  `2` – Website Attack Vectors
**Function:**  
Accesses web-based attack methods.

**Explanation:**  
Website attack vectors allow the creation of fake or cloned websites designed to trick users into submitting sensitive information.

---

###  `3` – Credential Harvester Attack Method
**Function:**  
Enables the credential harvesting module.

**Explanation:**  
This option captures data submitted through web forms, such as usernames and passwords, and displays them in real time.

---

###  `2` – Site Cloner
**Function:**  
Clones a legitimate website and hosts it locally.

**Explanation:**  
The Site Cloner creates a fake copy of the target website that looks identical to the original, making it effective for phishing simulations.

---

###  Attacker IP Address (e.g. `10.6.6.1`)
**Function:**  
Specifies the IP address that will host the cloned website.

**Explanation:**  
This is the IP address of the Kali Linux machine in the internal lab network. SET uses it to receive incoming connections and capture credentials.

---

###  Target Website URL (e.g. `http://DVWA.vm`)
**Function:**  
Defines the website to be cloned.

**Explanation:**  
SET retrieves the content of the target website and replicates it locally so users interacting with the fake page believe it is legitimate.

---

###  `CTRL + C`
**Function:**  
Stops the credential harvesting process.

**Explanation:**  
This command terminates the SET listener and generates a report file containing the captured credentials.

---

###  `cat "filename.xml"`
**Function:**  
Displays the contents of the captured credentials report.

**Explanation:**  
The report file is saved in XML format. Quotation marks are required because the filename contains spaces and special characters.

