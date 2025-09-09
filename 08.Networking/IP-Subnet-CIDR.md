# 📘 Networking Basics: IP Address, Subnet, and CIDR

A simple guide to understanding fundamental networking concepts — useful for Linux networking, system administration, DevOps, and general networking knowledge.

---

## 🌐 IP Address

An **IP address** (Internet Protocol address) is a unique identifier for a device on a network.

- **IPv4 Example**: `192.168.1.10`
- **IPv6 Example**: `2001:db8::1`

Each IP address consists of:
- A **network portion** (identifies the network)
- A **host portion** (identifies the device on that network)

> 📌 Example:
> ```
> IP Address: 192.168.1.10
> ```

---

## 🧩 Subnet

A **subnet** (short for *subnetwork*) is a logically visible subdivision of an IP network.

Subnets help:
- Organize networks
- Improve performance
- Enhance security

A **subnet mask** defines how many bits belong to the network and how many to hosts.

> 📌 Example:
> ```
> IP Address:    192.168.1.10
> Subnet Mask:   255.255.255.0
> Network:       192.168.1.0
> Host Range:    192.168.1.1 - 192.168.1.254
> Broadcast:     192.168.1.255
> ```

---

## 🧮 CIDR (Classless Inter-Domain Routing)

**CIDR** is a compact way to represent IP addresses and their associated subnet masks.

- **Format**: `<IP address>/<prefix length>`
- The prefix length specifies how many bits are used for the **network** part

> 📌 Example:
> ```
> CIDR Notation: 192.168.1.0/24
> Subnet Mask:   255.255.255.0
> Total IPs:     256
> Usable IPs:    254 (excluding network and broadcast)
> ```

---

## 📊 CIDR and Subnet Mask Reference Table

| CIDR     | Subnet Mask       | Total IPs | Usable IPs | Typical Use             |
|----------|-------------------|-----------|------------|--------------------------|
| /30      | 255.255.255.252   | 4         | 2          | Point-to-point links     |
| /29      | 255.255.255.248   | 8         | 6          | Very small networks      |
| /28      | 255.255.255.240   | 16        | 14         | Small networks           |
| /24      | 255.255.255.0     | 256       | 254        | Standard home networks   |
| /16      | 255.255.0.0       | 65,536    | 65,534     | Large internal networks  |

---

## 🧰 Linux Command Examples (Bonus)

```bash
# View IP address
ip addr show

# Assign IP with CIDR
sudo ip addr add 192.168.1.100/24 dev eth0

# Bring interface up/down
sudo ip link set eth0 down
sudo ip link set eth0 up

# Check routing table
ip route
