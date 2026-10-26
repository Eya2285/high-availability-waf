# Backend Web Server

## Environment

- Operating system: Red Hat Enterprise Linux (RHEL)
- Web server: Apache HTTP Server (`httpd`)
- Apache DocumentRoot: `/var/www/html`
- HTTP service port: 80

## Web files

The backend contains the following application files:

- `index.html`: web dashboard
- `events.php`: event-related endpoint
- `status.php`: backend status endpoint

Backup files present in the VM are not included in this repository.

## Juice Shop containers

Three Docker containers run OWASP Juice Shop:

| Container | Host port | Container port |
|---|---:|---:|
| `juiceshop` | 3000 | 3000 |
| `juiceshop2` | 3001 | 3000 |
| `juiceshop3` | 3002 | 3000 |

## Verification commands

Check Apache:

```bash
sudo systemctl status httpd
sudo httpd -S
sudo docker ps
sudo ss -lntp

## Étape 2 — Vérifier et publier

Avant de publier, vérifie le nouveau fichier :

```powershell
Get-Content "configs\backend\README.md"
git status --short
git add configs\backend\README.md
git diff --cached --check
git diff --cached --stat

@'
# Backend Web Server

## Environment

- Operating system: Red Hat Enterprise Linux (RHEL)
- Web server: Apache HTTP Server (`httpd`)
- Apache DocumentRoot: `/var/www/html`
- HTTP service port: 80

## Web files

The backend contains these application files:

- `index.html`: web dashboard
- `events.php`: event-related endpoint
- `status.php`: backend status endpoint

Backup files are not included in this repository.

## Juice Shop containers

Three Docker containers run OWASP Juice Shop.

| Container | Host port | Container port |
|---|---:|---:|
| `juiceshop` | 3000 | 3000 |
| `juiceshop2` | 3001 | 3000 |
| `juiceshop3` | 3002 | 3000 |

## Verification commands

Check Apache:

```bash
sudo systemctl status httpd
sudo httpd -S
```

Check Docker containers:

```bash
sudo docker ps
```

Check listening ports:

```bash
sudo ss -lntp
```

## Security notes

- Do not publish credentials, tokens, private keys, or sensitive logs.
- Review PHP files before publishing them.
- This document describes the observed environment; it is not a deployment script.
