# Nothing Phone (4a) Kernel Builder

Kernel builder for the **Nothing Phone (4a)** (`Frogger` / `A069` / `SM7635`) based on the official [NothingOSS](https://github.com/NothingOSS/android_kernel_msm-6.1_nothing_sm7635.git) kernel sources (`sm7635/b/mr_Frogger`).

## Features

- **KernelSU Next** from the `dev` branch with dual manager signature support (Official + Custom signed manager)
- **BBRv3** TCP congestion control (backported to Android 14 6.1)
- **FQ** and **CAKE** queue schedulers
- **ThinLTO** (Clang Thin Link-Time Optimization)
- **Battery & Overhead Optimization** (disabled SLUB_DEBUG, SCHED_DEBUG, and DEBUG_LIST overhead)
- **Multi-Gen LRU (MGLRU)** & **PM_AUTOSLEEP**
- **ZRAM** with high-speed LZ4 compression and ZRAM Writeback support
- **CCache** compilation acceleration
- **AnyKernel3** flashable package for recovery or Kernel Flasher
- Clang toolchain and CCache caching in GitHub Actions
- Weekly automated GitHub Releases with full build metadata

## Building

### GitHub Actions

- **Build Nothing Phone (4a) Kernel**: Manual workflow (`workflow_dispatch`) for testing builds and creating artifacts.
- **Weekly Release Nothing Phone (4a) Kernel**: Runs automatically every Sunday at 03:00 UTC (or manually via `workflow_dispatch`) to compile the kernel and publish a GitHub Release with detailed release notes and flashable packages.

### Local Build

```bash
./scripts/build.sh
```

Build outputs are saved in the `artifacts` directory:

- `Image`
- `Image.sha256`
- `Nothing-Phone-4a.zip`
- `Nothing-Phone-4a.zip.sha256`
- `release_notes.md`
- `build.log`

If the build fails, `failure.log` and any `*.rej` files are saved as well.

