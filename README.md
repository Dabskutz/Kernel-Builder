# Kernel-Builder

Automated GitHub Actions workflow for building a custom Android kernel targeting the **Xiaomi Peridot** (Redmi Turbo 3 / Poco F6).

---

## Overview

This repository provides a CI/CD pipeline that clones the kernel source, sets up the LLVM/Clang toolchain, compiles the kernel, and packages the output using AnyKernel3 — all via GitHub Actions without requiring a local build environment.

## Device Target

| Field | Value |
|---|---|
| Device | Xiaomi Peridot (peridot) |
| Codename | Redmi Turbo 3 / Poco F6 |
| Architecture | arm64 |
| Compiler | LLVM / Clang |

## Repository Structure

```
Kernel-Builder/
├── .github/
│   └── workflows/       # GitHub Actions workflow definitions
└── workflow/            # Supporting scripts and configuration files
```

## Usage

### Trigger a Build

1. Go to the **Actions** tab in this repository.
2. Select the kernel build workflow.
3. Click **Run workflow**.
4. Wait for the build to complete.
5. Download the compiled artifact (`.zip`) from the workflow run summary page.

### Flash

Flash the downloaded AnyKernel3 zip via a custom recovery (TWRP, OrangeFox, etc.) or via `fastboot`.

## Toolchain

Builds use the LLVM/Clang toolchain. The exact version and source are defined inside the workflow YAML under `.github/workflows/`.

## Notes

- The kernel source is pulled from [Peridot-Development/kernel_xiaomi_peridot](https://github.com/Peridot-Development/kernel_xiaomi_peridot).
- No local setup is needed — all compilation happens on GitHub-hosted runners.
- Build artifacts are uploaded automatically on successful completion.

## Credits

- Kernel source: [Peridot-Development](https://github.com/Peridot-Development/kernel_xiaomi_peridot)
- AnyKernel3: [osm0sis/AnyKernel3](https://github.com/osm0sis/AnyKernel3)
