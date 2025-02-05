## Zero-Tier-in-True-Nas

# Install & Konfigurasi zerotier Di TRUENAS

1. Install zerotier
```bash
sed -i .orig 's/enabled: yes/enabled: no/' /usr/local/etc/pkg/repos/local.conf
sed -i .orig 's/enabled: no/enabled: yes/' /usr/local/etc/pkg/repos/FreeBSD.conf
pkg update
pkg install -y zerotier
```
</br>

2. Start the service
```bash
service zerotier onestatus
service zerotier onestart
```
</br>

3. Move the database to a persisted zfs dataset
```bash
mkdir -p /mnt/tank/zerotier/db/
mv /var/db/zerotier-one/* /mnt/tank/zerotier/db/
/sbin/mount_nullfs /mnt/tank/zerotier/db/ /var/db/zerotier-one
ls -1 /var/db/zerotier-one
```
</br>

4. Join ZeroTier network
```bash
zerotier-cli join 41d49af6c20ee1ce
zerotier-cli info
cp /usr/local/etc/rc.d/zerotier /mnt/tank/zerotier/zerotier.rc.d
```
</br>

5. Create the startup script
```bash
curl https://alan.norbauer.com/articles/zerotier-on-truenas/scripts/zerotier-start.sh -o /mnt/tank/zerotier/zerotier-start.sh
chmod +x /mnt/tank/zerotier/zerotier-start.sh
```
</br>

6. Add zerotier-start.sh to TrueNAS as a Pre-Init startup script


# Perintah Lain

```bash
curl -s https://install.zerotier.com | bash
zerotier-cli join "network_id"
systemctl enable zerotier-one.service
systemctl restart zerotier-one.service
```



## Donate Qris ALL Payment
<p align="center">
<img src="https://github.com/arthasa28/Cyberior_MD-BOT/blob/master/pp%20Qris%20Artha.jpg?raw=true" alt="CYBERIR-MD" width="300"/>
