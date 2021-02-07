# [Catena](https://github.com/alysoid/catena) - Network Ansible Role

Manage system network via systemd using [systemd-networkd](https://man.archlinux.org/man/systemd-networkd.8.en).

Systemd.networkd read the files located in the system network directories `/usr/lib/systemd/network`, the volatile runtime network directory `/run/systemd/network` and the local administration network directory `/etc/systemd/network`. All configuration files are collectively sorted and processed in lexical order, regardless of the directories in which they live. However, files with identical filenames replace each other. Files in /etc/ have the highest priority, files in /run/ take precedence over files with the same name in /usr/lib/. This can be used to override a system-supplied configuration file with a local file if needed. As a special case, an empty file (file size 0) or symlink with the same name pointing to /dev/null disables the configuration file entirely (it is "masked").

## Role default variables

| Variable          | Default | Info
| ----------------- | ------- | ------------------
| `systemd_network` | `{}`    | They will apply a network configuration for a matching device.
| `systemd_netdev`  | `{}`    | They will create a virtual network device for a matching environment.
| `systemd_link`    | `{}`    | When a network device appears, udev will look for the first matching .link file.


### `systemd_network`

Manage [systemd.network - Network configuration](https://man.archlinux.org/man/systemd.network.5) files.

Files will have the .network extension and will be placed in the local administration network directory `/etc/systemd/network`. 

### `systemd_netdev`

Manage [systemd.netdev - Virtual Network Device configuration](https://man.archlinux.org/man/systemd.netdev.5) files.

Files will have the .netdev extension and will be placed in the local administration network directory `/etc/systemd/network`.

### `systemd_link`

Manage [systemd.link - Network device configuration](https://man.archlinux.org/man/systemd.link.5) files.

Files will have the .link extension and will be placed in the local administration network directory `/etc/systemd/network`.
