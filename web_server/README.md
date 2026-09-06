# Web Server

Automating server configuration: transferring files, installing and
configuring nginx, DNS, HTTP redirects, and custom error pages.

## Requirements

- Interpreted on Ubuntu 16.04 LTS (tested here against Ubuntu 24.04's
  nginx/shellcheck as the closest available equivalent)
- All Bash scripts start with `#!/usr/bin/env bash`, are executable, and
  have a comment on the second line
- Scripts pass shellcheck with no errors
- No `systemctl` — uses `service` instead
- Scripts are idempotent: safe to re-run on an already-configured server
  without breaking nginx (a pristine copy of the default config is kept
  and restored before each `sed` edit)

## Tasks

| File | Description |
| --- | --- |
| `0-transfer_file` | Transfers a file to a remote server's home directory via `scp` (4 args: file, IP, username, SSH key; strict host key checking disabled) |
| `1-install_nginx_web_server` | Installs nginx, serves "Holberton School" on `/` |
| `2-setup_a_domain_name` | Contains the registered `.tech` domain name pointing to web-01 |
| `3-redirection` | Adds a 301 redirect from `/redirect_me` on top of task 1 |
| `4-not_found_page_404` | Adds a custom 404 page ("Ceci n'est pas une page") on top of task 3 |
| `5-*` | Custom-designed 404 page (must still contain "Ceci n'est pas une page") |

## Server

- Name: `7206-web-01`
- User: `ubuntu`
- IP: `3.83.48.135`

## Note on task 2

Registering a `.tech` domain and setting DNS records is a manual step done
through the .TECH Domains / GitHub Student Pack flow described in the
project — there's no script for it. The answer file just contains the
domain name itself, e.g.:

```
yourdomain.tech
```
