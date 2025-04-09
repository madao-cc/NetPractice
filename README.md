# NetPractice

> **Objective:** Learn the fundamentals of computer networking by solving various network configuration problems using IP addressing, subnetting, and routing concepts.

---

## 📘 Table of Contents

- [What is NetPractice?](#what-is-netpractice)
- [What You Will Learn](#what-you-will-learn)
- [Project Interface Overview](#project-interface-overview)
- [Key Networking Concepts](#key-networking-concepts)
  - [1. IP Address](#1-ip-address)
  - [2. Subnet Mask](#2-subnet-mask)
  - [3. Network Address](#3-network-address)
  - [4. Broadcast Address](#4-broadcast-address)
  - [5. Gateway (Router)](#5-gateway-router)
  - [6. NAT (Network Address Translation)](#6-nat-network-address-translation)
  - [7. DNS](#7-dns)
- [How to Solve NetPractice Exercises](#how-to-solve-netpractice-exercises)
  - [Step-by-Step Strategy](#step-by-step-strategy)
- [Example Walkthrough](#example-walkthrough)
- [Tips and Common Errors](#tips-and-common-errors)
- [Useful Resources](#useful-resources)

---

## 🧠 What is NetPractice?

**NetPractice** is a 42 project that introduces you to basic **network engineering and architecture**.

You’ll be given diagrams with various devices (computers, routers, NATs, DNS servers), and you must **assign IPs, subnet masks, gateways, and routes** so that all the computers can communicate as expected.

Everything is done in the **web interface**, so no actual code or Linux terminal is needed.

---

## 🎯 What You Will Learn

By completing NetPractice, you’ll understand:

- How IP addresses and subnet masks work
- How computers communicate inside and outside their networks
- How routing and gateways function
- The purpose of NATs and DNS in real networks
- How to troubleshoot common networking issues

---

## 🖥️ Project Interface Overview

When you open an exercise on the 42 intranet or using the subject’s link:

- You will see **PCs**, **Routers**, **NATs**, **DNS servers**, and **Internet clouds**
- Your task is to **click each node** and **configure** its IP, mask, and routes.
- At the bottom, there’s a **"Check"** button to validate your solution.

---

## 🧩 Key Networking Concepts

### 1. IP Address
A **unique identifier** for a device on a network.

Example: `192.168.1.1`

### 2. Subnet Mask
Used to divide an IP into **network and host parts**. Common masks:

- `255.255.255.0` (or `/24`): 256 addresses (254 usable)
- `255.255.0.0` (or `/16`): 65,536 addresses

### 3. Network Address
The **first address** of a subnet, used to identify the network.

If you have `192.168.1.1/24` → Network address is `192.168.1.0`

### 4. Broadcast Address
The **last address** of a subnet, used to send data to **all** hosts in the network.

For `192.168.1.1/24` → Broadcast is `192.168.1.255`

### 5. Gateway (Router)
A device that connects **different networks**. Hosts use it to reach other subnets.

Each router has **two or more interfaces**, each in a **different network**.

### 6. NAT (Network Address Translation)
Translates a **private IP** (like `192.168.x.x`) into a **public IP** for Internet access.

You configure:
- **Internal network (private IP range)**
- **External IP (public)**

### 7. DNS
A **Domain Name System** server resolves hostnames (like `google.com`) to IPs.

You must set a DNS IP on the PCs, and it must be reachable.

---

## 🧑‍🔧 How to Solve NetPractice Exercises

### Step-by-Step Strategy

1. **Understand the diagram**
   - Identify each subnet and what devices are connected
   - Identify routers, NATs, DNS servers, and endpoints

2. **Assign IP addresses**
   - For each subnet, choose a consistent IP scheme (e.g., `192.168.1.1`, `192.168.1.2`, ...)

3. **Set subnet masks**
   - Usually `/24` (255.255.255.0) unless otherwise needed

4. **Configure routers**
   - Each interface must be in the correct subnet
   - Add **routes** when needed (from this router to other networks)

5. **Set gateways on PCs**
   - The gateway must be the **router IP on the same subnet**

6. **Configure NAT if needed**
   - Set the internal network and assign an external IP

7. **Set DNS settings**
   - Make sure PCs can **ping the DNS IP**
   - Then try the hostname (e.g., `ping google.com`)

8. **Test connectivity**
   - Use the "Ping" tool in the interface
   - Ping from each PC to others, to DNS, and to the Internet

---

## 🧪 Example Walkthrough

### 📘 Example: Two PCs on different subnets with a router

**Setup:**

- PC1 (in subnet A)
- PC2 (in subnet B)
- Router (one interface on A, one on B)

**Steps:**

1. Assign:
   - PC1 → IP: `192.168.1.2/24`, Gateway: `192.168.1.1`
   - Router eth0 (A side): `192.168.1.1/24`
   - Router eth1 (B side): `192.168.2.1/24`
   - PC2 → IP: `192.168.2.2/24`, Gateway: `192.168.2.1`

2. No need for extra routing: the router automatically knows both networks.

3. Now both PCs can ping each other!

---

## ⚠️ Tips and Common Errors

| Problem                          | Solution                                                        |
|----------------------------------|------------------------------------------------------------------|
| Can't ping another PC            | Check subnet masks and gateways                                 |
| Router not forwarding packets    | Check both interfaces have correct IPs and are in right subnets |
| DNS not resolving hostname       | Make sure DNS IP is correct and reachable                       |
| NAT not working                  | Internal network must match the PC's subnet                     |
| Forgetting routes on routers     | Add manual routes when needed to reach other networks           |

---

## 📚 Useful Resources

- [Subnetting made easy](https://www.davidbombal.com/subnetting/)
- [Cisco Packet Tracer tutorials (YouTube)](https://www.youtube.com/results?search_query=cisco+packet+tracer+basic)
- [Visual Subnet Calculator](https://www.davidc.net/sites/default/subnets/subnets.html)
- [IP subnet cheat sheet](https://www.aelius.com/njh/subnet_sheet.html)

---

## 🏁 Summary

To succeed in NetPractice:

✅ Learn how IP addresses and subnets work  
✅ Know how to configure gateways, routes, and NATs  
✅ Understand the flow of data between hosts  
✅ Use the tools in the UI to test and debug  
✅ Practice subnetting until it's second nature  
