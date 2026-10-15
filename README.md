<p align="center">
  <img src="AppIcon.png" width="128" height="128" alt="AppBinder Icon" />
  <h1 align="center">AppBinder for macOS</h1>
  <p align="center">
    <strong>Granular Per-App Network Interface Routing, Firewall Kill-Switch, Bandwidth Throttling & Data Quota Control for macOS</strong>
  </p>
  <p align="center">
    <a href="https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg">
      <img src="https://img.shields.io/badge/Download-AppBinder.dmg-007AFF?style=for-the-badge&logo=apple" alt="Download AppBinder.dmg" />
    </a>
    <img src="https://img.shields.io/badge/Version-1.1.0-blue?style=for-the-badge" alt="Version 1.1.0" />
    <img src="https://img.shields.io/badge/Platform-macOS%2014%2B%20%7C%2015%2B-lightgrey?style=for-the-badge&logo=apple" alt="macOS 14+ / 15+" />
  </p>
</p>

---

## 🌟 Overview

**AppBinder** gives you complete, granular control over every application's network access on macOS. 

Whether you want to force specific apps (like Chrome, Terminal, or Ghostty) to bind strictly to physical **Ethernet (`en0`)** to bypass VPN tunnels, completely isolate apps with a **zero-leak Firewall Kill-Switch**, throttle download bandwidth, or enforce monthly **Data Quotas**, AppBinder handles it all at the kernel level with zero latency.

---

## ⚡ Supercharged Capabilities (v1.1.0)

### 1. 🛡️ Per-App Firewall & Internet Kill-Switch
- Instantly block any macOS app or CLI tool from accessing the internet.
- Zero-leak kernel enforcement immediately refuses outbound TCP and UDP connections (`ECONNREFUSED`).
- One-click **Block / Unblock** button right on each application card.

### 2. ⚡ Per-App Bandwidth Speed Throttling
- Rate-limit download speeds per application: `256 KB/s`, `512 KB/s`, `1 MB/s`, `2 MB/s`, `5 MB/s`, or `Unlimited`.
- Implemented with a high-performance **Token Bucket Algorithm** with TCP window backpressure, smoothing bandwidth without dropping packets.

### 3. 📊 Per-App Data Cap & Live Usage Metering
- Set data transfer quotas: `100 MB`, `500 MB`, `1 GB`, `2 GB`, `5 GB`, or `Unlimited`.
- Live visual progress bar with dynamic color indicators:
  - 🔵 Normal (<80%)
  - 🟠 Warning (80%–99%)
  - 🔴 Quota Exceeded (100% — traffic paused automatically)
- One-click quota reset button (`arrow.clockwise`) to clear usage meters at any time.

### 4. 🌐 Per-App Network Interface & VPN Tunnel Binding
- Bind applications strictly to physical hardware interfaces (Ethernet `en0`, Wi-Fi `en1`) or VPN tunnels (`utun`).
- Force latency-critical apps to route over physical Ethernet even when a full-tunnel corporate VPN is active.
- Process hierarchy tracking: Terminal sessions (`zsh`, `bash`) and CLI subprocesses (`curl`, `git`, `ssh`, `python`) automatically inherit their parent terminal emulator's routing rule.

### 5. 🎨 World-Class macOS UI & Live Telemetry
- Card-based policy management with real-time status badges and instant controls.
- Live telemetry stream capturing all intercepted flows with search, filtering (All, Routed, Blocked), and real-time packet counters.

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
   - **Mode: Route via Interface**: Select your network interface (e.g., Ethernet `en0`), and optionally set a speed cap or data quota.
   - **Mode: Block Internet (Kill-Switch)**: Completely isolate the application from the network.
4. Click **Save Policy Rule** — all policies apply instantly in real time!

---

## 📄 Distribution

AppBinder is distributed as precompiled, notarized-ready release binaries. All rights reserved.
