
<div align="center">

# 🛡️ ORYVEX VPN

### Secure · Fast · Forever Free

> *Your privacy is our mission — encrypted tunnel to a free and open internet*

<br>

[![Version](https://img.shields.io/badge/Version-1.0.0-14b8a6?style=for-the-badge&logo=git&logoColor=white)](https://github.com/ORYVEX/VPN)
[![License](https://img.shields.io/badge/License-MIT-14b8a6?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows-14b8a6?style=for-the-badge&logo=windows&logoColor=white)](https://www.microsoft.com/windows)
[![Electron](https://img.shields.io/badge/Electron-27.0.0-14b8a6?style=for-the-badge&logo=electron&logoColor=white)](https://www.electronjs.org)

</div>

---

## 📖 Table of Contents

- [About ORYVEX VPN](#-about-oryvex-vpn)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage Guide](#-usage-guide)
- [API Endpoints](#-api-endpoints)
- [Project Structure](#-project-structure)
- [Development](#-development)
- [Troubleshooting](#-troubleshooting)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 About ORYVEX VPN

**ORYVEX VPN** is a modern, secure, and lightweight VPN client built with **Electron** and powered by **Xray-core**. It provides encrypted tunneling with support for multiple protocols including VLESS, VMess, HTTPUpgrade, WebSocket, gRPC, and XHTTP.

Our mission is to provide **free and unlimited** secure internet access to everyone, without tracking, without logs, and without hidden costs.

### Why ORYVEX?

| Feature | ORYVEX | Others |
|---------|--------|--------|
| 💰 Price | **Forever Free** | Subscription-based |
| 🔒 Privacy | Zero logs | Often collect data |
| 🚀 Speed | Optimized routing | Variable |
| 🛡️ Security | XTLS + REALITY | Basic protocols |
| 📱 Support | Windows (more coming) | Limited free tier |

---

## ✨ Features

### Core Features

| Feature | Description |
|---------|-------------|
| 🔐 **Multi-Protocol Support** | VLESS, VMess, HTTPUpgrade, WebSocket, gRPC, XHTTP |
| 🚀 **XTLS Vision** | Next-generation TLS encryption |
| 🎯 **REALITY Protocol** | Advanced censorship bypass |
| ⚡ **Auto Reconnect** | Automatic reconnection on config changes |
| 🌍 **Global Server Network** | Multiple server nodes worldwide |
| 📊 **Real-time Traffic Monitor** | Live bandwidth usage tracking |
| 🎨 **Modern UI** | Glass-morphism design with Tailwind CSS |

### Security Features

```
✅ Military-grade encryption (XTLS)
✅ Perfect forward secrecy
✅ No logging policy
✅ Kill switch protection
✅ DNS leak protection
✅ Automatic config updates
```

### User Management

| Role | Access Level |
|------|-------------|
| 👑 **Owner** | Full system access + 2FA |
| 👤 **Admin** | Server management + 2FA |
| 🌟 **User** | VPN access only (forever free) |

---

## 🛠️ Tech Stack

<div align="center">

### Frontend

![Electron](https://img.shields.io/badge/Electron-47848F?style=for-the-badge&logo=electron&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### Backend

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### Core Engine

![Xray-core](https://img.shields.io/badge/Xray--core-1.8.0-14b8a6?style=for-the-badge&logo=go&logoColor=white)

</div>

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         ORYVEX VPN                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐     ┌─────────────┐     ┌─────────────┐       │
│  │   Client    │────▶│   Xray      │────▶│   Remote    │       │
│  │  (Electron) │     │   Core      │     │   Server    │       │
│  └─────────────┘     └─────────────┘     └─────────────┘       │
│         │                   │                    │             │
│         ▼                   ▼                    ▼             │
│  ┌─────────────┐     ┌─────────────┐     ┌─────────────┐       │
│  │   Local     │     │  VLESS/     │     │   Global    │       │
│  │   Proxy     │     │  VMess      │     │   Network   │       │
│  │  :10808/9   │     │  HTTPUpgrade│     │             │       │
│  └─────────────┘     └─────────────┘     └─────────────┘       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                       Server API                                │
├─────────────────────────────────────────────────────────────────┤
│  • User Authentication (2FA)                                    │
│  • Server Config Management                                     │
│  • Session Tracking                                             │
│  • Code Generation (Admin/Owner)                               │
└─────────────────────────────────────────────────────────────────┘
```

---

## 💻 Installation

### Prerequisites

| Requirement | Version |
|-------------|---------|
| Windows OS | 10 / 11 |
| Node.js | 18+ |
| Python | 3.9+ |
| Administrator privileges | Required |

### Quick Install

```bash
# Clone the repository
git clone https://github.com/ORYVEX/VPN.git
cd VPN

# Install Node dependencies
npm install

# Install Python dependencies (for server)
pip install flask flask-cors axios

# Run installer (as Administrator)
install.bat

# Start the application (as Administrator)
start.bat
```

### Server Setup

```bash
cd server
python app.py
```

Server runs on: `http://localhost:5000`

### Build from Source

```bash
# Install Electron globally
npm install -g electron

# Run in development mode
npm start

# Build executable (coming soon)
# npm run build
```

---

## ⚙️ Configuration

### Client Configuration (`main.js`)

```javascript
// API endpoints
const API_BASE = 'http://your-server:5000';
const RAW_CONFIG_URL = `${API_BASE}/token/raw`;

// Proxy ports
SOCKS_PORT = 10808;
HTTP_PORT = 10809;

// Auto-reconnect interval (ms)
RECONNECT_INTERVAL = 300000;  // 5 minutes
```

### Server Configuration (`app.py`)

```python
# Security token (keep secret!)
FIXED_TOKEN = "your-secure-token-here"

# Data directory
DATA_DIR = './data'

# Session expiration (hours)
SESSION_EXPIRY = 24

# 2FA code expiry (minutes)
CODE_EXPIRY = 5
```

### Environment Variables

```bash
# Optional: Enable development mode
FLASK_ENV=development

# Optional: Configure email for 2FA
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-password
```

---

## 🚀 Usage Guide

### First Time Setup

1. **Run as Administrator** (required for system proxy)
2. **Register** a new account
3. **Login** with your credentials
4. **Select** a server node
5. **Connect** and enjoy secure browsing

### Dashboard Overview

| Section | Description |
|---------|-------------|
| 🔘 **Power Button** | Connect/Disconnect VPN |
| 📊 **VPN Status** | Shows connection state |
| ⏱️ **Session Duration** | Connection time counter |
| 🌐 **Active Gateway** | Current server node |
| ⚡ **Optimal Node** | Auto-select best server |

### Server Nodes Panel

```
┌────────────────────────────────────────┐
│  🌍 Server Nodes                       │
├────────────────────────────────────────┤
│  🟢 Oryvex-1     45ms  ● Active       │
│  🟡 Oryvex-2    120ms                  │
│  🔴 Oryvex-3    230ms                  │
│  🟢 Oryvex-4     67ms  ● Selected     │
└────────────────────────────────────────┘
```

### Speed Test Panel

- Measures **download** and **upload** speeds
- Real-time gauge animation
- Tests connection to current server

### Settings Panel

| Option | Function |
|--------|----------|
| Auto Connect | Connect on app startup |
| Kill Switch | Block internet if VPN drops |

### Admin Panel (Browser)

Access via: `http://your-server:5000/YOUR_TOKEN/admin/codes`

```
┌─────────────────────────────────────────────────────┐
│  👑 ADMIN CODES MANAGEMENT                          │
├─────────────────────────────────────────────────────┤
│  ┌─────────────────────────────────────────────┐    │
│  │ Username: [admin    ]  [GENERATE CODE]      │    │
│  └─────────────────────────────────────────────┘    │
│                                                     │
│  ┌─────────┬──────────┬─────────────────────────┐  │
│  │  Code   │ Username │ Status                  │  │
│  ├─────────┼──────────┼─────────────────────────┤  │
│  │ 123456  │ admin    │ 🟡 Pending (4:32 left)  │  │
│  │ 789012  │ admin    │ ✅ Used                  │  │
│  └─────────┴──────────┴─────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```

---

## 📡 API Endpoints

### Authentication

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/register` | POST | Create new user account |
| `/api/login` | POST | Authenticate user |
| `/api/verify-2fa` | POST | Verify 2FA code |
| `/api/verify` | POST | Verify session token |
| `/api/logout` | POST | End user session |

### Server Management

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/configs` | GET | Retrieve server configs |
| `/YOUR_TOKEN/raw` | GET | Raw config endpoint |
| `/YOUR_TOKEN/text-uploader` | GET/POST | Manage server configs |
| `/YOUR_TOKEN/admin/codes` | GET/POST | Admin 2FA codes |
| `/YOUR_TOKEN/owner/codes` | GET/POST | Owner 2FA codes |

### API Response Format

```json
{
  "success": true,
  "message": "Operation successful",
  "data": { ... }
}
```

---

## 📁 Project Structure

```
ORYVEX-VPN/
├── 📄 main.js                 # Electron main process
├── 📄 preload.js              # Secure IPC bridge
├── 📄 renderer.js             # UI logic & events
├── 📄 index.html              # Main application UI
├── 📄 login.html              # Authentication page
├── 📄 register.html           # User registration
├── 📄 tailwind.js             # Tailwind CSS engine
├── 📄 install.bat             # Dependency installer
├── 📄 start.bat               # Application launcher
├── 📄 package.json            # Node dependencies
│
├── 📁 server/
│   ├── 📄 app.py              # Flask API server
│   └── 📁 data/               # Server data storage
│       ├── users.json         # User accounts
│       ├── servers.json       # VPN server configs
│       ├── codes.json         # Admin 2FA codes
│       ├── owner_codes.json   # Owner 2FA codes
│       ├── sessions.json      # Active sessions
│       └── pending_2fa.json   # Temporary 2FA codes
│
└── 📁 v2ray/                  # Xray-core engine
    ├── v2ray.exe              # Xray executable
    ├── geoip.dat              # IP geolocation data
    ├── geosite.dat            # Domain classification
    └── LICENSE                # Xray-core license
```

---

## 🔧 Development

### Setup Development Environment

```bash
# Clone repository
git clone https://github.com/ORYVEX/VPN.git
cd VPN

# Install dependencies
npm install

# Install server dependencies
cd server
pip install -r requirements.txt
cd ..

# Run in development mode
npm run dev
```

### Debug Mode

```javascript
// Enable debug logging in main.js
const DEBUG = true;

// Enable dev tools in mainWindow
webPreferences: { devTools: true }
```

### Build Custom Version

```bash
# Install electron-builder
npm install -g electron-builder

# Build for Windows
electron-builder --win

# Build portable version
electron-builder --win portable
```

---

## 🐛 Troubleshooting

### Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| **"Run as Administrator" error** | Right-click `start.bat` → Run as Administrator |
| **Xray core not found** | Run `install.bat` as Administrator first |
| **Connection failed** | Check server status, try different node |
| **Proxy not working** | Disable other VPN/proxy software |
| **2FA code invalid** | Code expires in 5 minutes, generate new one |
| **App freezes** | Restart application, clear temp cache |

### Logs Location

```bash
# Electron logs
%APPDATA%/oryvex-vpn/logs/

# Xray logs
%USERPROFILE%/.xray/logs/

# Server logs
server/data/debug.log
```

### Reset Application

```bash
# Clear user data
rm -rf %APPDATA%/oryvex-vpn/

# Reset server data
rm -rf server/data/*.json

# Reinstall Xray core
run install.bat again
```

---

## 🗺️ Roadmap

### Version 1.1 (Coming Soon)

- [ ] macOS support
- [ ] Linux support
- [ ] Split tunneling
- [ ] Custom DNS settings
- [ ] Connection profiles

### Version 1.2 (Planned)

- [ ] Mobile apps (iOS/Android)
- [ ] WireGuard protocol support
- [ ] Bandwidth limiter
- [ ] Ad-blocker integration
- [ ] Dark/Light theme toggle

### Version 2.0 (Future)

- [ ] P2P optimized servers
- [ ] Multi-hop connections
- [ ] Built-in speed test server
- [ ] Desktop notifications
- [ ] CLI mode for servers

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Ways to Contribute

| Type | Description |
|------|-------------|
| 🐛 **Bug Reports** | Submit issues with detailed reproduction steps |
| 💡 **Feature Requests** | Suggest new features via GitHub Issues |
| 📝 **Documentation** | Improve README, add wiki pages |
| 🔧 **Code** | Submit pull requests for bug fixes or features |
| 🌍 **Translations** | Help translate the UI to other languages |

### Pull Request Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing`)
5. Open a Pull Request

### Code Style

- **JavaScript**: ESLint configuration
- **Python**: PEP 8 guidelines
- **HTML/CSS**: Tailwind CSS utilities

---

## 📜 License

```
MIT License

Copyright (c) 2024 ORYVEX

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Acknowledgments

- [Xray-core](https://github.com/XTLS/Xray-core) - Core VPN engine
- [Electron](https://electronjs.org) - Desktop framework
- [Tailwind CSS](https://tailwindcss.com) - UI styling
- [Flask](https://flask.palletsprojects.com) - Backend API
- [Cloudflare](https://cloudflare.com) - Infrastructure

---

## 📞 Contact & Support

| Channel | Link |
|---------|------|
| 🌐 **Website** | [oryvex.com](https://oryvex.com) |
| 📧 **Email** | support@oryvex.com |
| 🐙 **GitHub** | [github.com/ORYVEX](https://github.com/ORYVEX) |
| 💬 **Telegram** | [t.me/oryvex](https://t.me/oryvex) |

---

<div align="center">

## ⭐ Star Us on GitHub

If you find ORYVEX VPN useful, please give us a star! ⭐

[![GitHub stars](https://img.shields.io/github/stars/ORYVEX/VPN?style=social)](https://github.com/ORYVEX/VPN/stargazers)

---

**Made with ❤️ by ORYVEX Team**

*Secure internet access — not a luxury, but a fundamental right*

</div>
