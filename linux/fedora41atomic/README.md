these instructions / notes should be able to be applied to any most derivatives of fedora 41 atomic desktops including
ublue bazzite / aurora dx

## fix amd graphical artifacts
https://gitlab.freedesktop.org/drm/amd/-/issues/3388

rpm-ostree kargs --append=amdgpu.dcdebugmask=0x10

hopefully not needed post kernel 6.13.x

# connecting to meraki l2tp vpn
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

find the ipsec.conf file

journalctl --no-hostname _SYSTEMD_UNIT=NetworkManager.service + SYSLOG_IDENTIFIER=pppd | grep -i ipsec.conf

add ikev1-policy=accept ?

sudo nano ... ipsec.conf

## disable selinux
sudo nano /etc/selinux/config

SELINUX=disabled

## questionable
sudo update-crypto-policies --set DEFAULT:SHA1

## powershell 
distrobox-create --image ghcr.io/ublue-os/powershell-toolbox --name pwsh

distrobox-upgrade --all

distrobox enter pwsh

distrobox-export --app pwsh

curl -s https://ohmyposh.dev/install.sh | bash -s

mkdir -p /home/$user/.local/share/powershell/PSReadLine

touch /home/$user/.local/share/powershell/PSReadLine/ConsoleHost_history.txt

## vscode
settings.json

```
{
    "window.titleBarStyle": "custom",
    "editor.fontFamily": "'Cascadia Code', 'Droid Sans Mono', 'monospace', monospace",
    "terminal.integrated.automationProfile.linux": {},
    "terminal.integrated.defaultProfile.linux": "bash",
    "terminal.integrated.env.linux": {
    
    },
    "terminal.integrated.profiles.linux": {

        "bash": {
            "path": "bash",
            "icon": "terminal-bash"
        },
        "zsh": {
            "path": "zsh"
        },
        "fish": {
            "path": "fish"
        },
        "tmux": {
            "path": "tmux",
            "icon": "terminal-tmux"
        },
        "pwsh": {
            "path": "distrobox",
            "icon": "terminal-powershell",
            "args": ["enter", "pwsh"]
        }
    }
}
```

