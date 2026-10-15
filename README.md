<p align="center">
  <img src="AppIcon.png" width="128" height="128" alt="AppBinder Icon" />
  <h1 align="center">AppBinder for macOS</h1>
  <p align="center">
    <strong>Live Per-App Bandwidth Speeds, Cumulative Data Usage Meters, 24/7 Autonomous Background Routing, Firewall Kill-Switch, Independent Download/Upload Throttling, Quotas & Xcode iOS Simulator Binding</strong>
  </p>
  <p align="center">
    <a href="https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg">
      <img src="https://img.shields.io/badge/Download-AppBinder.dmg-007AFF?style=for-the-badge&logo=apple" alt="Download AppBinder.dmg" />
    </a>
    <img src="https://img.shields.io/badge/Version-1.3.0-blue?style=for-the-badge" alt="Version 1.3.0" />
    <img src="https://img.shields.io/badge/Platform-macOS%2014%2B%20%7C%2015%2B-lightgrey?style=for-the-badge&logo=apple" alt="macOS 14+ / 15+" />
  </p>
</p>

---

## 🌟 Overview

**AppBinder** is a professional macOS utility giving you total control over application network routing, firewall permissions, bandwidth speed limits, data consumption quotas, developer simulator binding, and live bandwidth monitoring.

Force latency-sensitive apps (like Chrome, Terminal, Ghostty, or Xcode iOS Simulator) to bind strictly to physical **Ethernet (`en0`)** or specific interfaces to bypass VPN tunnels, completely isolate apps with a **zero-leak Firewall Kill-Switch**, set independent **Download and Upload Speed Caps**, monitor **Live Speeds (`⬇` / `⬆`)** across all applications, and enforce policies **24/7 in the background** — all at the Apple Network Extension kernel level with zero latency.

---

## ⚡ What's New in v1.3.0

### 1. ⚡ Live Download & Upload Speeds & Per-App Data Usage
- Real-time 1-second interval bandwidth meters display instantaneous transfer rates: `🟢 ⬇ 2.4 MB/s  ⬆ 120 KB/s`.
- Direct per-application byte tracking displays total consumed data along with independent **Download** and **Upload** breakdowns.
- Real-time live status pill directly on every policy card in **Binding Rules** and in a dedicated live activity strip in **Live Telemetry**.

### 2. 🌐 System-Wide Bandwidth & Quotas for ALL Installed Apps (Even Unconfigured)
- The **Installed Applications** catalog now continuously tracks and displays live transfer speeds and data consumption for **every installed app on macOS**, even before any rule is configured.
- Shows real-time bandwidth indicators, total transferred bytes, and active quota caps.
- Instant 1-click **Block / Unblock** firewall toggle and **Configure Policy** buttons right from the Installed Apps list.
- Quick filter control: switch seamlessly between **All Apps**, **Active Traffic** (apps actively transferring data), **Configured**, and **Unconfigured**.

### 3. 🌙 24/7 Autonomous Background Execution (Works When App Is Closed)
- Low-level network interception, per-app interface binding, rate-limiting, and firewall kill-switches run inside the privileged root System Extension daemon (`ProxyExtension`).
- Runs continuously 24/7 managed by macOS `sysextd` and `launchd` without requiring the `AppBinder.app` user interface to stay open.
- Rules and cumulative counters are automatically mirrored to `/Users/Shared/AppBinder/rules.json`, allowing the daemon to load and enforce policies autonomously on system boot.

### 4. 🚀 Launch Automatically on macOS Login
- Native login item management powered by Apple’s modern `SMAppService.mainApp` API (macOS 13+ / 14 Sonoma / 15 Sequoia).
- Toggleable directly from **Settings → Startup & Background Operation**.
- Ensures seamless background notifications and live graph streaming upon login with zero manual intervention.

### 5. 📱 Reliable Xcode iOS Simulator Live Speeds & Quotas
- Direct attribution across all CoreSimulator, `launchd_sim`, and runtime helper processes (`configd_sim`, `simdeviceio`, `CoreSimulatorBridge`, `com.apple.WebKit.WebContent`).
- Full support for live speed gauges (`⬇` / `⬆`), rate limiting, and quota enforcement across iOS Simulator network traffic.

---

## 🛡️ Core Capabilities

### 🔹 Granular Network Interface Binding
- Bind applications strictly to physical hardware interfaces (Ethernet `en0`, Wi-Fi `en1`) or VPN tunnels (`utun`).
- Process hierarchy tracking: Terminal sessions (`zsh`, `bash`) and CLI subprocesses (`curl`, `git`, `ssh`, `python`) automatically inherit their parent terminal emulator's routing rule.

### 🔹 Per-App Firewall & Internet Kill-Switch
- Instantly block any macOS app or CLI tool from accessing the internet.
- Zero-leak kernel enforcement immediately refuses outbound TCP and UDP connections (`ECONNREFUSED`).
- One-click **Block / Unblock** toggle directly on each application card.

### 🔹 Independent Download & Upload Bandwidth Throttling
- Rate-limit download and upload speeds separately per application (e.g. 1 MB/s download / 256 KB/s upload).
- Dual **Token Bucket Limiters** using TCP window backpressure smooth traffic without dropping packets.

### 🔹 Independent Download & Upload Data Quotas
- Set independent data caps for download and upload traffic (e.g., 5 GB download / 500 MB upload).
- Dual live progress bars with dynamic color alerts:
  - 🔵 Normal (<80%)
  - 🟠 Warning (80%–99%)
  - 🔴 Quota Exceeded (100% — traffic paused automatically)
- One-click meter reset button to clear counters at any time.

### 🔹 Modern Configuration Canvas
- Clean chip preset grids (`Unlimited`, `256 KB/s`, `512 KB/s`, `1 MB/s`, `2 MB/s`, `5 MB/s`, `Custom...`) for both download and upload.
- Dedicated custom pickers with unit selection (`KB/s`, `MB/s`, `MB`, `GB`) and live Mbps conversion.

### 🔹 Dedicated Settings & Rules Backup
- Export all rules to formatted JSON, import from backup, and batch reset meters.
- Auto-sync guarantees policies are instantly applied upon app launch and tunnel reconnects.

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
2. Go to **Binding Rules** → click **Add Rule** (or open **Installed Apps** to browse discovered applications).
3. Select your application:
   - **Mode: Route via Interface**: Select your network interface (e.g., Ethernet `en0`), and optionally configure independent download/upload speed limits or data quotas.
   - **Mode: Block Internet (Kill-Switch)**: Completely isolate the application from the network.
4. Click **Save Policy Rule** — all policies apply instantly in real time!

---

## 📄 Distribution

AppBinder is distributed as precompiled release binaries. All rights reserved.
