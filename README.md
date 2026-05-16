# Revenant Kernel

Custom GKI kernel for **POCO X7 Pro** (codename `rodin`, MediaTek Dimensity 8400 / MT6899)
on Android 15 / 16 HyperOS.

Built from AOSP `common-android15-6.6` with **KernelSU-Next** + **SuSFS** integration,
ZSWAP/LRU_GEN memory tuning, and CAKE qdisc networking.

## Status

> **🚧 Beta — work in progress.** Use at your own risk. Backups required.

## Details

| | |
|---|---|
| Base | Linux 6.6.127 GKI `android15-8-4k` |
| Toolchain | Android clang (PGO + BOLT + LTO + MLGO) |
| Page size | 4K |
| KernelSU-Next | v3.2.0 (33129) — spoofed package |
| SuSFS | v2.1.0 (gki-android15-6.6) |

## Releases

Each release ships an AnyKernel3 zip. Flash via Horizon Kernel Flasher or Franco Kernel Manager.

| Tag | Highlights |
|---|---|
| `Beta-v1.0` | Baseline — KernelSU-Next + SuSFS + ZSWAP/LRU_GEN + Kyber I/O |
| `Beta-v1.1` | Adds CAKE qdisc, BBR+TFO, autogroup scheduler, F2FS compression, CFS bandwidth |
| `Beta-v1.2` | Adds SUS_MAP, custom RASP-defense patches (prop hook, vbmeta intercept, per-app mount NS) |
| `Beta-v1.3` | All of v1.1 + v1.2 combined |

## Requirements

- Unlocked bootloader
- Root flasher (Horizon, Franco, FKM) — no custom recovery
- Stock backup of `boot_a.img`, `init_boot_a.img`, `vendor_boot_a.img`

## Installation

1. Download the `Revenant-<tag>-AnyKernel3.zip` from Releases
2. Open Horizon Kernel Flasher (or Franco) and select the zip
3. Flash, reboot

To revert: flash your stock `boot_a.img` via fastboot.

## Build

CI: GitHub Actions. See `.github/workflows/build.yml`.
