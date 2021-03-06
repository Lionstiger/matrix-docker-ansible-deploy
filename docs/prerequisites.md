# Prerequisites

- **CentOS** (7.0+), **Debian** (9/Stretch+) or **Ubuntu** (16.04+) server. This playbook can take over your whole server or co-exist with other services that you have there.

- [Python](https://www.python.org/) being installed on the server. Most distributions install Python by default, but some don't (e.g. Ubuntu 18.04) and require manual installation (something like `apt-get install python`).

- the [Ansible](http://ansible.com/) program being installed on your own computer. It's used to run this playbook and configures your server for you. Take a look at [our guide about Ansible](ansible.md) for [version requirements](ansible.md#supported-ansible-versions) or alternative ways to run Ansible.

- either the `dig` tool or `python-dns` installed on your own computer. Used later on, by the playbook's [services check](maintenance-checking-services.md) feature.

- an HTTPS-capable web server at the base domain name (`<your-domain>`) which is capable of serving static files (unless you decide to use DNS SRV records for [Server Delegation](howto-server-delegation.md))

- properly configured DNS records for `<your-domain>` (details in [Configuring DNS](configuring-dns.md))

- some TCP/UDP ports open. This playbook configures the server's internal firewall for you. In most cases, you don't need to do anything special. But **if your server is running behind another firewall**, you'd need to open these ports: `80/tcp` (HTTP webserver), `443/tcp` (HTTPS webserver), `3478/tcp`  (STUN over TCP), `3478/udp` (STUN over UDP), `8448/tcp` (Matrix Federation API HTTPS webserver), `49152-49172/udp` (TURN over UDP).

When ready to proceed, continue with [Configuring DNS](configuring-dns.md).
