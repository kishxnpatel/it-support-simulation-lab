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
2. **Technician VM (Windows 10)** – Simulated IT support staff responding to tickets.  
3. **User VM (Windows 10)** – Simulated an end-user submitting tickets.

### Network Configuration
- **Internal Network and Host-Only Adapter** enabled communication between VMs.  
- Static IPs assigned:
  - Linux Mint: 192.168.56.104
  - Technician VM: 192.168.56.101
  - User VM: 192.168.56.102
- Connectivity tested successfully using ping commands.

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
FLUSH PRIVILEGES;

