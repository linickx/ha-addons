# Documentation

A basic implementation of https://github.com/DNSCrypt/dnscrypt-proxy

## Configuration

When the addon starts for the first time, a default configuration will be created: 

- `/addon_configs/ba53f40c-dnscrypt-proxy/dnscrypt-proxy.toml`

The syntax is documented on [DNSCrypt-Proxy's Wiki here](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Configuration).

### 🔥 Important Note about folders/paths 🔥

The dnscrypt-proxy runs as a container, the path you edit (from SSH) is different to what the container sees.

- `/addon_configs/ba53f40c-dnscrypt-proxy/dnscrypt-proxy.toml` == `/config/dnscrypt-proxy.toml`

Therefore, if you wish to import your own custom block-list, you must use `/config/` as the folder, eg replace 

```
blocked_names_file = '/etc/dnscrypt-proxy/blocked-names.txt'
```

**with this...**

```
blocked_names_file = '/config/my-blocked-names.txt'
```

### Block lists

The [default block list](https://github.com/linickx/addon-dnscrypt-proxy/blob/main/blocked-names.txt) prevents reverse lookups for RFC1918 addresses being sent upstream, you can block your local zone or whatever you like being forwarded by simply adding the domain to the bottom of the file and importing it (see above)
