# SSH

Connecting to a remote server with SSH key-based authentication, generating
an RSA key pair, and configuring the local SSH client to skip password auth.

## Requirements

- Interpreted on Ubuntu 20.04 LTS
- Bash scripts start with `#!/usr/bin/env bash`, are executable, and have a
  comment on the second line explaining what they do

## Tasks

| File | Description |
| --- | --- |
| `0-use_a_private_key` | Connects to the server via `ssh` using the private key `~/.ssh/school` (single-character flags only, no `-l`) |
| `1-create_ssh_key_pair` | Generates a 4096-bit RSA key pair named `school`, protected by the passphrase `betty` |
| `2-ssh_config` | Local SSH client config: use `~/.ssh/school` as the identity file, refuse password authentication |
| Task 3 ("Let me in!") | No file — the reviewer's public key is appended to `~/.ssh/authorized_keys` directly on the live server (see below) |

## Note on task 3

Task 3 has no script. On the server itself:

```
echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNdtrNGtTXe5Tp1EJQop8mOSAuRGLjJ6DW4PqX4wId/Kawz35ESampIqHSOTJmbQ8UlxdJuk0gAXKk3Ncle4safGYqM/VeDK3LN5iAJxf4kcaxNtS3eVxWBE5iF3FbIjOqwxw5Lf5sRa5yXxA8HfWidhbIG5TqKL922hPgsCGABIrXRlfZYeC0FEuPWdr6smOElSVvIXthRWp9cr685KdCI+COxlj1RdVsvIo+zunmLACF9PYdjB2s96Fn0ocD3c5SGLvDOFCyvDojSAOyE70ebIElnskKsDTGwfT4P6jh9OBzTyQEIS2jOaE5RQq4IB4DsMhvbjDSQrP0MdCLgwkN" >> ~/.ssh/authorized_keys
```
