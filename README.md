# IPv4-Addressing-Foundations-Networking-Fundamentals
Assignment intends to show that you can recognize IPv4 address classes, apply default subnet masks, identify network and broadcast addresses, and check whether a default gateway belongs to the correct network.
IPv4 Addressing Foundations

## Networking Fundamentals

**Assessment:** Individual Assignment done by OMOWUMI Omolola Sharon
**Total Marks:** 50
**Suggested Time:** 60 minutes
**Topic:** Classful IPv4 Addressing

---

# Part A: Core Concepts

## 1. Define an IPv4 Address and Explain Why the Address Must Be Unique

An **IPv4 address** is a 32-bit logical address assigned to a device or network interface. It identifies the device on an IP network and allows data to be delivered to the correct destination.

Each device on the same network must have a **unique IP address** to prevent address conflicts and communication problems.

---

## 2. Flat vs. Hierarchical Addressing

**Flat addressing** uses identifiers without dividing them into levels or groups, while **hierarchical addressing** divides information into levels that make networks easier to organize and manage.

| Addressing Type             | Example                                                |
| --------------------------- | ------------------------------------------------------ |
| **Flat addressing**         | MAC address                                            |
| **Hierarchical addressing** | IPv4 address, which contains network and host portions |

---

## 3. Static vs. Dynamic IP Addressing

| Type                   | Description                                                                       | Example / Protocol                             |
| ---------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------- |
| **Static addressing**  | An IP address is manually configured and normally remains assigned to the device. | Manually configured IP address                 |
| **Dynamic addressing** | An IP address is automatically assigned to a device for a period of time.         | **DHCP — Dynamic Host Configuration Protocol** |

---

## 4. Classful vs. Classless Addressing

### Difference Between Classful and Classless Addressing

| Type                     | Description                                                                                                           |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| **Classful addressing**  | Uses fixed address classes such as A, B, and C with predefined default subnet masks.                                  |
| **Classless addressing** | Allows networks to use variable prefix lengths instead of being restricted to the traditional A, B, and C boundaries. |
| **CIDR**                 | **Classless Inter-Domain Routing**                                                                                    |

---

## 5. IPv4 Configuration Items

The four IPv4 configuration items presented in the lesson for normal name-based Internet access are:

1. **IP address** – Identifies the device on the network.
2. **Subnet mask** – Identifies the network and host portions of the address.
3. **Default gateway** – Provides the route to other networks.
4. **DNS server** – Translates domain names into IP addresses.

---

# Part B: Classful Address Identification

## IPv4 Address Classification

| IPv4 Address      | Class   | Network & Host Pattern | Default Subnet Mask |
| ----------------- | ------- | ---------------------- | ------------------- |
| **23.14.6.9**     | Class A | N.H.H.H                | **255.0.0.0**       |
| **145.80.12.200** | Class B | N.N.H.H                | **255.255.0.0**     |
| **198.51.100.27** | Class C | N.N.N.H                | **255.255.255.0**   |
| **9.200.10.1**    | Class A | N.H.H.H                | **255.0.0.0**       |
| **188.44.9.72**   | Class B | N.N.H.H                | **255.255.0.0**     |

## Classful Rules Used

| Class | First-Octet Range | Network/Host Pattern | Default Mask  |
| ----- | ----------------: | -------------------- | ------------- |
| **A** |             0–127 | N.H.H.H              | 255.0.0.0     |
| **B** |           128–191 | N.N.H.H              | 255.255.0.0   |
| **C** |           192–223 | N.N.N.H              | 255.255.255.0 |

---

# Part C: Network and Broadcast Analysis

## 1. Address: 34.72.6.19

The first octet is **34**, which falls within the **Class A** range. Therefore, the default subnet mask is **255.0.0.0**.

| Item                     | Answer                   |
| ------------------------ | ------------------------ |
| **IP Address**           | 34.72.6.19               |
| **Class**                | Class A                  |
| **Default Subnet Mask**  | 255.0.0.0                |
| **Network Address**      | **34.0.0.0**             |
| **Broadcast Address**    | **34.255.255.255**       |
| **First Usable Host**    | **34.0.0.1**             |
| **Last Usable Host**     | **34.255.255.254**       |
| **Maximum Usable Hosts** | **2²⁴ − 2 = 16,777,214** |

---

## 2. Address: 150.20.7.200

The first octet is **150**, which falls within the **Class B** range. Therefore, the default subnet mask is **255.255.0.0**.

| Item                     | Answer               |
| ------------------------ | -------------------- |
| **IP Address**           | 150.20.7.200         |
| **Class**                | Class B              |
| **Default Subnet Mask**  | 255.255.0.0          |
| **Network Address**      | **150.20.0.0**       |
| **Broadcast Address**    | **150.20.255.255**   |
| **First Usable Host**    | **150.20.0.1**       |
| **Last Usable Host**     | **150.20.255.254**   |
| **Maximum Usable Hosts** | **2¹⁶ − 2 = 65,534** |

---

## 3. Address: 203.0.113.44

The first octet is **203**, which falls within the **Class C** range. Therefore, the default subnet mask is **255.255.255.0**.

| Item                     | Answer            |
| ------------------------ | ----------------- |
| **IP Address**           | 203.0.113.44      |
| **Class**                | Class C           |
| **Default Subnet Mask**  | 255.255.255.0     |
| **Network Address**      | **203.0.113.0**   |
| **Broadcast Address**    | **203.0.113.255** |
| **First Usable Host**    | **203.0.113.1**   |
| **Last Usable Host**     | **203.0.113.254** |
| **Maximum Usable Hosts** | **2⁸ − 2 = 254**  |

---

# Part D: Applied Troubleshooting

## 1. Network Address and Broadcast Address

The workstation has the address **201.110.213.28** with a subnet mask of **255.255.255.0**.

| Item                       | Answer              |
| -------------------------- | ------------------- |
| **Workstation IP Address** | 201.110.213.28      |
| **Subnet Mask**            | 255.255.255.0       |
| **Network Address**        | **201.110.213.0**   |
| **Broadcast Address**      | **201.110.213.255** |

The first three octets identify the network, while the final octet is the host portion.

---

## 2. Is the Configured Default Gateway Valid?

**No, the configured default gateway is not valid.**

The workstation belongs to the **201.110.213.0/24** network, while the configured gateway **201.110.214.1** belongs to the **201.110.214.0/24** network.

With the subnet mask **255.255.255.0**, the workstation and gateway must be on the same network for the workstation to communicate with the router.

Therefore, **201.110.214.1 is not a valid default gateway for this workstation**.

---

## 3. Valid Default Gateway

One valid default gateway address would be **201.110.213.1**, assuming that the address is actually assigned to the router and is not already in use by another device.

| Item                                         | Answer                                                            |
| -------------------------------------------- | ----------------------------------------------------------------- |
| **Valid Default Gateway**                    | **201.110.213.1**                                                 |
| **Valid Host Range**                         | 201.110.213.1 – 201.110.213.254                                   |
| **Network Address**                          | 201.110.213.0                                                     |
| **Broadcast Address**                        | 201.110.213.255                                                   |
| **Why the Network Address Cannot Be Used**   | It identifies the entire network rather than an individual host.  |
| **Why the Broadcast Address Cannot Be Used** | It is reserved to send traffic to all hosts on the local network. |

Therefore, **201.110.213.1** is a valid example of a default gateway.

---

## 4. Communication With the Incorrect Gateway

| Communication                                      | Expected Result    | Reason                                                                                        |
| -------------------------------------------------- | ------------------ | --------------------------------------------------------------------------------------------- |
| **Communication with devices on 201.110.213.0/24** | **May work**       | Devices on the same local network can communicate directly without using the default gateway. |
| **Communication with devices on another network**  | **Likely to fail** | Traffic to remote networks requires a valid default gateway.                                  |
| **Internet access**                                | **Likely to fail** | The workstation cannot correctly forward traffic to the router.                               |
| **Access to 8.8.8.8**                              | **Likely to fail** | 8.8.8.8 is outside the local network and requires a working gateway.                          |

---

## 5. Recommended Addressing for 25 Student Computers

**Dynamic addressing is recommended.**

The computers can receive their IP addresses automatically from a **DHCP (Dynamic Host Configuration Protocol) server**.

Using DHCP reduces the amount of manual configuration required and helps prevent duplicate IP addresses.

---

# Summary

This assignment covered the fundamentals of **IPv4 addressing**, including:

* IPv4 address structure and uniqueness
* Flat and hierarchical addressing
* Static and dynamic IP addressing
* DHCP
* Classful and classless addressing
* CIDR
* IPv4 configuration parameters
* Class A, B, and C addressing
* Default subnet masks
* Network and broadcast addresses
* Usable host ranges
* Default gateway troubleshooting
* DHCP-based network configuration

These concepts provide the foundation for understanding IPv4 network design, subnetting, routing, and network troubleshooting.
