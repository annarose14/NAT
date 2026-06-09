# NAT

# NAT Network System

A Network Address Translation (NAT) system implemented in Python,
built as part of COMP9331 (Computer Networks) at UNSW Sydney.

## What It Does

This program simulates a real NAT device (like your home router) that:
- Translates private IP addresses to a single public IP address
- Manages a translation table with configurable timeouts
- Handles UDP fragmentation and reassembly
- Generates ICMP error messages
- Processes packets from multiple simultaneous connections

## How to Run

```bash
python3 nat.py <external_ip> <num_ports> <timeout> <mtu> <internal_port> <nexthop_port>
```

**Example:**
```bash
python3 nat.py 192.0.2.1 5 30 576 57713 60893
```

## Project Structure

| File | Purpose |
|------|---------|
| `nat.py` | Main program — event loop and packet forwarding |
| `packets.py` | IP/UDP/ICMP packet parsing and construction |
| `translation.py` | NAT translation table and fragment buffer |

## Concepts Covered

- IPv4 addressing and packet structure
- UDP socket programming
- Network Address Port Translation (NAPT)
- Internet checksum algorithm (RFC 1071)
- IP fragmentation and reassembly
- ICMP error message generation
- Asynchronous I/O with `select()`

## Tech Stack

- Python 3
- Standard library only (`socket`, `struct`, `select`, `threading`)
