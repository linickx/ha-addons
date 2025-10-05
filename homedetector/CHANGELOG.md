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
