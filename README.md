## Zero-Tier-in-True-Nas

# Install & Konfigurasi zerotier Di TRUENAS

1. Install zerotier
```bash
sed -i .orig 's/enabled: yes/enabled: no/' /usr/local/etc/pkg/repos/local.conf
sed -i .orig 's/enabled: no/enabled: yes/' /usr/local/etc/pkg/repos/FreeBSD.conf
pkg update
pkg install -y zerotier
```

2. Start the service
```bash
service zerotier onestatus
service zerotier onestart
```

3. Move the database to a persisted zfs dataset
```bash
mkdir -p /mnt/tank/zerotier/db/
mv /var/db/zerotier-one/* /mnt/tank/zerotier/db/
/sbin/mount_nullfs /mnt/tank/zerotier/db/ /var/db/zerotier-one
ls -1 /var/db/zerotier-one
```

```bash
```

```bash
```


## Donate Qris ALL Payment
<p align="center">
<img src="https://github.com/arthasa28/Cyberior_MD-BOT/blob/master/pp%20Qris%20Artha.jpg?raw=true" alt="CYBERIR-MD" width="300"/>
