# DNS Zone File Template

This is a customizable DNS zone file template for BIND, designed for local lab or production use.

## How to use

1. Copy this template and rename it to your zone file, e.g., `lab.prod.zone`.
2. Replace all `<domain>`, `<ns_ip_address>`, `<server1_ip_address>`, etc. placeholders with your actual domain name and IP addresses.
3. Update the serial number each time you modify the zone file to ensure DNS servers recognize the changes.
4. Place the zone file in the appropriate directory on your DNS server (e.g., `/var/named/`).
5. Reference the zone file in your BIND configuration (`named.conf`).

## Notes

- The SOA record defines the primary DNS server and admin contact.
- NS records define authoritative DNS servers for the domain.
- A records map hostnames to IPv4 addresses.
- Optional records include CNAME, MX, and TXT for aliases, mail servers, and text information.
- Remember to increment the serial number after every edit (usually with date and revision).

## Example

```zone
; Sample record
server1 IN A 192.168.1.10
