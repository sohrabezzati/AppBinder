<p align="center">
  <img src="AppIcon.png" width="128" height="128" alt="AppBinder Icon" />
  <h1 align="center">AppBinder for macOS</h1>
  <p align="center">
    <strong>Granular Per-App Network Interface Routing, Firewall Kill-Switch, Independent Download/Upload Throttling & Data Quotas for macOS</strong>
  </p>
  <p align="center">
    <a href="https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg">
      <img src="https://img.shields.io/badge/Download-AppBinder.dmg-007AFF?style=for-the-badge&logo=apple" alt="Download AppBinder.dmg" />
    </a>
    <img src="https://img.shields.io/badge/Version-1.2.0-blue?style=for-the-badge" alt="Version 1.2.0" />
    <img src="https://img.shields.io/badge/Platform-macOS%2014%2B%20%7C%2015%2B-lightgrey?style=for-the-badge&logo=apple" alt="macOS 14+ / 15+" />
  </p>
</p>

---

## 🌟 Overview

**AppBinder** is a professional macOS utility giving you total control over application network routing, firewall permissions, bandwidth speed limits, and monthly data consumption.

Force latency-sensitive apps (like Chrome, Terminal, or Ghostty) to bind strictly to physical **Ethernet (`en0`)** to bypass VPN tunnels, completely isolate apps with a **zero-leak Firewall Kill-Switch**, set independent **Download and Upload Speed Caps**, and enforce **Data Quotas** with live meters — all enforced at the Apple Network Extension kernel level with zero latency.

---

## ⚡ Key Capabilities (v1.2.0)

### 1. 🛡️ Per-App Firewall & Internet Kill-Switch
- Instantly block any macOS app or CLI tool from accessing the internet.
- Zero-leak kernel enforcement immediately refuses outbound TCP and UDP connections (`ECONNREFUSED`).
- One-click **Block / Unblock** button right on each application card.

### 2. ⬇️ / ⬆️ Independent Download & Upload Bandwidth Throttling
- Rate-limit download and upload speeds separately per application!
- Presets: `Unlimited`, `256 KB/s`, `512 KB/s`, `1 MB/s`, `2 MB/s`, `5 MB/s`.
- **Custom Rate Inputs**: Enter custom speeds in `KB/s` or `MB/s` with live Mbps calculations.
- Implemented with dual **Token Bucket Limiters** using TCP window backpressure, smoothing bandwidth without dropping packets.

### 3. 📊 Independent Download & Upload Data Quotas
- Set independent data caps for download and upload traffic (e.g., 2 GB download / 200 MB upload).
- Presets: `No Limit`, `100 MB`, `500 MB`, `1 GB`, `2 GB`, `5 GB`, or **Custom Caps** in `MB` or `GB`.
- Dual live progress bars with dynamic color alerts:
  - 🔵 Normal (<80%)
  - 🟠 Warning (80%–99%)
  - 🔴 Quota Exceeded (100% — traffic paused automatically)
- One-click meter reset button to clear counters at any time.

### 4. 📁 Select Any Application or CLI Binary
- **Installed Apps**: Search all discovered macOS applications.
- **Choose File...**: Pick ANY application, helper, or Unix binary (`/bin`, `/usr/local/bin`, Homebrew) via native file browser.
- **Custom Identifiers**: Enter custom bundle IDs or process names directly (`curl`, `git`, `python3`).
- **Custom Interface / IP**: Bind to custom virtual interfaces or static IP gateways.

### 5. ⚙️ Dedicated Settings Dashboard
- Real-time System Extension & Transparent Proxy lifecycle management.
- General Preferences: Auto-start proxy on app launch, quota notifications, kill-switch alerts.
- **Rules Backup & Restore**: Export all rules to JSON, import from backup, and batch reset meters.

### 6. 🌐 Physical Interface & VPN Tunnel Binding
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
3. Pick your application:
   - **Mode: Route via Interface**: Select your network interface (e.g., Ethernet `en0`), and optionally set separate download/upload speed limits or data quotas.
   - **Mode: Block Internet (Kill-Switch)**: Completely isolate the application from the network.
4. Click **Save Policy Rule** — all policies apply instantly in real time!

---

## 📄 Distribution

AppBinder is distributed as precompiled release binaries. All rights reserved.
