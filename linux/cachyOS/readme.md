# changes
installed kernel cacyos-znver4/linux-cachyos-eevdf
installed rog-control-center, asusctl
installed waterfox-bin

optimistic changes keep power efficiency lowish (browsing ~20w, maybe can be lower) 
## Optimize the CPU Governor
### limine config
```
# 1. Append the parameter to the persistent Limine defaults configuration file
echo 'KERNEL_CMDLINE[default]+=" amd_pstate=active"' | sudo tee -a /etc/default/limine

# 2. Regenerate the Limine boot entries using the CachyOS tool script
sudo limine-mkinitcpio
```

## Lower iGPU Power Limits via AMDGPU Driver
### udev rule
```
echo 'ACTION=="add", SUBSYSTEM=="drm", DRIVERS=="amdgpu", ATTR{device/power_dpm_force_performance_level}="low"' | sudo tee /etc/udev/rules.d/30-amdgpu-low-power.rules && sudo udevadm control --reload-rules && sudo udevadm trigger
```

## rog-control-center
## system control tunables
defaults
|config|value|
|-|-|
cpu sustained power limit| 35
cpu turbo power limit| 65
cpu fast burst power limit| 80
gpu temperature limit| 87
