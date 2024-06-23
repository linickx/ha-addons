# Documentation

## Installation

🚨 Warning: Home Detector is only support on 64bit processors, i.e. x86_64 (`amd64`) or ARM64 (`aarch64`) this is due to modern cryptography libraries (_used by Open Canary_) requiring rust which is not provided in the base python/alpine 32bit docker images. For Raspberry Pi users, that means Pi 4 or newer.

## Example Automations

### Delayed Start

An example automation for starting up Home Detector 30sec after boot: [automation_delayed_start.yml](https://github.com/linickx/HomeDetector/blob/main/homedetector/docs/automation_delayed_start.yml)

### Notify via webhook

Example automation for generating custom alerts via the webhook: [automation_webhook_notify.yml](https://github.com/linickx/HomeDetector/blob/main/homedetector/docs/automation_webhook_notify.yml)
