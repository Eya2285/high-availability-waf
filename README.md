@'
# High-Availability Open-Source Web Application Firewall

Academic cybersecurity project implementing a high-availability Web Application Firewall (WAF) architecture in a virtualized lab environment.

## Objectives

- Protect a web application using ModSecurity and OWASP Core Rule Set (CRS).
- Configure Apache as an HTTPS reverse proxy.
- Explore high availability using Keepalived and VRRP.
- Test web attack filtering and service continuity during component failures.

## Architecture

The laboratory architecture consists of:

- WAF1: primary WAF node.
- WAF2: secondary WAF node.
- Backend: web application server.
- Virtual IP (VIP): shared service address managed through Keepalived/VRRP.

## Technologies

- Red Hat Enterprise Linux (RHEL)
- Apache HTTP Server
- ModSecurity
- OWASP Core Rule Set (CRS)
- Keepalived / VRRP
- VMware
- OWASP Juice Shop

## Repository Structure

```text
.
├── configs/
│   ├── apache/
│   ├── modsecurity/
│   └── keepalived/
├── docs/
├── scripts/
├── screenshots/
├── .gitignore
└── README.md
