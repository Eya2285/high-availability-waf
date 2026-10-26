# High-Availability Open-Source Web Application Firewall

Academic cybersecurity project implementing a high-availability Web Application Firewall (WAF) architecture in a virtualized lab environment.

## Project objectives

- Protect web applications using ModSecurity and the OWASP Core Rule Set (CRS).
- Configure Apache as an HTTPS reverse proxy.
- Explore high availability using Keepalived and VRRP.
- Distribute application traffic across Juice Shop instances.
- Document security validation and service continuity tests.

## Architecture

The lab includes:

- **WAF1:** primary WAF node.
- **WAF2:** secondary WAF node.
- **Backend:** web application services.
- **Virtual IP (VIP):** shared service address managed by Keepalived/VRRP.

The repository contains example configurations with sanitized addresses and placeholder secrets. Adapt them to your environment before deployment.

## Technologies

- Red Hat Enterprise Linux (RHEL)
- Apache HTTP Server
- ModSecurity
- OWASP Core Rule Set (CRS)
- Keepalived / VRRP
- VMware
- Docker
- OWASP Juice Shop

## Repository structure

```text
.
|-- configs/
|   |-- apache/
|   |-- keepalived/
|   `-- modsecurity/
|-- docs/
|-- scripts/
|-- screenshots/
|-- .gitignore
`-- README.md
## Security considerations

- Never commit private keys, credentials, access tokens or real VRRP passwords.
- Review all configuration files before publishing.
- Example configurations may require adaptation before use.
- Restrict access to security logs and monitoring endpoints.

## Limitations

The architecture uses two WAF nodes. If both WAF nodes become unavailable, the service exposed through the virtual IP may become unavailable. Resilience also depends on the backend and application configuration.

## Validation

Document results and screenshots for:
- HTTPS access through the virtual IP.
- ModSecurity request filtering.
- WAF failover when a node becomes unavailable.
- Backend availability and recovery.

Only report tests that have actually been performed.

## Authors

**Eya GARA** 

Cybersecurity Engineering Project - TEK-UP University.
