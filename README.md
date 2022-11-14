# Mikrotik-Scripts
Useful scripts for use as an edge RouterOS device

# Installation

1. In the RouterOS WebGUI (doing this via CLI will make you want to do unspeakable things to people), System > Scripts > Add New

2. Follow the configuration requirements for each script below

## Cloudflare-DDNS

Depends on [Mikrotik JSON Parser](https://github.com/Winand/mikrotik-json-parser) *(if repo is unavailable, please open an issue and I'll provide the script)

1. Install [python-cloudflare](https://github.com/cloudflare/python-cloudflare)

```$ sudo apt install python-pip && sudo pip install cloudflare```

2. Edit the cloudflare-api.py to enter your domain you want to find the IDs for, your email, and global API key

3. Run the cloudflare-api.py to get your zone IDs and record IDs

4. Edit the RouterOS script according to your domains and specifications

```$ python cloudflare-api.py```

RouterOS Config Requirements:
```
Don't Require Permissions: UNCHECKED
Policy: Read, Write, Test
```

## wake-on-lan

1. Edit the RouterOS according to the interface the device is on and the MAC Address of the NIC

RouterOS Config Requirements:
```
Don't Require Permissions: UNCHECKED
Policy: Read, Test
```
