<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.1-blue" alt="Version 1.0.1" />
  <img src="https://img.shields.io/badge/platform-Windows%2010%2F11-0078D6?logo=windows" alt="Windows 10/11" />
  <img src="https://img.shields.io/badge/.NET-10.0-512BD4?logo=dotnet" alt=".NET 10" />
  <img src="https://img.shields.io/badge/license-proprietary-gray" alt="License" />
</p>

# Nexus

**A powerful, modern remote desktop connection manager for Windows.**

Nexus lets you organize, connect to, and manage hundreds of remote machines from a single interface. It supports multiple protocols, tabbed sessions, split-pane views, encrypted credential vaults, session recording, and much more — all wrapped in a polished WPF desktop application with dark and light themes.

<p align="center">
  <a href="https://github.com/sultanfu/Nexus-Releases/releases/latest">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-28a745?style=for-the-badge&logo=github" alt="Download" />
  </a>
</p>

---

## Table of Contents

- [Key Features](#key-features)
- [Supported Protocols](#supported-protocols)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Feature Overview](#feature-overview)
  - [Connection Management](#connection-management)
  - [Session Management](#session-management)
  - [Credential Security](#credential-security)
  - [Import & Export](#import--export)
  - [Session Recording & Playback](#session-recording--playback)
  - [SFTP File Transfer](#sftp-file-transfer)
  - [Network Topology Map](#network-topology-map)
  - [Command Snippets](#command-snippets)
  - [Broadcast Mode](#broadcast-mode)
  - [Automation & Scripting](#automation--scripting)
  - [Connection Health Monitoring](#connection-health-monitoring)
  - [Audit Logging](#audit-logging)
  - [Backup & Restore](#backup--restore)
  - [Auto-Update](#auto-update)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Technology Stack](#technology-stack)
- [Architecture](#architecture)
- [System Requirements](#system-requirements)
- [File Formats](#file-formats)
- [FAQ](#faq)

---

## Key Features

| Feature | Description |
|---|---|
| **Multi-Protocol** | RDP, SSH, VNC, and Telnet in one app |
| **Tabbed Sessions** | Work with dozens of connections simultaneously |
| **Split View** | Side-by-side or stacked panes for comparing servers |
| **Grid View** | Thumbnail overview of all open sessions |
| **Broadcast Mode** | Type once, send to multiple sessions at the same time |
| **Encrypted Vault** | AES-256-GCM master-password vault for credentials |
| **Session Recording** | Record and replay terminal sessions with full timeline control |
| **SFTP** | Built-in file transfer for SSH connections |
| **Topology Map** | Visual network map of all your connections |
| **Groups, Tags & Favorites** | Organize connections your way |
| **Pre/Post-Connect Scripts** | Automate tasks with PowerShell or batch scripts |
| **Dark & Light Themes** | Switch instantly with a single click |
| **Import/Export** | RDP files, CSV, mRemoteNG, encrypted `.nexuspack` packages |
| **Auto-Update** | Checks for updates on startup and installs seamlessly |
| **Portable & Installer** | Choose between a standalone EXE or full installer |

---

## Supported Protocols

### RDP (Remote Desktop Protocol)
Full-featured RDP client powered by the native Windows `mstscax` ActiveX control.
- Multi-monitor support and custom resolutions
- Clipboard, printer, drive, and smart card redirection
- Audio playback and capture redirection
- Network Level Authentication (NLA)
- RD Gateway support with separate credentials
- Performance tuning (wallpaper, themes, font smoothing, desktop composition)
- Dynamic desktop resize without reconnecting
- Connection bar in full-screen mode

### SSH (Secure Shell)
Built on the SSH.NET library with a full terminal emulator (xterm-256color).
- Password and private key authentication
- SSH jump host / bastion proxy (multi-hop connections)
- Port forwarding: local, remote, and dynamic (SOCKS) tunnels
- Integrated SFTP file transfer
- SOCKS4, SOCKS5, and HTTP proxy support
- Anti-idle keep-alive
- Session recording

### VNC (Virtual Network Computing)
Native RFB protocol implementation with DES challenge-response authentication.
- Raw and incremental framebuffer updates
- Mouse and keyboard input forwarding
- Bitmap caching for performance
- Session recording

### Telnet
TCP-based terminal protocol with option negotiation.
- Terminal emulation
- Telnet IAC command handling
- Session recording

---

## Installation

### Option 1: Installer (Recommended)
1. Download **`Nexus.Setup.exe`** from the [latest release](https://github.com/sultanfu/Nexus-Releases/releases/latest)
2. Run the installer — it will download and install Nexus to `%LocalAppData%\Programs\Nexus\`
3. Start Menu shortcut and optional desktop shortcut are created automatically
4. The app registers in Add/Remove Programs for clean uninstallation

### Option 2: Portable
1. Download **`Nexus.App.exe`** from the [latest release](https://github.com/sultanfu/Nexus-Releases/releases/latest)
2. Place it anywhere and run — no installation required
3. Data is stored in `%LocalAppData%\Nexus\`

> **Note:** Both downloads are self-contained — no .NET runtime installation is required.

---

## Quick Start

1. **Launch Nexus** — The app opens with a dark-themed interface and an empty connection list
2. **Add a connection** — Press `Ctrl+N` or click the **+** button in the toolbar
3. **Fill in details** — Choose a protocol (RDP/SSH/VNC/Telnet), enter hostname, port, and credentials
4. **Connect** — Double-click the connection in the sidebar or press Enter
5. **Organize** — Create groups (`Ctrl+G`), add tags, mark favorites with the star icon
6. **Quick Connect** — Press `Ctrl+K` to open the quick connect overlay; type `ssh://user@host` or just a hostname

---

## Feature Overview

### Connection Management

**Groups & Hierarchy**
Organize connections into nested groups with a tree view in the sidebar. Drag and drop connections between groups, or use the right-click context menu to move them.

**Favorites & Recent**
Star your most-used connections for quick access. The sidebar shows your favorites and recently connected sessions separately.

**Tags**
Assign color-coded tags to connections for cross-group categorization. Filter and search by tags.

**Search & Quick Connect**
Real-time search (`Ctrl+Q`) across all connection names and hostnames. The Quick Connect overlay (`Ctrl+K`) supports protocol prefixes like `ssh://`, `rdp://`, `vnc://`, and `telnet://` with `host:port` syntax.

**Connection Templates**
Save connection configurations as reusable templates. When creating a new connection, select a template to pre-fill all settings.

**Per-Connection Settings**
Each connection has its own detailed settings across multiple tabs:
- **General** — Name, protocol, hostname, port, credentials, group, notes
- **Display** — Resolution, color depth, full-screen, multi-monitor
- **Local Resources** — Clipboard, printers, drives, smart cards, audio
- **Gateway** — RD Gateway server and credentials
- **Performance** — Visual effects and bandwidth optimization
- **Security** — NLA configuration
- **Scripts** — Pre-connect and post-disconnect automation
- **Proxy** — SOCKS4/5 or HTTP proxy settings

---

### Session Management

**Tabbed Interface**
Open multiple connections in tabs. Navigate with `Ctrl+Tab` / `Ctrl+Shift+Tab`, close with `Ctrl+W`, or use the tab context menu.

**Split View**
View two sessions side by side (`Ctrl+|` for vertical, `Ctrl+-` for horizontal). Each pane operates independently.

**Grid View**
Toggle thumbnail grid view to see all open sessions at a glance. Click any thumbnail to switch to that session.

**Full-Screen Mode**
Press `F11` to maximize the active session. A floating connection bar provides quick access to controls.

**Screenshots**
Capture the current session with `Ctrl+Shift+S`. Screenshots are saved to `Pictures\Nexus\` with timestamps.

---

### Credential Security

**DPAPI Encryption**
By default, credentials are encrypted using Windows Data Protection API (DPAPI), tied to your Windows user account.

**Master Password Vault**
For stronger, portable security, enable the credential vault:
- AES-256-GCM encryption with PBKDF2 key derivation (100,000 iterations, SHA-256)
- Independent of your Windows account — works if you move machines
- Stored as a `.nexusvault` file
- Change the master password at any time

**Inline Credential Creation**
Create new credentials directly from the connection dialog without losing your place.

---

### Import & Export

| Format | Import | Export | Description |
|---|:---:|:---:|---|
| `.nexuspack` | Yes | Yes | Encrypted package with connections, groups, tags, and optional credentials (AES-256, passphrase-protected) |
| `.rdp` | Yes | Yes | Standard Remote Desktop Protocol files (single or batch folder) |
| `.csv` | Yes | Yes | Spreadsheet format — columns: Name, Hostname, Port, Group, Credential |
| `mRemoteNG` | Yes | — | Import from mRemoteNG's `confCons.xml` configuration file |

**Import Preview** — Review all connections before importing, with conflict resolution for duplicates.

---

### Session Recording & Playback

Record SSH and Telnet terminal sessions for training, auditing, or documentation:
- Recordings capture all terminal I/O with precise timestamps
- Stored in `.nexusrec` binary format
- **Playback player** with play/pause/stop, timeline scrubbing, and speed control (0.5x, 1x, 2x, 4x)
- Metadata tracking: connection name, protocol, duration, file size

---

### SFTP File Transfer

Built-in file transfer for SSH connections:
- Browse the remote file system
- Upload and download files with progress indicators
- Create and delete directories
- View file permissions and metadata

---

### Network Topology Map

Visualize your entire connection infrastructure on an interactive canvas:
- Connections displayed as nodes grouped by their organization groups
- Color-coded status indicators (online/offline)
- Protocol icons (RDP, SSH, VNC, Telnet)
- Drag nodes to rearrange, zoom in/out, pan the canvas
- Double-click or right-click a node to connect

---

### Command Snippets

Save frequently-used terminal commands for quick reuse:
- Organize snippets by category
- Click to send a snippet directly to the active SSH/Telnet session
- Toggle the snippets panel from the toolbar

---

### Broadcast Mode

Send keyboard input to multiple sessions simultaneously:
- Enable broadcast from the toolbar
- Select which sessions receive input
- Ideal for running the same command across a fleet of servers

---

### Automation & Scripting

**Pre-Connect Scripts**
Run a PowerShell or batch script before a connection is established — useful for VPN setup, network checks, or environment preparation.

**Post-Disconnect Scripts**
Run cleanup scripts after a session ends — useful for logging, notifications, or teardown.

**Environment Variables**
Scripts receive connection details automatically:
- `NEXUS_HOSTNAME` — target hostname
- `NEXUS_PORT` — target port
- `NEXUS_USERNAME` — connection username

**Configurable Timeout**
Scripts are enforced with a timeout (default 30 seconds) to prevent hangs.

---

### Connection Health Monitoring

Background health checks continuously monitor server availability:
- Green/red/gray status dots on each connection in the sidebar
- Real-time status change detection
- Configurable poll interval (default 60 seconds)
- Smart monitoring — only checks visible connections to minimize traffic

---

### Audit Logging

Track all connection activity for compliance and review:
- **Events tracked:** Connected, Disconnected, ConnectionFailed, SessionReconnected
- Each entry records: connection name, hostname, protocol, username, timestamp
- View logs in Settings > Audit Log with pagination
- Persistent database storage

---

### Backup & Restore

- Automatic periodic backups of the connection database
- Manual backup creation
- View backup history with file sizes and dates
- One-click restore to any backup point

---

### Auto-Update

- Nexus checks for updates automatically on startup
- An update banner appears with version info and release notes
- Click to update — the installer handles the rest
- Skip a version if you prefer to wait

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+N` | New connection |
| `Ctrl+G` | New group |
| `Ctrl+K` | Quick connect overlay |
| `Ctrl+Q` / `Ctrl+F` | Focus search |
| `Ctrl+W` | Close active tab |
| `Ctrl+Tab` | Next tab |
| `Ctrl+Shift+Tab` | Previous tab |
| `F11` | Toggle full-screen |
| `Escape` | Exit full-screen |
| `Ctrl+\|` | Split vertical |
| `Ctrl+-` | Split horizontal |
| `Ctrl+Shift+S` | Screenshot |
| `Ctrl+,` | Open settings |

---

## Technology Stack

| Component | Technology |
|---|---|
| **Framework** | .NET 10.0 (self-contained, no runtime needed) |
| **UI** | WPF (Windows Presentation Foundation) |
| **Architecture** | MVVM with CommunityToolkit.Mvvm |
| **Database** | SQLite via Entity Framework Core 9 |
| **RDP** | Native `mstscax` ActiveX control (COM interop) |
| **SSH/SFTP** | SSH.NET 2025.1.0 |
| **VNC** | Custom RFB protocol implementation |
| **Telnet** | Custom implementation with IAC negotiation |
| **Logging** | Serilog with rolling file sinks (14-day retention) |
| **Encryption** | DPAPI + AES-256-GCM (vault) + PBKDF2 key derivation |
| **DI** | Microsoft.Extensions.DependencyInjection |
| **Installer** | Custom WPF setup wizard with GitHub Releases integration |
| **Code Signing** | Authenticode SHA-256 with DigiCert timestamping |

---

## Architecture

Nexus is built with a clean layered architecture across six projects:

```
Nexus.slnx
├── Nexus.App        UI layer — WPF views, XAML, dialogs, themes
├── Nexus.Core       Business logic — ViewModels, services, models
├── Nexus.Data       Data access — EF Core, SQLite, entities, migrations
├── Nexus.Rdp        Protocol layer — RDP, SSH, VNC, Telnet session hosts
├── Nexus.Web        Web interface — ASP.NET Core, Guacamole integration
└── Nexus.Setup      Installer — WPF setup wizard, GitHub release downloader
```

**Data Flow:**
```
User Input → Views (XAML) → ViewModels (MVVM) → Services → Data (EF Core / SQLite)
                                                    ↓
                                             Session Hosts (RDP/SSH/VNC/Telnet)
```

**Key Design Patterns:**
- **MVVM** — Views are data-bound to ViewModels via WPF bindings
- **Dependency Injection** — Services registered in a DI container, injected via constructors
- **Repository Pattern** — EF Core DbContext with async operations
- **Strategy Pattern** — `ISessionHost` interface with protocol-specific implementations
- **Observer Pattern** — `INotifyPropertyChanged` for reactive UI updates

---

## System Requirements

| Requirement | Details |
|---|---|
| **OS** | Windows 10 version 1809 or later, Windows 11 |
| **Architecture** | x64 (64-bit) |
| **.NET** | Not required — bundled in the self-contained executable |
| **Disk Space** | ~80 MB (app), ~65 MB (installer) |
| **RAM** | 100 MB minimum + ~20 MB per active session |
| **Display** | 1280x720 minimum, 1920x1080 recommended |
| **Network** | Internet connection required for initial download and updates |

---

## File Formats

| Extension | Description | Encryption |
|---|---|---|
| `.nexuspack` | Connection package for sharing/backup | AES-256, passphrase-protected |
| `.nexusvault` | Credential vault | AES-256-GCM, master password |
| `.nexusrec` | Session recording | None (terminal I/O log) |
| `nexus.db` | Application database | SQLite (credentials encrypted via DPAPI) |

---

## FAQ

**Q: Is Nexus free?**
A: Yes. Nexus is free to download and use.

**Q: Does Nexus require .NET to be installed?**
A: No. The executables are self-contained and include the .NET runtime.

**Q: Where is my data stored?**
A: All data (database, vault, recordings, logs) is stored in `%LocalAppData%\Nexus\`.

**Q: Can I move Nexus to another computer?**
A: Copy the `%LocalAppData%\Nexus\` folder and the app executable. If you use the DPAPI-encrypted credentials (default), you'll need to re-enter passwords. If you use the master password vault (`.nexusvault`), credentials transfer seamlessly.

**Q: How do I migrate from mRemoteNG?**
A: Go to Settings > Import/Export > Import from mRemoteNG, then select your `confCons.xml` file.

**Q: Does Nexus phone home or collect telemetry?**
A: No. The only network call Nexus makes is checking the GitHub Releases API for updates, which can be dismissed.

**Q: Why does SmartScreen warn about an unknown publisher?**
A: The executables are signed with a self-signed certificate. SmartScreen warnings will be resolved in a future release with a trusted CA certificate. The app is safe — you can verify the signature in the file's Properties > Digital Signatures tab.

---

<p align="center">
  <sub>Built by <a href="https://github.com/sultanfu">sultanfu</a> &mdash; Copyright &copy; 2026</sub>
</p>
