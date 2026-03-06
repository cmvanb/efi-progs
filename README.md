# efi-progs

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
