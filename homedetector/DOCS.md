# Documentation

## Installation

🚨 Warning: Home Detector is only support on 64bit processors, i.e. x86_64 (`amd64`) or ARM64 (`aarch64`) this is due to modern cryptography libraries (_used by Open Canary_) requiring rust which is not provided in the base python/alpine 32bit docker images. For Raspberry Pi users, that means Pi 4 or newer.

## Setting up DNS Anomaly Detection

By default DNS inspection is disabled, that is DNS requests pass-through without any anomaly detection, you must designate devices you wish to inspect, below is an example for setting __Local IoT Networks__:

```
- address: 192.168.1.10
  type: host
- address: 192.168.1.20-192.168.1.25
  type: range
- address: 192.168.2.0/24
  type: subnet
```
### Upstream DNS Servers

By default Home Detector will use Home Assistant DNS server, you can change this like so...

```
- server: 8.8.8.8
  port: 53
- server: 1.1.1.1
  port: 53
```
If you run _another_ DNS server on Home Assistant, like Pi-hole or DNSguard you need to grab their local name and use that, e.g for [my DNSCrypt addon](https://github.com/linickx/addon-dnscrypt-proxy)

```
- server: ba53f40c-dnscrypt-proxy
  port: 53
```
### Custom DNS Host Records (A)

If you need something resolvable, you can avoid it being sent upstream by creating custom A records:
```
- name: homeassistant.internal
  address: 192.168.1.1
```

### DNS Firewall (Blocking)

By default **nothing is blocked**. If you wish to enable DNS Blocking, toggle this to on.

### Unknown IP Action

By default, only _configured_ IPs are subject to inspection. You can enable it for _all_ with this toggle, however *IMPORTANT NOTE* laptops/phone are incredibly noisy, as soon as 30days (learning mode) is up, an alert will be created for every new site visited, you probably don't want that ;)

### Learning Mode Duration & Network Scope TTL (Time to Live)

Anomaly detection works by recording all the DNS requests for a fixed period of time and then once over alerting when there is a deviation from this baseline.

* Learning Mode Duration -> Default 30days -> How long to create the baseline
* Network Scope TTL -> How often the Source IP should be re-validated to check it's learning status

### Manually Changing the status of a Domain (Query)

To manually update a Scope from Learning to Alerting/Blocking:

1. Open the [Home Detector Dashboard](https://my.home-assistant.io/redirect/supervisor_ingress/?addon=ba53f40c_homedetector) select `DNS`
2. Click "pass" and change to "block"

___NOTE___: Keyword "block" will _alert_ if DNS firewalling is disabled.

### Manually Changing the status of a scope

To manually update a Scope from Learning to Alerting/Blocking:

1. Open the [Home Detector Dashboard](https://my.home-assistant.io/redirect/supervisor_ingress/?addon=ba53f40c_homedetector) select `Tuning`
2. Click "learning" and change to "block"

___NOTE___: Keyword "block" will _alert_ if DNS firewalling is disabled.

## Honey Pot Setup

By default, Telnet (TCP/23) is enabled.

* Enable the HTTP Honeypot by Setting a Port -> 80
* Enable the FTP Honeypot by Setting a Port -> 21

Currently Open Canary cannot be customized.

## Example Automations

The following automations are [available in the docs](https://github.com/linickx/HomeDetector/tree/main/docs) folder:

### Delayed Start

An example automation for starting up Home Detector 30sec after boot: [automation_delayed_start.yml](https://github.com/linickx/HomeDetector/blob/main/homedetector/docs/automation_delayed_start.yml)

### Notify via webhook

Example automation for generating custom alerts via the webhook: [automation_webhook_notify.yml](https://github.com/linickx/HomeDetector/blob/main/homedetector/docs/automation_webhook_notify.yml)
