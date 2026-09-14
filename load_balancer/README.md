# Load Balancer

Doubling web server capacity and putting HAProxy in front of them for
round-robin traffic distribution.

## Requirements

- Interpreted on Ubuntu 16.04 LTS
- Bash scripts start with `#!/usr/bin/env bash`, are executable, have a
  comment on the second line, and pass shellcheck

## Tasks

| File | Description |
| --- | --- |
| `0-custom_http_response_header` | Adds an `X-Served-By: <hostname>` response header to nginx (run on both web-01 and web-02) |
| `1-install_load_balancer` | Installs and configures HAProxy on lb-01 with round-robin balancing across web-01 and web-02 |

## Before running these

1. Both web-01 and web-02 need their hostnames set to `<student_id>-web-01`
   and `<student_id>-web-02` respectively (see the tutorial linked in the
   project if not already configured).
2. `1-install_load_balancer` has placeholders `WEB01_IP_HERE` and
   `WEB02_IP_HERE` — replace these with the real IPs from the intranet's
   "my servers" page before running it on lb-01.

## Servers

- web-01: `ubuntu@3.83.48.135` (confirmed)
- web-02: not yet provisioned in "my servers"
- lb-01: not yet provisioned in "my servers"
