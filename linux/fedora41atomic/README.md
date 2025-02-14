these instructions / notes should be able to be applied to any most derivatives of fedora 41 atomic desktops including
ublue bazzite / aurora dx

## fix amd graphical artifacts
https://gitlab.freedesktop.org/drm/amd/-/issues/3388
rpm-ostree kargs --append=amdgpu.dcdebugmask=0x10
hopefully not needed post kernel 6.13.x

## connecting to meraki l2tp vpn
rpm-ostree uninstall libreswan
rpm-ostree install NetworkManager-l2tp strongswan-libipsec strongswan

## not sure if this is necessary - remove blacklist for l2tp
/etc/modprobe.d/l2tp_netlink-blacklist.conf
/etc/modprobe.d/l2tp_ppp-blacklist.conf

changed "load = yes" to "load = no" in /etc/strongswan/strongswan.d/charon/kernel-libipsec.conf, 
rebooted my computer and the connection works

sudo systemctl stop xl2tpd
sudo systemctl disable xl2tpd
sudo systemctl mask xl2tpd

## questionable
sudo update-crypto-policies --set DEFAULT:SHA1
