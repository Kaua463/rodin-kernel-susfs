# rodin-kernel-susfs

GKI `android15-6.6` kernel para **POCO X7 Pro** (codename `rodin`, Dimensity 8400 / MT6899)
com **KernelSU-Next** + **SuSFS** + ZRAM zstd + CAKE qdisc.

Base: kernel stock `6.6.89-android15-8-g8e4be6b47e40-ab14134548-4k` (4K pages, no LTO).

## Build

Roda no GitHub Actions (`Actions` tab → `Build Kernel` → `Run workflow`).
Output: `Image.lz4` + `AnyKernel3-rodin-*.zip` como artifacts.

## Flash

1. Baixe o `AnyKernel3-rodin-*.zip` do artifact
2. Reboot recovery (OrangeFox/TWRP do rodin)
3. Install → selecione o zip
4. Reboot
5. Re-aplique Play Integrity Fix / Kairos (a string de versão muda)

**Backup do boot atual está salvo localmente antes de qualquer flash.**
Em caso de bootloop: `fastboot flash boot boot_a.img` (o backup).
