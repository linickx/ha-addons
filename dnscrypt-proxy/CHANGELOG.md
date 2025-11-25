# Releases

## 2025.11.25
Automated Rebuild triggered by [2025.11.2](https://github.com/home-assistant/docker-base/releases/tag/2025.11.2)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Bump actions/checkout from 5.0.0 to 6.0.0 (#329) @dependabot[bot]
Add reusable builder workflow (#328) @cdce8p
Tag Python 3.14-alpine3.22 images with the latest tag (#327) @sairon
Drop deprecated architectures, build aarch64 on ARM runners (#324) @sairon
```

## 2025.11.21
Automated Rebuild triggered by [2025.11.1](https://github.com/home-assistant/docker-base/releases/tag/2025.11.1)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Add release-suffixed tags to Docker images for version pinning (#326) @sairon
Delete the Python archive signature file after validation (#325) @agners
Update pip to v25.3 (#323) @sairon
```

## 2025.11.13
Automated Rebuild triggered by [2025.11.0](https://github.com/home-assistant/docker-base/releases/tag/2025.11.0)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Drop Alpine 3.19 builds (#322) @sairon
Reduce number of layers and optimize build of the base-python images (#321) @sairon
```

## 2025.10.16
Automated Rebuild triggered by [2025.10.1](https://github.com/home-assistant/docker-base/releases/tag/2025.10.1)

Upstream Release Notes (only Alpine applies):
```
What’s Changed
Update Python to 3.13.9 (#320) @cdce8p
```

## 2025.10.15
Automated Rebuild triggered by [2025.10.0](https://github.com/home-assistant/docker-base/releases/tag/2025.10.0)

Upstream Release Notes (only Alpine applies):
```
What’s Changed
Update Python to 3.12.12 (#318) @cdce8p
Update Bashio to v0.17.5 (#319) @sairon
Add Python 3.14 + drop Python 3.11 + update 3.13 (#306) @cdce8p
Use yaml anchors for workflow (#316) @cdce8p
Bump home-assistant/builder from 2025.03.0 to 2025.09.0 (#317) @dependabot[bot]
Update Bashio to v0.17.2 (#315) @sairon
```

## 2025.09.23
Support for custom `dnscrypt-proxy.toml` files.

`dnscrypt-proxy.toml` is now stored in `/addon_configs/ba53f40c-dnscrypt-proxy/` which can be edited by users with either the ssh addon or vscode addons available in Home Assistant

Base image has been updated to Alpine 3.22 (latest)

## 2025.09.21
Testing automated rebuilds with n8n -- better but not perfect.

## 2025.09.22
Testing automated rebuilds with renovate -- No good ☹️

## 2024.06.23
Testing Releases and Updates.

## 2024.06.19.1
Added block list to prevent RFC1918 reverse lookups being sent externally.

## 2024.06.19 Hello World
Initial Release
