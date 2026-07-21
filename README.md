<div align="center">

<img src="https://img.shields.io/badge/TryHackMe-Pickle%20Rick-00b894?style=for-the-badge&logo=tryhackme&logoColor=white" />
<img src="https://img.shields.io/badge/Difficulty-Easy-00b894?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Completed-00b894?style=for-the-badge" />
<img src="https://img.shields.io/badge/Linux-FF6B6B?style=for-the-badge&logo=linux&logoColor=white" />

#  Pickle Rick - Complete Walkthrough

> *"Wubbalubbadubdub!"* — Rick Sanchez

**A comprehensive, step-by-step guide to conquering the Pickle Rick room on TryHackMe.**

[![TryHackMe](https://img.shields.io/badge/Platform-TryHackMe-212529?style=flat-square&logo=tryhackme)](https://tryhackme.com)
[![License](https://img.shields.io/badge/License-MIT-212529?style=flat-square)](LICENSE)

</div>

---

## 🎯 Room Overview

| 🏷️ Property | 📋 Value |
|:-----------:|:---------|
| **Room Name** | Pickle Rick |
| **Platform** | [TryHackMe](https://tryhackme.com) |
| **Difficulty** | 🟢 Easy |
| **Category** | Web Exploitation / Linux Privilege Escalation |
| **Status** | ✅ Completed |

---

## 📖 Table of Contents

- [🎯 Room Overview](#-room-overview)
- [📖 Table of Contents](#-table-of-contents)
- [🚀 Quick Start](#-quick-start)
- [🗺️ Attack Path](#️-attack-path)
- [📁 Repository Structure](#-repository-structure)
- [🛠️ Tools Used](#️-tools-used)
- [📝 Step-by-Step Walkthrough](#-step-by-step-walkthrough)
- [🏆 Flags Captured](#-flags-captured)
- [💡 Key Takeaways](#-key-takeaways)
- [🛡️ Disclaimer](#️-disclaimer)

---

## 🚀 Quick Start

```bash
# 🔍 Step 1: Port Scanning
nmap -sV -sC <TARGET_IP>

# 🕵️ Step 2: Web Enumeration
curl http://<TARGET_IP>/robots.txt

# 🔐 Step 3: Login Portal
# [FIND USERNAME IN PAGE SOURCE]
# [FIND PASSWORD IN robots.txt]

# 💥 Step 4: Command Injection
whoami

# 🏴 Step 5: Find Flags
find / -name "*ingredient*" 2>/dev/null

# 👑 Step 6: Privilege Escalation
sudo -l
sudo bash
```

---

## 🗺️ Attack Path

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   🎯 Target     │────▶│   🔍 Recon      │────▶│   🕵️ Enum       │
│   10.10.10.10   │     │   Ports 22,80   │     │   Credentials   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
         │                                               │
         ▼                                               ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   🏆 Root       │◀────│   👑 PrivEsc    │◀────│   💥 Exploit    │
│   All Flags     │     │   sudo bash     │     │   Command Panel │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

---

## 📁 Repository Structure

```
🗂️ pickle-rick-walkthrough/
│
├── 📄 README.md                          ⭐ Main documentation
├── 📄 LICENSE                            ⚖️ MIT License
├── 📄 .gitignore                         🚫 Git ignore rules
│
├── 📁 01-reconnaissance/                 🔍 Port scanning & service detection
│   └── 📄 README.md
│
├── 📁 02-enumeration/                    🕵️ Web enumeration & credential discovery
│   └── 📄 README.md
│
├── 📁 03-exploitation/                   💥 Web login & command injection
│   └── 📄 README.md
│
├── 📁 04-post-exploitation/              🏴 Finding flags & reverse shell
│   └── 📄 README.md
│
├── 📁 05-privilege-escalation/           👑 Escalating to root
│   └── 📄 README.md
│
├── 📁 06-flags/                          🏆 All 3 ingredients captured
│   └── 📄 README.md
│
├── 📁 scripts/                           🛠️ Useful automation scripts
│   └── 📄 README.md
│
├── 📁 screenshots/                       📸 Screenshot placeholders
│   └── 📄 README.md
│
└── 📁 assets/                            🎨 Visual assets
    └── 📄 .gitkeep
```

---

## 🛠️ Tools Used

<div align="center">

| 🔧 Tool | 🎯 Purpose | 🔗 Link |
|:-------:|:-----------|:-------:|
| **Nmap** | Port scanning & service detection | [nmap.org](https://nmap.org) |
| **Gobuster** | Directory enumeration | [GitHub](https://github.com/OJ/gobuster) |
| **Netcat** | Listener for reverse shell | [netcat.sourceforge.net](http://netcat.sourceforge.net) |
| **cURL** | Web requests & testing | [curl.se](https://curl.se) |
| **Browser DevTools** | Source code inspection | Built-in |
| **Python** | TTY upgrade & filter bypass | [python.org](https://python.org) |

</div>

---

## 📝 Step-by-Step Walkthrough

| Step | 📂 Folder | 🔗 Link |
|:----:|:----------|:-------:|
| 1 | 🔍 Reconnaissance | [01-reconnaissance/](01-reconnaissance/) |
| 2 | 🕵️ Enumeration | [02-enumeration/](02-enumeration/) |
| 3 | 💥 Exploitation | [03-exploitation/](03-exploitation/) |
| 4 | 🏴 Post-Exploitation | [04-post-exploitation/](04-post-exploitation/) |
| 5 | 👑 Privilege Escalation | [05-privilege-escalation/](05-privilege-escalation/) |
| 6 | 🏆 Flags | [06-flags/](06-flags/) |

---

## 🏆 Flags Captured

<div align="center">

| 🏅 Ingredient |📝 Name | 📍 Location | ✅ Status |
|:----------:|:-------|:------------|:---------:|
| 🥇 **1st** | ****** | Web directory / Source code | ✅ Found |
| 🥈 **2nd** | ****** | `/home/rick/second ingredients` | ✅ Found |
| 🥉 **3rd** | ****** | `/root/` | ✅ Found |

</div>

---

## 💡 Key Takeaways

> 🧠 **What I Learned:**
> 
> - 🔍 Always check **page source code** for hidden credentials
> - 📝 **`robots.txt`** can contain sensitive information, not just URLs
> - 🛡️ **Filter bypass** techniques are essential (`less` vs `cat`)
> - 👑 **`sudo -l`** is the first command to run for privilege escalation
> - 🐚 **Reverse shells** give full control over the target

---

## 🛡️ Disclaimer

> ⚠️ **This walkthrough is for educational purposes only.**
> 
> All techniques documented here should only be used on systems you **own** or have **explicit written permission** to test. Unauthorized access to computer systems is illegal under the Computer Fraud and Abuse Act (CFAA) and similar laws worldwide.

---

<div align="center">

## 🙏 Credits

**Room Author:** TryHackMe Team

**Walkthrough By:**

### 👤 Swoyon

</div>

---

<div align="center">

⭐ **If this helped you, give it a star!** ⭐

**Made with 💜 by Swoyon**

</div>
