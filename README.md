## Zero-Tier-in-True-Nas

# Install & Konfigurasi zerotier Di TRUENAS

1. Install zerotier
```bash
sed -i .orig 's/enabled: yes/enabled: no/' /usr/local/etc/pkg/repos/local.conf
sed -i .orig 's/enabled: no/enabled: yes/' /usr/local/etc/pkg/repos/FreeBSD.conf
pkg update
pkg install -y zerotier
```

```bash
```

```bash
```

```bash
```

```bash
```
