# These files were created following the process posted on asus-linux.org
https://asus-linux.org/wiki/cirrus-amps/

## updated grub
sudo grub2-mkconfig -o /etc/grub2.cfg

## not a complete fix - need to revisit
```
dmesg | grep CSC35
[    0.002956] ACPI: Table Upgrade: install [SSDT-CUSTOM- CSC3551]
[    0.002957] ACPI: SSDT 0x000000009B0BE000 00014D (v01 CUSTOM CSC3551  00000001 INTL 20220331)
[    7.468255] Serial bus multi instantiate pseudo device driver CSC3551:00: Instantiated 2 I2C devices.
[    7.640874] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.0: Cirrus Logic CS35L41 (35a40), Revision: B2
[    7.641188] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.1: Reset line busy, assuming shared reset
[    7.679950] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.0: DSP1: cirrus/cs35l41-dsp1-spk-prot-10431463.wmfw: invalid magic
[    7.679957] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.0: Cannot Initialize Firmware. Error: -22
[    7.680825] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.0: Cannot Run Firmware, reverting to dsp bypass...
[    7.680835] snd_hda_codec_realtek hdaudioC1D0: bound i2c-CSC3551:00-cs35l41-hda.0 (ops cs35l41_hda_comp_ops [snd_hda_scodec_cs35l41])
[    7.681049] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.1: DSP1: cirrus/cs35l41-dsp1-spk-prot-10431463.wmfw: invalid magic
[    7.681053] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.1: Cannot Initialize Firmware. Error: -22
[    7.681821] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.1: Cannot Run Firmware, reverting to dsp bypass...
[    7.681828] snd_hda_codec_realtek hdaudioC1D0: bound i2c-CSC3551:00-cs35l41-hda.1 (ops cs35l41_hda_comp_ops [snd_hda_scodec_cs35l41])
[    7.681834] cs35l41-hda i2c-CSC3551:00-cs35l41-hda.1: Cirrus Logic CS35L41 (35a40), Revision: B2
```
