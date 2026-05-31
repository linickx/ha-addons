# 0.1.0 - UX Upgrades & more!

This release contains the user experience updates I have been wanting to implement for a long time!

> 👉🏼 BACKUP before proceeding!
> This version performs a database update, I recommend you manually take a copy of `/addon_configs/ba53f40c_homedetector/hd.db` before updating as well as using Home Assistant's own backup utils.

## UX: Alert Management

The alerts page now has the buttons you would expect; alerts are unread by default they can be toggle between read/unread, there is a button to delete them as well! My Home Assistant has circa 300 alerts, now I can clean it up and so can you.

## UX: Separate Alert & Block Toggles

For both domains and queries the logic for Alerting and Blocking has now been separated.

To avoid breaking anyone's setup, any domain/query record currently set to pass, will be migrated to "Allow without Alert". When a new domain/query is detect, the existing behaviour of "Block and Alert" is maintained, as before no _actual_ blocking happens unless `DNS Firewalling` is enabled: 👉🏼 **This will change in future versions - blocking will soon be the default.**

This change allows for 2x new situations which can be found under `Tuning`:

### Ignored DNS Blocks

For situations where you have decided to block something, but you don't want to be alerted every time it is called, you can set a domain/query is a toggle of block=on and alert=off, when your DB has circa 300 rows it can be hard to find these, thus this page surfaces them for you so you can change your mind.

### Alerting DNS Pass

For situations where blocking breaks something important, but you still wish to know when it is called -- perhaps troubleshooting something. Similar to the above, this allows you to surface these when your DB starts to grow above a few pages.

## UX: Fixed broken Config Button

Addon's have been renamed to Apps -> https://github.com/home-assistant/architecture/discussions/1287

With this change, the `Config` button in Home Detector started to return an 404 page not found, this has been fixed.

## Bonus: `Apparmor.txt` 

Not UX related, but something I wanted to do: the container now includes an [Apparmor](https://developers.home-assistant.io/docs/apps/presentation/#apparmor) file, this boosts Home Detector's security rating to 8 -- This looks to be the highest available currently.

## Bonus: Build using Base `2026.05.20`

This image is running the [latest base - 2026.05.20](https://github.com/home-assistant/docker-base/releases/tag/2026.05.0)

## Bonus: Updated Multi-Arch Builds

Workflow (GitHub Actions) updates, triggered by [upstream changes to container builds](https://developers.home-assistant.io/blog/2026/04/02/builder-migration/). ~~Addons~~ Apps are now multi-architecture, this change is mostly about notifying HomeAssistant installs so they know where to find updates.

Since I was already here, I added SBOMS -- Software Bill of Materials -- to the flow, see the release artefacts.

# 0.0.13 - 2026.05.19

Automated Rebuild triggered by [2026.04.0](https://github.com/home-assistant/docker-base/releases/tag/2026.04.0)

Upstream Release Notes (only Alpine applies):

```
What’s Changed
Flatten base images, modernize the build (#358) @sairon
Update Python in base-python to 3.13.13/3.14.4 (#357) @sairon
Bump release-drafter/release-drafter from 7.1.1 to 7.2.0 (#359) @dependabot[bot]
Bump release-drafter/release-drafter from 7.0.0 to 7.1.1 (#355) @dependabot[bot]
```

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
