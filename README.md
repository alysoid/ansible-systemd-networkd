# [Catena](https://github.com/alysoid/catena) Ansible Role: systemd-networkd

Manage system network with systemd using [systemd-networkd](https://man.archlinux.org/man/systemd-networkd.8.en), a system service that manages networks. It detects and configures network devices as they appear, as well as creating virtual network devices. Low-level link settings can be set independently of networks.

## Role default variables

| Variable          | Default | Info                                                                                        |
| ----------------- | ------- | ------------------------------------------------------------------------------------------- |
| `systemd_network` | `{}`    | Apply a network configuration for a matching device.                                        |
| `systemd_netdev`  | `{}`    | Create a virtual network device for a matching environment.                                 |
| `systemd_link`    | `{}`    | Create link settings. When a network device appears, udev will look for the first matching. |
| `network_cleanup` | `no`    | Remove existing configuration files: `/etc/systemd/network/{*.network}{*.netdev}{*.link}`   |

### `systemd_network`

Manage [systemd.network - Network configuration](https://man.archlinux.org/man/systemd.network.5) files.

Configuration files will have the .network extension and will be placed in the local administration network directory `/etc/systemd/network`.

### `systemd_netdev`

Manage [systemd.netdev - Virtual Network Device configuration](https://man.archlinux.org/man/systemd.netdev.5) files.

Configuration files will have the .netdev extension and will be placed in the local administration network directory `/etc/systemd/network`.

### `systemd_link`

Manage [systemd.link - Network device configuration](https://man.archlinux.org/man/systemd.link.5) files.

Configuration files will have the .link extension and will be placed in the local administration network directory `/etc/systemd/network`.
