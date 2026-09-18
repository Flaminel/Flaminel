# Automating things I refuse to do twice

Senior .NET / Backend engineer

A lot of what I build in my spare time starts with something in my homelab annoying me more than once.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/marius-nechifor)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/flaminel)

---

## Cleanuparr

[![Stars](https://img.shields.io/github/stars/Cleanuparr/Cleanuparr?style=for-the-badge&logo=github&color=e3b341&labelColor=1c1c1c)](https://github.com/Cleanuparr/Cleanuparr/stargazers)
[![Release](https://img.shields.io/github/v/release/Cleanuparr/Cleanuparr?style=for-the-badge&logo=github&color=4c8eda&labelColor=1c1c1c)](https://github.com/Cleanuparr/Cleanuparr/releases)
[![Downloads](https://img.shields.io/github/downloads/Cleanuparr/Cleanuparr/total?style=for-the-badge&logo=github&label=GitHub%20Downloads&color=3fb950&labelColor=1c1c1c)](https://github.com/Cleanuparr/Cleanuparr/releases)
[![Docker Pulls](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fghcr-badge.elias.eu.org%2Fapi%2FCleanuparr%2FCleanuparr%2Fcleanuparr&query=%24.downloadCount&style=for-the-badge&logo=docker&label=Docker%20Pulls&color=2496ed&labelColor=1c1c1c)](https://github.com/Cleanuparr/Cleanuparr/pkgs/container/cleanuparr)

An advanced download manager for the Servarr ecosystem built on the latest version of .NET, with a REST API, Quartz.NET background workers, and a modern UI built with the latest version of Angular. Available for Docker, Linux, Windows, and macOS.

---

## Homelab

```mermaid
flowchart TD
    MIKROTIK["Mikrotik hAP ax3"]

    subgraph HEIMDAL["Heimdal / Proxmox VE"]
        OPN["OPNsense<br/>routing&nbsp;&&nbsp;firewall"]
        subgraph DEBIANVM["Debian VM"]
            VAULT["HashiCorp Vault"]
        end
    end

    subgraph JARVIS["Jarvis / Debian"]
        subgraph K3S["k3s / single node"]
            MEDIA["Plex / Servarr stack"]
        end
    end

    subgraph HOMER["Homer / Raspberry Pi"]
        subgraph HAOS["Home Assistant OS"]
            AUTO["Home Automations"]
            ADGUARD["AdGuard"]
        end
    end

    MIKROTIK -->|192.168.1.0/24| OPN
    MIKROTIK -->|192.168.1.0/24| HOMER
    OPN -->|192.168.2.0/24| DEBIANVM
    OPN -->|192.168.2.0/24| JARVIS
    MEDIA -.->|secrets| VAULT
    MIKROTIK -.->|DNS| ADGUARD
```
