<div align="center">

<img width="845" alt="Arc Loader" src="https://github.com/AuxXxilium/arc/raw/page/docs/arc_loader.png?raw=true">

### Arc — a customized Redpill Loader for DSM 7.x

Enhanced hardware support, add-ons, guided (semi-automated) installation and a lot of built-in customization.<br>
Modified to run on a wide range of hardware — bare metal, mini-PC or VM.

<a href="https://github.com/AuxXxilium/arc/releases/latest"><img alt="Stable" src="https://img.shields.io/badge/download-red?style=for-the-badge&label=stable&color=%23FF0000"></a>
<a href="https://github.com/AuxXxilium/arc-essential/releases/latest"><img alt="Essential" src="https://img.shields.io/badge/download-red?style=for-the-badge&label=essential&color=%23FF0000"></a>
<a href="https://github.com/AuxXxilium/arc-beta/releases/latest"><img alt="Beta" src="https://img.shields.io/badge/download-red?style=for-the-badge&label=beta&color=%23FF0000"></a>
<a href="https://xpenology.tech/wiki"><img alt="Wiki" src="https://img.shields.io/badge/read_first-blue?style=for-the-badge&label=wiki&color=%230066CC"></a>

</div>

---

> [!IMPORTANT]
> * Arc and DSM are **independent** from each other — Arc is a boot helper for DSM.
> * **Commercial use is not permitted and strictly forbidden.**
> * DSM and all parts of it are under copyright / ownership by Synology Inc.
> * The Loader is free and will stay free forever. If you paid a suspicious person for it, I can't help you — I'm not connected to them.

---

## 📦 Projects

**Everything below is part of the Arc ecosystem. Each project stands on its own, but they are built to work together.**

<br>

### <img src="https://img.shields.io/badge/-Arc-FF0000?style=flat-square" height="20"> Arc Loader

The loader itself — guided setup that turns almost any x64 PC, mini-PC or VM into a DSM 7.x box.

* **Guided or fully automated install** — a dialog-driven walkthrough (Model → DSM version → Add-ons → Build → Boot) or a hands-off automated mode
* **Hardware-aware model picker** — probes CPU flags, SATA/SAS/NVMe/RAID controllers, iGPU and thread count, then shows only models your hardware can actually run
* **Broad platform support** — apollolake, geminilake(nk), broadwell(nk/v2), purley, icelaked, epyc7002, epyc7003(ntb), r1000nk, v1000nk
* **Selectable custom kernel** — switch between Synology's stock kernel and Arc's own builds on supported platforms
* **Smart add-ons** — auto-enables what your hardware needs (NVMe, cpufreq scaling, sensors, LED control, i915, vmtools, SMART …)
* **Web UI & remote help** — browser config page, file upload service, web terminal, plus one-click remote assistance for support
* **Built-in updater** — update the loader, add-ons, modules, patches, configs and kernels from the menu, each from its own release channel
* **Rescue toolbox** — reset DSM passwords, add an admin, force-enable SSH, clear blocked IPs, restore config or `machine.key`, clone the loader, edit cmdline/synoinfo and much more

<sub><a href="https://github.com/AuxXxilium/arc">Repository</a> ·
<a href="https://github.com/AuxXxilium/arc/releases/latest">Releases</a></sub>

---

<br>

### <img src="https://img.shields.io/badge/-arx-B91C1C?style=flat-square" height="20"> arx &nbsp;<img src="https://img.shields.io/badge/beta-B91C1C?style=flat-square" height="18">

The evolution of arc — the Arc Loader, set up entirely from your browser.

* **Setup in the browser** — a few simple steps with Back and Next, in plain words; the screen on the machine tells you which address to open
* **Arc at its core** — the same proven setup and build logic as the Arc Loader
* **Picks the right add-ons for you** — recognises whether it runs in a virtual machine or on real hardware, and what disks it has, and chooses to match
* **Model picker that knows your hardware** — shows what each model supports, like integrated graphics or M.2 drives, and highlights what your computer has
* **Tweaks** — optional fixes for CPU, memory, power saving, network and graphics, each a simple on/off switch
* **Starts DSM by itself** — once set up, switching the computer on goes straight into DSM
* **Updates itself** — with one click, or from a downloaded file when there is no internet
* **Format Disks** — wipe disks that held another system before installing DSM
* **Works offline** — everything it needs is on the loader disk

> [!NOTE]
> arx is young and tested in VMware so far; it is not yet proven on a wide range of real hardware.

<sub><a href="https://github.com/AuxXxilium/arx">Repository</a> ·
<a href="https://github.com/AuxXxilium/arx/releases/latest">Releases</a></sub>

---

<br>

### <img src="https://img.shields.io/badge/-Kernel-5B21B6?style=flat-square" height="20"> Arc Custom Kernel

Custom DSM kernels that add back the hardware Synology's own kernel never knew about.

* **Kernel 5.10.55 ABI** — stays compatible with DSM's prebuilt modules (parts backported from Linux 6.18)
* **Targets** — epyc7002, geminilakenk, r1000nk and v1000nk for DSM 7.2, 7.3 and 7.4
* **Three flavours** — `legacy` (stock ABI), `full` (up to 64 threads - not released yet)
* **Modern GPU support** — backported i915 and amdgpu for hardware transcoding: Intel up to Meteor Lake incl. Arc A-series, AMD through RDNA 3.5 and Ryzen APUs *(headless — transcoding only, no display output)*
* **Huge network driver set** — Realtek 2.5G/5G, Intel, Aquantia, Mellanox, Broadcom, Solarflare, QLogic, Marvell and many USB adapters, plus WireGuard and modern TCP congestion algorithms
* **Storage & sensors** — MegaRAID, mpt3sas, smartpqi, hpsa, aacraid and more, with a broad hwmon set for temperatures and fan control
* **Virtualization & extras** — VFIO/GPU passthrough, virtio-fs, Hyper-V and VMware support, exFAT/NTFS/FUSE, USB4/Thunderbolt and Coral Edge TPU drivers

<sub>Built kernels are published as <a href="https://github.com/AuxXxilium/arc-custom">Arc Custom</a>.</sub>

---

<br>

### <img src="https://img.shields.io/badge/-Connect-10B981?style=flat-square" height="20"> Arc Connect &nbsp;<img src="https://img.shields.io/badge/beta-10B981?style=flat-square" height="18">

Reach your NAS from anywhere without port forwarding — a self-hosted alternative to QuickConnect.

* **Public HTTPS address for a NAS behind NAT** — your system becomes reachable at its own `connect` subdomain, with no router changes, no open ports and no dynamic DNS required
* **Reverse tunnel** — the NAS dials out and keeps one multiplexed connection open, so nothing has to be exposed to the internet
* **Works with DSM as-is** — the tunnel passes bytes through untouched, so DSM Web UI, File Station, Drive, Photos, Surveillance Station and the Synology mobile apps behave normally
* **Token-based access** — enter your Access Token to connect; the same token identifies your system in Arc Web Management
* **Sensors-only mode** — publish live hardware telemetry without exposing DSM at all
* **Live status** — reports whether the tunnel is up and whether DSM is actually being served, so a dashboard can tell the difference
* **Runs as a service** — installs with systemd units and reconnects automatically with backoff; on Arc installs the token is detected for you
* **Set up from Arc Control** — the Arc Connect tab configures and starts the client for you

> [!NOTE]
> Arc Connect is in beta. The token is the only credential in front of DSM's own login, so treat it like a password. Traffic is TLS-encrypted.

---

<br>

### <img src="https://img.shields.io/badge/-Web-2563EB?style=flat-square" height="20"> Arc Web Management

A hosted portal for your Arc systems — config backup, free DDNS, live monitoring and the community benchmark board.

* **Sign in with Discord** — no extra account and no separate password to manage
* **Register your systems** — add each loader's Access Token with a friendly name and see all of them in one place
* **Config backup & restore** — your loader uploads its configuration and system info, so you can pull it back after a rebuild or a new disk
* **Free ArcDNS hostname** — claim a `*.arcdns.tech` name for your NAS, with optional wildcard and a built-in connection check
* **Live monitoring through Arc Connect** — diagnostics, resource and network views for a connected system, plus a direct link into DSM
* **Benchmark scoreboard** — compare CPU and GPU results with the rest of the community, best result per chip
* **Shared dark mode** — matches the look of Arc Control and the loader web config

<sub>🌐 <a href="https://arc.auxxxilium.tech">arc.xpenology.tech</a></sub>

---

<br>

### 🖥️ DSM Apps

The following install directly in DSM. Add the package source once, then find them in **Package Center → Community**:

Updates then arrive through Package Center like any other app — no manual `.spk` download needed.

<br>

### <img src="https://img.shields.io/badge/-Control-0EA5E9?style=flat-square" height="20"> Arc Control

A DSM app that brings loader configuration, monitoring and hardware tuning to your Synology desktop — no reboot into config mode needed.

* **Edit the loader config from DSM** — model, DSM version, serial, MACs, USB VID/PID, SataDOM, cmdline and more, with config backup
* **Add-on management** — browse, search and toggle add-ons; get notified when a loader update is available
* **One-click reboot into any mode** — rebuild, update, config, recovery, automated, junior or UEFI
* **Live monitoring** — CPU, RAM, clocks, temperatures, disk I/O, full SMART per drive, NVMe, network throughput and an NVIDIA tab when a card is present
* **CPU & power tuning that survives reboot** — thread count, governor, turbo, energy preference, P-core/E-core pinning and dynamic power saving
* **Fan control** — three-point temperature curves for Full/Cool/Quiet modes with a live graph *(needs supported hardware)*
* **Services & patches** — Arc Connect remote access, storage panel matching, HDD/SSD database, Synology Photos and Surveillance Station patches, UGREEN LED control
* **Diagnostics** — storage/CPU/encode benchmarks, speedtest, kernel log, module list, browser terminal and a one-click report for support
* **DSM integration** — desktop app tile plus a widget showing version, temperature, CPU clock, load and disk I/O

<sub>📦 Package Center → Community → **Arc Control** · also published as <a href="https://github.com/AuxXxilium/arc-control">arc-control</a>.</sub>

---

<br>

### <img src="https://img.shields.io/badge/-VMM-F59E0B?style=flat-square" height="20"> Arc VMM &nbsp;<img src="https://img.shields.io/badge/beta-F59E0B?style=flat-square" height="18">

A standalone QEMU/KVM hypervisor packaged for DSM — virtual machines with real PCI passthrough, without Synology's Virtual Machine Manager.

* **Full VM lifecycle** — create, edit, delete, start, shut down and force off; BIOS or UEFI, NUMA split, autostart
* **Flexible disks** — create qcow2/raw images, reuse existing ones, or hand a whole physical disk to a guest
* **Virtual networks** — isolated or bridged onto a NIC, with multiple adapters per machine
* **PCI & GPU passthrough** — binds the full IOMMU group to `vfio-pci`, lists devices and warns about group mates *(the thing Synology VMM cannot do)*
* **Browser console** — noVNC behind DSM's own login, so the console has no LAN presence; optional temporary VNC port with an expiring password
* **Snapshots & scheduling** — offline disk snapshots plus scheduled start, shutdown or snapshot with retention
* **Import & export** — JSON for lossless moves, OVA for Proxmox, ESXi or VirtualBox
* **Coexists with Synology VMM** — never touches its libvirtd or API

> [!NOTE]
> Arc VMM is still in beta and not yet proven on a wide range of real hardware. Requires DSM 7.x on x86-64 with hardware virtualization; IOMMU for passthrough.

<sub>📦 Package Center → Community → **Arc VMM**</sub>

---

<br>

### <img src="https://img.shields.io/badge/-Container-2496ED?style=flat-square" height="20"> Arc Container &nbsp;<img src="https://img.shields.io/badge/beta-2496ED?style=flat-square" height="18">

A container manager for DSM with its own, current Docker engine — independent of Synology's Container Manager and the Docker version it is stuck on.

* **Current Docker engine** — Docker's own static builds, updated with the package, so compose v2, the newer mount syntax and buildx just work
* **Containers** — create with a guided editor (ports, mounts, environment, devices, limits), start, stop, restart, pause, inspect and remove; change restart policy and limits without recreating
* **Compose projects** — edit, bring up, take down, update and read the logs of a whole stack
* **Images, volumes & networks** — pull with Docker Hub search and tag browser, bridge and macvlan networks, registry sign-in and mirrors
* **Logs & live stats** — filter, follow and download logs; live CPU, memory, network and disk use per container
* **Updates on a schedule** — one-step update for a project or container, plus timed update, start and stop tasks
* **Housekeeping** — disk usage per type with cleanup, and a choice of volume for the image store
* **Coexists with Container Manager** — its own daemon, socket and image store; never touches Synology's

> [!NOTE]
> Arc Container is still in beta and not yet proven on real hardware. Requires DSM 7.x on x86-64 and the Arc Loader. Images and containers are not shared with Container Manager, and both cannot publish the same host port.

<sub>📦 Package Center → Community → **Arc Container**</sub>

---

<br>

### <img src="https://img.shields.io/badge/-NVIDIA-76B900?style=flat-square" height="20"> Syno NVIDIA Driver

Run a real NVIDIA GPU on your NAS — install the driver from DSM and pass it into Docker.

* **Installs as a normal DSM package** — a small `.spk` that fetches the driver on demand instead of bundling it
* **Pick and switch versions from a UI** — its own web UI plus a tab in Arc Control; install, start, stop, switch or remove without SSH
* **Driver branches** — 595.x, 580.x, 550.x, 535.x LTSB and 470.x with a recommendation per GPU from a built-in compatibility table
* **Platform support** — DSM 7.2+ on kernel 5.10.55 platforms (epyc7002, v1000nk, r1000nk, geminilakenk); modules are compiled per platform
* **Full CUDA / NVENC / NVDEC userspace** — including `nvidia-smi`, persistence mode and automatic device node creation
* **Docker & Container Manager GPU support** — optional NVIDIA Container Toolkit layer that registers the `nvidia` runtime and re-asserts it after updates
* **Optional NVENC ffmpeg layer** — a jellyfin-ffmpeg build pinned to the driver's NVENC API

> [!NOTE]
> Physical / passthrough GPUs only — no vGPU and no license server.

<sub>📦 Package Center → Community → **NVIDIA Driver**</sub>

---

<br>

### <img src="https://img.shields.io/badge/-VCRT-8B5CF6?style=flat-square" height="20"> Video Compute Runtime (VCRT)

A modern, fully hardware-accelerated FFmpeg for DSM — Intel Quick Sync, AMD VCN and NVIDIA NVENC in one package.

* **FFmpeg 8.1.2 for DSM** — installs *alongside* DSM and never patches or replaces Synology's own ffmpeg
* **Intel Quick Sync & VAAPI** — iHD and i965 drivers, Media Driver, oneVPL and OpenCL, with a legacy fallback so Gen8–Gen11 (Skylake → Ice Lake, Gemini Lake, Jasper Lake) get QSV too
* **AMD acceleration** — Mesa radeonsi VAAPI with VCN decode *and* encode, RADV Vulkan and AMF, covering Polaris through RDNA 3
* **NVIDIA NVENC / NVDEC / CUDA** — compiled in, working through the NVIDIA driver package
* **Split into base + vendor packages** — download only the driver stack your hardware needs; either side updates independently
* **Broad codec coverage** — H.264, HEVC, AV1 (dav1d/SVT-AV1/libaom), VP8/VP9, VVC, AAC, Opus, FLAC, JPEG XL, WebP, plus subtitles, tone mapping, VMAF and SRT/RIST/RTMP streaming
* **~100 Jellyfin patches** — tone mapping, Dolby Vision and HDR10+ handling, CUDA/OpenCL/VAAPI/QSV filters
* **GPU diagnostics included** — `vainfo`, `vulkaninfo`, `clinfo` and render node permission setup

> [!NOTE]
> Hardware acceleration is x86-64 only. VCRT installs binaries you can point any app or script at.

<sub>📦 Package Center → Community → **Video Compute Runtime**, plus **- Intel** or **- AMD** for your GPU</sub>

---

## 🧰 More from the Arc Project

| Project | Description |
| :-- | :-- |
| [Arc Loader Essential](https://github.com/AuxXxilium/arc-essential) | Reduced-size loader, Linux 5.x models only |
| [Arc Loader Beta](https://github.com/AuxXxilium/arc-beta) | Beta releases of the Arc Loader |
| [Arc Utilities](https://github.com/AuxXxilium/arc-utils) | Tools to install, patch and activate DSM apps on Xpenology |
| [FAQ & Wiki](https://xpenology.tech/wiki) | **Read this first** |

---

## ⬇️ Download

| Release | Download | Version | Downloads |
| :-- | :-- | :-- | :-- |
| **Stable** | [get it](https://github.com/AuxXxilium/arc/releases/latest) | ![Release](https://img.shields.io/github/v/release/AuxXxilium/arc?sort=date&display_name=release&style=flat-square&logo=github&label=) | ![Downloads](https://img.shields.io/github/downloads/AuxXxilium/arc/total?style=flat-square&logo=github&label=) |
| **Essential** | [get it](https://github.com/AuxXxilium/arc-essential/releases/latest) | ![Release](https://img.shields.io/github/v/release/AuxXxilium/arc-essential?sort=date&display_name=release&style=flat-square&logo=github&label=) | ![Downloads](https://img.shields.io/github/downloads/AuxXxilium/arc-essential/total?style=flat-square&logo=github&label=) |
| **Beta** | [get it](https://github.com/AuxXxilium/arc-beta/releases/latest) | ![Release](https://img.shields.io/github/v/release/AuxXxilium/arc-beta?sort=date&display_name=release&style=flat-square&logo=github&label=) | ![Downloads](https://img.shields.io/github/downloads/AuxXxilium/arc-beta/total?style=flat-square&logo=github&label=) |
| **arx** | [get it](https://github.com/AuxXxilium/arx/releases/latest) | ![Release](https://img.shields.io/github/v/release/AuxXxilium/arx?sort=date&display_name=release&style=flat-square&logo=github&label=) | ![Downloads](https://img.shields.io/github/downloads/AuxXxilium/arx/total?style=flat-square&logo=github&label=) |

---

## 💬 Social & GitHub

<div align="center">

[![Stars](https://img.shields.io/github/stars/AuxXxilium/arc?style=for-the-badge&logo=github)](https://github.com/AuxXxilium/arc)
[![Discord](https://img.shields.io/discord/639072565155069962?style=for-the-badge&logo=discord&label=Discord)](https://discord.auxxxilium.tech)

</div>
