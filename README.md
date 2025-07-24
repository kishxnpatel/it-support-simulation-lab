# 🖥️# IT Support Lab Project – osTicket Helpdesk System

## Overview
This project demonstrates the setup of a functional IT helpdesk system using osTicket in a virtualized lab environment.  
It replicates a real-world IT support workflow where users submit tickets, and technicians manage and resolve them.

The goal of this project was to strengthen hands-on skills in virtualization, Linux server administration, networking, and IT support ticketing systems.

---

## Key Skills Demonstrated
- Virtualization with Oracle VirtualBox (multi-VM lab setup)
- Network configuration and troubleshooting (Host-Only and Internal networks)
- Linux server administration (Apache, PHP, MariaDB installation)
- Database management (MySQL database creation and user configuration)
- Helpdesk operations using osTicket (ticket creation, assignment, and resolution)

---

## Lab Setup

### Virtual Machines
Three virtual machines were created and configured:

1. **Linux Mint Server** – Hosted Apache, PHP, MariaDB, and osTicket.
<img src="New folder/Linuxsetup.png" alt="Linux Mint Setup" width="450">
2. **Technician VM (Windows 10)** – Simulated IT support staff responding to tickets.
<img src="screenshots/TechnicianSetup.png" alt="Technician VM Setup" width="450">
3. **User VM (Windows 10)** – Simulated an end-user submitting tickets.
<img src="screenshots/userSetup.png" alt="User VM Setup" width="450">

### Network Configuration
- **Internal Network and Host-Only Adapter** enabled communication between VMs.  
- Static IPs assigned:
  - Linux Mint: 192.168.56.104
  - Technician VM: 192.168.56.101
  - User VM: 192.168.56.102
  
  Connectivity tested successfully using ping commands. </br>
 <img src="screenshots/ping (1).png" alt="Ping Test 1" width="400"> <img src="screenshots/ping (2).png" alt="Ping Test 2" width="400">

---

## Installation Highlights

### Hosting Environment Setup
- Installed Apache, PHP, and MariaDB on Linux Mint.
- Verified PHP prerequisites required by osTicket.

### Database Configuration
Created and configured the database:

```sql
CREATE DATABASE osticket;
CREATE USER 'osticketuser'@'localhost' IDENTIFIED BY 'pass123';
GRANT ALL PRIVILEGES ON osticket.* TO 'osticketuser'@'localhost';
FLUSH PRIVILEGES:
```

### osTicket Installation
1. Downloaded and extracted osTicket to /var/www/html/osticket.
2. Renamed and secured the configuration file: </br>
`sudo cp include/ost-sampleconfig.php include/ost-config.php` </br>
`sudo chmod 0644 include/ost-config.php`
3. Completed web-based installation, connecting to the configured database.

<img src="screenshots/osticketinst (1).png" alt="osTicket Installation Step 1" width="400"> <img src="screenshots/osticketinst (2).png" alt="osTicket Installation Step 2" width="400"> </br>
<img src="screenshots/osticketinst (3).png" alt="osTicket Installation Step 3" width="400"> <img src="screenshots/osticketinst (4).png" alt="osTicket Installation Step 4" width="400"> </br>
<img src="screenshots/osticketinst (5).png" alt="osTicket Installation Step 5" width="400">

### Ticket Workflow
User Actions
 - Accessed `http://192.168.56.104/osticket` from the User VM.
 - Submitted a new ticket with issue details. </br>
<img src="screenshots/userticketform.png" alt="User Ticket Form" width="400"> <img src="screenshots/userticketconform.png" alt="User Ticket Confirmation" width="400"> </br>

Technician Actions
 - Logged into the Staff Control Panel at `http://192.168.56.104/osticket/scp`
 - Viewed, responded to, and resolved the submitted ticket.
</br>

<img src="screenshots/Staffcontrol.png" alt="Staff Control Panel" width="400"> <img src="screenshots/staffresponse.png" alt="Staff Ticket Response" width="400"> </br>
<img src="screenshots/Staffreply.png" alt="Staff Ticket Reply" width="400"> <img src="screenshots/Ticketresolved.png" alt="Ticket Resolved" width="400"> </br>
<img src="screenshots/osticketstaffdashboard.png" alt="Staff Dashboard" width="500">

### How to Reproduce
1. Clone this repository.
2. Follow the setup steps described in the IT Support Lab Report.
3. Test the helpdesk system using the provided configuration steps.

### Conclusion
This project replicates a real-world IT helpdesk environment. It demonstrates skills in networking, Linux administration, database management, and helpdesk workflows. It can be extended further by integrating email notifications and automation for advanced IT support simulations.
