<p align="center">
  <img src="AppIcon.png" width="128" height="128" alt="AppBinder Icon" />
  <h1 align="center">AppBinder for macOS</h1>
  <p align="center">
    <strong>Granular Per-App Network Interface & VPN Tunnel Binding for macOS</strong>
  </p>
  <p align="center">
    <a href="https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg">
      <img src="https://img.shields.io/badge/Download-AppBinder.dmg-007AFF?style=for-the-badge&logo=apple" alt="Download AppBinder.dmg" />
    </a>
  </p>
</p>

---

## 🌟 Overview

**AppBinder** gives you granular, per-application control over your macOS network routing. Route specific apps (such as Google Chrome, Terminal, Ghostty, or custom binaries) directly through physical interfaces like **Ethernet (`en0`)** or **Wi-Fi (`en1`)**, completely bypassing system-wide VPN tunnels (`utun`), or vice-versa.

### ✨ Key Features

- **Per-Application Binding**: Map any macOS app or terminal emulator directly to a designated hardware interface or VPN tunnel.
- **VPN Bypass**: Force latency-critical apps (browsers, terminals, dev tools) to route over physical Ethernet even when a full-tunnel VPN is active.
- **Process Hierarchy Tracking**: Terminal sessions (`zsh`, `bash`) and CLI subprocesses (`curl`, `git`, `ssh`, `python`) automatically inherit their parent terminal emulator's routing rule.
- **Subprocess & Helper Support**: Seamlessly routes multi-process architectures (e.g., Google Chrome Helper, Electron renderers).
- **Apple Network System Extension**: Built using Apple's modern NetworkExtension framework (`NETransparentProxyProvider`) with kernel-level performance and 0ms connection latency.
- **Live Flow Telemetry**: Real-time dashboard showing every active flow, destination host, and routed interface.

---

## 🚀 Installation & Getting Started

### 1. Download
Download the latest disk image installer:
👉 **[Download AppBinder.dmg](https://github.com/sohrabezzati/AppBinder/releases/latest/download/AppBinder.dmg)**

### 2. Move to `/Applications`
Open `AppBinder.dmg` and drag **AppBinder** into your **Applications** folder.

> **Note:** macOS kernel security requires System Extensions to reside within the `/Applications` folder to activate.

### 3. First Launch & Security Approval
Because AppBinder is distributed outside the Mac App Store:
- **First Open**: Right-click (Control-click) `AppBinder.app` in `/Applications` and select **Open**, then click **Open**.
  *(Or run `xattr -cr /Applications/AppBinder.app` in Terminal).*
- **Approve Extension**: When prompted by macOS, allow the Network Extension in:
  **System Settings → General → Login Items & Extensions → Network Extensions → Enable AppBinder**.

---

## 🛠 Usage

1. Launch **AppBinder** and verify the status indicators in the sidebar are green (**Proxy Active**).
2. Go to **Binding Rules** → click **Add Rule**.
3. Select your application (e.g. **Google Chrome**, **Terminal**, or **Ghostty**).
4. Select the target network interface (e.g. **Ethernet (en0)**).
5. Click **Save Binding Rule**.
6. All traffic from that application will now route strictly through the designated interface!

---

## 📄 License & Distribution

AppBinder is distributed as precompiled binaries. All rights reserved.
