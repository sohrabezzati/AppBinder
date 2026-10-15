<p align="center">
  <img src="AppIcon.png" width="128" height="128" alt="AppBinder Icon" />
  <h1 align="center">AppBinder for macOS</h1>
  <p align="center">
    <strong>Granular Per-App Network Interface Routing, Firewall Kill-Switch, Independent Download/Upload Throttling, Data Quotas & Xcode iOS Simulator Binding for macOS</strong>
  </p>
  <p align="center">
    <a href="https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg">
      <img src="https://img.shields.io/badge/Download-AppBinder.dmg-007AFF?style=for-the-badge&logo=apple" alt="Download AppBinder.dmg" />
    </a>
    <img src="https://img.shields.io/badge/Version-1.2.1-blue?style=for-the-badge" alt="Version 1.2.1" />
    <img src="https://img.shields.io/badge/Platform-macOS%2014%2B%20%7C%2015%2B-lightgrey?style=for-the-badge&logo=apple" alt="macOS 14+ / 15+" />
  </p>
</p>

---

## 🌟 Overview

**AppBinder** is a professional macOS utility giving you total control over application network routing, firewall permissions, bandwidth speed limits, monthly data consumption, and developer simulator binding.

Force latency-sensitive apps (like Chrome, Terminal, Ghostty, or Xcode iOS Simulator) to bind strictly to physical **Ethernet (`en0`)** or specific interfaces to bypass VPN tunnels, completely isolate apps with a **zero-leak Firewall Kill-Switch**, set independent **Download and Upload Speed Caps**, and enforce **Data Quotas** with live meters — all enforced at the Apple Network Extension kernel level with zero latency.

---

## ⚡ Key Capabilities (v1.2.1)

### 1. 📱 Xcode iOS Simulator Full Network Binding
- Seamlessly binds all traffic from **Xcode iOS Simulator** to your designated network interface (e.g. Ethernet `en0`).
- Deep inspection across simulator runtime layers: automatically captures mobile Safari (`com.apple.WebKit.Networking`), Flutter / React Native / native simulated apps (e.g. `Runner.app`), and `launchd_sim` background daemons.
- Automatic discovery of Xcode developer applications (`Simulator.app`, Instruments) in the Installed Apps catalog with native icons.

### 2. 🎨 Redesigned Modern Policy Configuration Dialog
- Spacious, native macOS configuration canvas with zero truncated controls or clipped headers.
- **Speed & Quota Preset Grids**: Clean 2x3 chip grids (`Unlimited`, `256 KB/s`, `512 KB/s`, `1 MB/s`, `2 MB/s`, `5 MB/s`, `Custom...`) for both download and upload.
- **Dedicated Custom Pickers**: Clean numeric inputs with dedicated unit pickers (`KB/s` / `MB/s` and `MB` / `GB`) with live Mbps conversion.
- Native interface selection dropdown with real-time IP badges.

### 3. 🛡️ Per-App Firewall & Internet Kill-Switch
- Instantly block any macOS app or CLI tool from accessing the internet.
- Zero-leak kernel enforcement immediately refuses outbound TCP and UDP connections (`ECONNREFUSED`).
- One-click **Block / Unblock** button right on each application card.

### 4. ⬇️ / ⬆️ Independent Download & Upload Bandwidth Throttling
- Rate-limit download and upload speeds separately per application!
- Implemented with dual **Token Bucket Limiters** using TCP window backpressure, smoothing bandwidth without dropping packets.

### 5. 📊 Independent Download & Upload Data Quotas
- Set independent data caps for download and upload traffic (e.g., 2 GB download / 200 MB upload).
- Dual live progress bars with dynamic color alerts:
  - 🔵 Normal (<80%)
  - 🟠 Warning (80%–99%)
  - 🔴 Quota Exceeded (100% — traffic paused automatically)
- One-click meter reset button to clear counters at any time.

### 6. 📁 Select Any Application or CLI Binary
- **Installed Apps**: Search all discovered macOS applications.
- **Choose File...**: Pick ANY application, helper, or Unix binary (`/bin`, `/usr/local/bin`, Homebrew) via native file browser.
- **Custom Identifiers**: Enter custom bundle IDs or process names directly (`curl`, `git`, `python3`).
- **Custom Interface / IP**: Bind to custom virtual interfaces or static IP gateways.

### 7. ⚙️ Dedicated Settings Dashboard & Auto-Sync
- Real-time System Extension & Transparent Proxy lifecycle management.
- General Preferences: Auto-start proxy on app launch, quota notifications, kill-switch alerts.
- **Rules Backup & Restore**: Export all rules to JSON, import from backup, and batch reset meters.
- **Persistent Rule Auto-Sync**: Automatic synchronization ensures all saved rules are instantly applied upon app launch, proxy tunnel connection, and reconnects.

### 8. 🌐 Physical Interface & VPN Tunnel Binding
- Bind applications strictly to physical hardware interfaces (Ethernet `en0`, Wi-Fi `en1`) or VPN tunnels (`utun`).
- Process hierarchy tracking: Terminal sessions (`zsh`, `bash`) and CLI subprocesses (`curl`, `git`, `ssh`, `python`) automatically inherit their parent terminal emulator's routing rule.

---

## 🚀 Installation & Setup

### 1. Download
👉 **[Download AppBinder.dmg](https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg)**

### 2. Move to `/Applications`
Open `AppBinder.dmg` and drag **AppBinder** into your **Applications** folder.

> **Note:** macOS kernel security requires System Extensions to reside within `/Applications` to activate.

### 3. First Launch & Security Approval
Because AppBinder is distributed outside the Mac App Store:
- **First Open**: Right-click (Control-click) `AppBinder.app` in `/Applications` and select **Open**, then click **Open**.
  *(Alternatively, run `xattr -cr /Applications/AppBinder.app` in Terminal).*
- **Approve Extension**: When prompted by macOS, allow the Network Extension in:
  **System Settings → General → Login Items & Extensions → Network Extensions → Enable AppBinder**.

---

## 🛠 Quick Usage

1. Launch **AppBinder** and verify the status indicator in the sidebar shows **Proxy Active**.
2. Go to **Binding Rules** → click **Add Rule**.
3. Pick your application (or select **Simulator** for Xcode iOS Simulator):
   - **Mode: Route via Interface**: Select your network interface (e.g., Ethernet `en0`), and optionally set separate download/upload speed limits or data quotas.
   - **Mode: Block Internet (Kill-Switch)**: Completely isolate the application from the network.
4. Click **Save Policy Rule** — all policies apply instantly in real time!

---

## 📄 Distribution

AppBinder is distributed as precompiled release binaries. All rights reserved.
