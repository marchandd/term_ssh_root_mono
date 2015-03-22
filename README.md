# marchandd/term_ssh_root_mono

[marchandd/term_ssh_root_mono](https://registry.hub.docker.com/u/marchandd/term_ssh_root_mono/ "MarchandD") [Docker:copyright:](https://docs.docker.com/ "Docker") image

## Description

A sandbox container with last version of Mono environment ready to be exploited for Mono app from Linux or Windows host.

### Goal

Easy method to produce a light terminal containers to run Mono app into sandbox from secured host to remote client with SSH.  
Based from Docker official version image but not including mono-complete...

### Image size

Around 400 Mb.

### References

[Marchand D. Maintainer](https://github.com/marchandd/ "Maintainer")

[Details source](https://github.com/marchandd/term_ssh_root_mono/ "Details")

[Part of project studies](https://github.com/marchandd/docker_index/ "References")

## Build image

### Command line

:computer: `docker pull marchandd/term_ssh_root_mono`

### Firewall

:warning: If your Firewall is enabled on the host, with default outgoing policy turned to 
deny, 
you will have to disable 22 port filtering:  
- Make a new rule for OpenSSH (22/TCP) to enable outgoing policy.

## Build container

### Command line

:computer: `docker run -d -p XXX.XXX.XXX.XXX:YYYYY:22 marchandd/term_ssh_root_mono`

Where XXX.XXX.XXX.XXX is your IP v4 address.  
Where YYYYY is your Private port, if you doesn't know free port, try from 49200...

### Command line explanation

- Run in detached mode.
- Export port 22.

## Container usage

### SSH access

Open terminal with root/administrator account.
Basic fixed password for Docker public repository = 'term_ssh_root_mono'

:computer: `ssh -X root@XXX.XXX.XXX.XXX -p YYYYY`

## Explanations

### Dockerfile

- Make dynamic root password and display it into logs.
- Change config for SSH daemon.
- Give Supervisor management for OpenSSH server.
- Expose SSH port.

### Display

Make sure to have installed OpenSSH client or GUI SSH client (Putty).

### Risks

Root account from container is exposed.  
A password is used and not a certificate that could be more secure.
