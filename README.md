# arch-efi-progs

Minimal UEFI EFI applications for shutting down and rebooting a machine directly from the UEFI boot menu.

## Applications

| Binary | Action |
|--------|--------|
| `poweroff.efi` | Shuts the machine down (`EfiResetShutdown`) |
| `reboot.efi` | Cold-reboots the machine (`EfiResetCold`) |

## Building

```
make
```

## Installation

Copy the binaries to the EFI System Partition and register them with `efibootmgr`:

```sh
cp poweroff.efi reboot.efi /boot/EFI/arch-efi-progs/

efibootmgr --create --disk /dev/sda --part 1 --label "Power Off" --loader '\EFI\arch-efi-progs\poweroff.efi'
efibootmgr --create --disk /dev/sda --part 1 --label "Reboot"    --loader '\EFI\arch-efi-progs\reboot.efi'
```

Adjust the disk and partition to match your ESP.
