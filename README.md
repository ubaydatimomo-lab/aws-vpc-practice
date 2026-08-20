# AWS VPC Infrastructure & Custom Web Server Project

A hands-on AWS networking project demonstrating the creation of a custom Virtual Private Cloud (VPC), public and private subnet architecture, routing controls, and automated web server deployment.

---

## Architecture Overview

The infrastructure for this project was built from scratch in AWS:

* **VPC CIDR:** `10.0.0.0/24` (256 Total IPs)
* **Subnet Layout:**
  * **Public Subnet 1:** `10.0.0.0/26` (AZ-A)
  * **Public Subnet 2:** `10.0.0.64/26` (AZ-B)
  * **Private Subnet 1:** `10.0.0.128/26` (AZ-A)
  * **Private Subnet 2:** `10.0.0.192/26` (AZ-B)
* **Internet Gateway (IGW):** Attached to the VPC to route public subnet traffic to the internet.
* **Route Tables:** 
  * `Public Route Table`: Associated with public subnets, routing `0.0.0.0/0` to the IGW.
  * `Private Route Table`: Isolated subnets.

---

## Features & Deployment

1. **Custom Networking:** High-availability subnets partitioned across multiple Availability Zones.
2. **Security Controls:** Security group configured allowing restricted **SSH (Port 22)** and **HTTP (Port 80)** traffic.
3. **Apache Web Server:** Configured on an Amazon Linux EC2 instance to serve custom landing pages.
4. **Verified Connectivity:** Confirmed inbound/outbound traffic flow through the public subnet routing table.

---

## Verification

* Verified successful HTTP response over Port 80.
* Verified SSH connectivity via public key authentication.
* Resources safely destroyed post-testing to maintain zero cloud costs.
