# 0.0.12 - 2025.12.08

Automated Rebuild triggered by [2025.12.0](https://github.com/home-assistant/docker-base/releases/tag/2025.12.0)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Update Python to 3.13.11 and 3.14.2 (#337) @cdce8p
Bump actions/checkout from 6.0.0 to 6.0.1 (#336) @dependabot[bot]
Bump home-assistant/builder from 2025.09.0 to 2025.11.0 (#334) @dependabot[bot]
Drop obsolete QEMU_CPU build argument (#333) @sairon
```

# 0.0.11 - 2025.11.26

Automated Rebuild triggered by [2025.11.3](https://github.com/home-assistant/docker-base/releases/tag/2025.11.3)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Fix tagging of latest images (#332) @sairon
Fix incorrect version-suffixed tags of Python images (#331) @sairon
```

# 0.0.10 - 2025.11.25

Automated Rebuild triggered by [2025.11.2](https://github.com/home-assistant/docker-base/releases/tag/2025.11.2)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Bump actions/checkout from 5.0.0 to 6.0.0 (#329) @dependabot[bot]
Add reusable builder workflow (#328) @cdce8p
Tag Python 3.14-alpine3.22 images with the latest tag (#327) @sairon
Drop deprecated architectures, build aarch64 on ARM runners (#324) @sairon
```

# 0.0.9 - 2025.11.21

Automated Rebuild triggered by [2025.11.1](https://github.com/home-assistant/docker-base/releases/tag/2025.11.1)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Add release-suffixed tags to Docker images for version pinning (#326) @sairon
Delete the Python archive signature file after validation (#325) @agners
Update pip to v25.3 (#323) @sairon
```

# 0.0.8 - 2025.11.13

Automated Rebuild triggered by [2025.11.0](https://github.com/home-assistant/docker-base/releases/tag/2025.11.0)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Drop Alpine 3.19 builds (#322) @sairon
Reduce number of layers and optimize build of the base-python images (#321) @sairon
```

# 0.0.7 - 2025.10.16

Automated Rebuild triggered by [2025.10.1](https://github.com/home-assistant/docker-base/releases/tag/2025.10.1)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Update Python to 3.13.9 (#320) @cdce8p
```

# 0.0.6 - 2025.10.15

* Automated Update: 0.0.6 - 2025.10.15
* Triggered by Upstream Release: https://github.com/home-assistant/docker-base/releases/tag/2025.10.0

Upstream Release Notes (Only Alpine Applies):

```
What’s Changed
Update Python to 3.12.12 (#318) @cdce8p
Update Bashio to v0.17.5 (#319) @sairon
Add Python 3.14 + drop Python 3.11 + update 3.13 (#306) @cdce8p
Use yaml anchors for workflow (#316) @cdce8p
Bump home-assistant/builder from 2025.03.0 to 2025.09.0 (#317) @dependabot[bot]
Update Bashio to v0.17.2 (#315) @sairon
```

# 0.0.5 - Support for custom `opencanary.conf`

The `opencanary.conf` file is now stored in the `/addon_configs/`, see https://opencanary.readthedocs.io for details on what you can do.

Note: Services available will be limited by Port Forwarding configuration in Home Assistant.

# 0.0.4 - Update Container Image.

Another dependency update while I figure out what features to work on!

# 0.0.3 - Dependency Updates.

Mostly about getting OpenCanary to the latest version (0.9.6) but some other pip updates as well for requests & twisted.

# 0.0.2 - Move the DB!

During Development the sqlite DB was in `/share` so the [add-on for sqlite](https://github.com/hassio-addons/addon-sqlite-web) could be used for troubleshooting, a pull request to allow access to `/addons_config` [was declined](https://github.com/hassio-addons/addon-sqlite-web/pull/313) due to some weirdness.

This release moves the DB to the intended target location, and tests the update/release process 😉

# 0.0.1 - Hello World

Initial release
