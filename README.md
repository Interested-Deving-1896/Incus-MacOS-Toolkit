[update-readmes]   Mode: rewrite — migrating to template structure...
# Incus-MacOS-Toolkit

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/Incus-MacOS-Toolkit)

<!-- AI:start:what-it-does -->
This project provides a unified toolkit for macOS users requiring advanced virtualization, filesystem interoperability, and storage solutions. It enables macOS KVM virtualization, access to Linux filesystems on macOS, compatibility tools for cross-platform workflows, and a hybrid BTRFS+DwarFS storage framework. It is designed for developers and system administrators working across macOS and Linux environments.
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
The project consists of multiple components organized into distinct directories, each addressing a specific functionality. These components interact through shared build and runtime dependencies, coordinated via the `Makefile`. The directory structure is as follows:

```plaintext
.
├── macos-vm/       # macOS KVM virtualization using QEMU and Incus
├── linuxfs/        # Go-based CLI for accessing Linux filesystems on macOS/Windows
├── compat/         # Compatibility tools for macOS and Linux (e.g., linuxify, mlsblk)
├── btrfs-dwarfs/   # BTRFS+DwarFS hybrid filesystem (kernel module + userspace tools)
├── btrfs-devel/    # Read-only reference to upstream BTRFS development sources
├── .github/        # CI/CD workflows and GitHub-specific configurations
├── LICENSE         # Project license (GPL-3.0-or-later)
├── Makefile        # Unified build and management entry point
└── README.md       # Project documentation
```

Key interactions include:
- `macos-vm` depends on `btrfs-dwarfs` for storage backends.
- `linuxfs` and `compat` provide tools for cross-platform filesystem and compatibility support.
- The `Makefile` orchestrates builds, tests, and installations, with support for per-component operations and host-specific configurations.
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/Incus-MacOS-Toolkit.git
cd Incus-MacOS-Toolkit
```

## Usage

<!-- Add usage examples here. This section is yours — the AI will not modify it. -->

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
The repository uses GitHub Actions for continuous integration. The following workflows are defined:

1. **btrfs-devel-sync.yml**  
   Synchronizes the `btrfs-devel` directory with the upstream `kdave/btrfs-devel` repository.  
   - **Triggers**: Manual dispatch, scheduled (daily).  
   - **Required Secrets**: `UPSTREAM_REPO_URL`, `GITHUB_TOKEN` (provided by default).  

2. **mirror-osp-to-ooc.yaml**  
   Mirrors the repository from an open-source platform (OSP) to an out-of-cloud (OOC) backup.  
   - **Triggers**: Push to the default branch.  
   - **Required Secrets**: `OOC_REPO_URL`, `OOC_SSH_KEY`.  

Ensure the required secrets are configured in the repository settings for workflows to function correctly.
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/Incus-MacOS-Toolkit`](https://github.com/Interested-Deving-1896/Incus-MacOS-Toolkit) and mirrored through:

```
Interested-Deving-1896/Incus-MacOS-Toolkit  ──►  OpenOS-Project-OSP/Incus-MacOS-Toolkit  ──►  OpenOS-Project-Ecosystem-OOC/Incus-MacOS-Toolkit
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
[@Interested-Deving-1896](https://github.com/Interested-Deving-1896): 43 commits  
[@ona-agent](https://github.com/ona-agent): 2 commits  

*Note: This repository is a mirror. Please refer to the upstream source for additional details.*
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->

Original project — unified toolkit for macOS KVM virtualisation and Linux filesystem access on macOS via Incus.

| Origin | Host | Fork in I-D-1896 |
|--------|------|-----------------|
| [lxc/incus](https://github.com/lxc/incus) | GitHub | ✅ |
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
| File | Description |
|---|---|
| [dep-graph/origins.md](https://github.com/Interested-Deving-1896/Incus-MacOS-Toolkit/blob/main/dep-graph/origins.md) | Dependency graph (Markdown table) |
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
[GPL-3.0](https://github.com/Interested-Deving-1896/Incus-MacOS-Toolkit/blob/main/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
