<div align="center">

<img src="https://raw.githubusercontent.com/akarshxs/gitexplor/main/public/icon.png" width="120" alt="GitExplorer" />

<h1>GitExplorer</h1>

<p><strong>The most powerful way to explore GitHub repositories.</strong><br/>
Discover, filter, star, fork, and track repositories across 84 curated technology streams — beautifully.</p>

<br/>

[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Android-238636?style=for-the-badge&logo=github&logoColor=white)](https://akarshxo.org)
[![Status](https://img.shields.io/badge/Status-Live-2f81f7?style=for-the-badge&logo=vercel&logoColor=white)](https://akarshxo.org)
[![License](https://img.shields.io/badge/License-Closed%20Source-f85149?style=for-the-badge&logo=lock&logoColor=white)](#-license)
[![Version](https://img.shields.io/badge/Version-1.0.0-a371f7?style=for-the-badge&logo=semanticrelease&logoColor=white)](#)
[![Free to Use](https://img.shields.io/badge/Free%20to%20Use-Yes-3fb950?style=for-the-badge&logo=heart&logoColor=white)](https://akarshxo.org)
[![Android](https://img.shields.io/badge/Android-APK%20Available-d29922?style=for-the-badge&logo=android&logoColor=white)](#-android-apk)

<br/>

**[🌐 Launch Web App](https://akarshxo.org)** · **[📱 Download APK](#-android-apk)** · **[🐛 Report Issue](https://github.com/akarshxs/gitexplorer/issues)** · **[💡 Request Feature](https://github.com/akarshxs/gitexplorer/issues)**

<br/>

</div>

---

> **⚠️ Important:** GitExplorer is **free to use** for everyone. However, this is a **closed-source** project. The web application and Android APK source code are **private and proprietary**. Usage is open. Code is not.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Why GitExplorer](#-why-gitexplorer)
- [Screenshots](#-screenshots)
- [Architecture](#-architecture-overview)
- [Access Model](#-access-model)
- [Web Access](#-web-access)
- [Android APK](#-android-apk)
- [Technology Streams](#-technology-streams)
- [Why Not Open Source](#-why-gitexplorer-is-not-open-source)
- [Security Philosophy](#-security-philosophy)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [FAQ](#-faq)
- [License](#-license)
- [Author](#-author--maintainer)
- [Support](#-support--contact)

---

## 🔭 Overview

**GitExplorer** is a next-generation GitHub repository discovery platform designed for developers who want to go beyond GitHub's default explore page.

Instead of endless scrolling and irrelevant results, GitExplorer gives you a **structured, real-time, and beautifully designed interface** to discover the most valuable open-source projects — organized by technology domain, filtered by quality signals, and enriched with GitHub data.

Whether you're a developer exploring the latest AI tools, a security researcher tracking offensive security projects, or an engineer looking for the best DevOps frameworks — GitExplorer surfaces exactly what you need, instantly.

```
🌐 Web App    →  https://akarshxo.org
📱 Android    →  Free APK download (see below)
🔒 Source     →  Private / Closed Source
💸 Cost       →  Completely Free to Use
```

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🔍 Discovery
- **84 curated technology streams** covering every major domain
- **Real-time GitHub data** via API v3 with multi-token rotation
- **Trending analysis** — daily, weekly, monthly
- **Smart search** — global index + instant client-side filter
- **Advanced filters** — language, stars, forks, license, activity

</td>
<td width="50%">

### ⭐ Interaction
- **Star repositories** directly from the platform
- **Fork repositories** with one click
- **Copy clone URLs** to clipboard instantly
- **Bookmark repos** locally for later reference
- **GitHub OAuth** — secure login, stays logged in

</td>
</tr>
<tr>
<td width="50%">

### 🎨 Design
- **GitHub-style dark UI** — familiar and clean
- **Mobile-first** — pixel-perfect on every device
- **Smooth animations** — Framer Motion powered
- **Adaptive layouts** — grid and list views
- **Progressive loading** — skeleton screens, no jarring flashes

</td>
<td width="50%">

### 📱 Android App
- **Native WebView wrapper** — identical to web experience
- **GitHub OAuth** fully supported inside app
- **Offline screen** — detects and handles no connectivity
- **File downloads** via Android DownloadManager
- **Back navigation** — full history support
- **Swipe to refresh** — pull-to-reload support

</td>
</tr>
</table>

---

## 🚀 Why GitExplorer

| Problem with GitHub Explore | GitExplorer Solution |
|---|---|
| No domain-specific filtering | 84 precise technology streams |
| Trending is one generic list | Trending per stream, per timeframe |
| Can't star/fork without leaving | Full OAuth actions inline |
| Poor mobile experience | Dedicated mobile-optimized interface |
| No quality signal filtering | Filter by stars, forks, activity, license |
| Results feel random | Curated topic mapping per stream |
| No way to bookmark for later | Local bookmarking system |
| Hard to compare repos | Side-by-side detail cards |

> GitExplorer is not a GitHub replacement. It is a **GitHub supercharger** — everything you love about GitHub's data, with a dramatically better discovery experience on top.

---

## 📸 Screenshots

<div align="center">

| Web — Stream View | Web — Repository Card | Android App |
|:---:|:---:|:---:|
| ![Stream View](https://via.placeholder.com/280x180/0d1117/58a6ff?text=Stream+View) | ![Repo Card](https://via.placeholder.com/280x180/0d1117/3fb950?text=Repo+Card) | ![Android](https://via.placeholder.com/280x180/0d1117/a371f7?text=Android+App) |

> 📌 *Replace placeholder images above with actual screenshots of your app*

</div>

---

## 🏗 Architecture Overview

GitExplorer is built on a modern, production-grade stack. While the source code is private, here is a high-level overview of how the platform works:

```
┌─────────────────────────────────────────────────────┐
│                     CLIENT LAYER                     │
│                                                      │
│   Web Browser (Next.js 14)   Android App (WebView)   │
│          ↓                          ↓                │
│              Unified Web Interface                   │
└──────────────────────┬──────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────┐
│                     API LAYER                        │
│                                                      │
│   /api/repos          → Stream-scoped discovery      │
│   /api/global-search  → Full GitHub index search     │
│   /api/trending       → Trending score engine        │
│   /api/auth/*         → GitHub OAuth 2.0 flow        │
│   /api/repo/fork      → Fork via authenticated user  │
│   /api/repo/star      → Star/unstar repositories     │
└──────────────────────┬──────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────┐
│                   DATA LAYER                         │
│                                                      │
│   GitHub REST API v3  (multi-token rotation)         │
│   In-memory cache     (5-min TTL per query)          │
│   httpOnly Cookies    (OAuth token storage)          │
│   Vercel Serverless   (zero cold start infra)        │
└─────────────────────────────────────────────────────┘
```

**Key design principles:**
- 🔄 **Multi-token rotation** — distributes GitHub API rate limits across multiple tokens
- 🔒 **Zero client-side token exposure** — OAuth tokens live only in httpOnly cookies
- ⚡ **Dual search architecture** — server search for discovery, client filter for speed
- 📱 **Single codebase** — web and Android share 100% of the same UI via WebView

---

## 🔐 Access Model

<div align="center">

| What | Access |
|:---|:---:|
| 🌐 Web Application | ✅ Free, No signup required |
| 📱 Android APK | ✅ Free download |
| ⭐ Star / Fork repos | ✅ Free with GitHub login |
| 🔖 Bookmarks | ✅ Free, stored locally |
| 💻 Web Source Code | ❌ Private |
| 📦 Android Source Code | ❌ Private |
| 🔑 API Keys / Tokens | ❌ Private |
| 🏗 Infrastructure Config | ❌ Private |

</div>

> GitExplorer follows a **"Free to use, closed source"** model — similar to tools like Notion, Linear, and Vercel. The product is fully accessible to everyone at no cost. The code that powers it is not.

---

## 🌐 Web Access

No installation required. Open your browser and go:

```
https://akarshxo.org
```

- ✅ Works on all modern browsers (Chrome, Firefox, Safari, Edge)
- ✅ Fully responsive — works on mobile browsers too
- ✅ No account required to browse
- ✅ GitHub login optional — only needed for star/fork actions
- ✅ Always up to date — no version management needed

---

## 📱 Android APK

GitExplorer is available as a native Android application. The app renders the exact same interface as the web version, fully synchronized with every update automatically.

**Requirements:**
- Android 7.0 (Nougat) or higher
- Internet connection

**Installation steps:**

```
1. Download the APK from the Releases section of this repository
2. On your Android device: Settings → Security → Enable "Install unknown apps"
3. Open the downloaded APK file
4. Tap Install
5. Launch GitExplorer
```

> 📌 The Android APK is provided as a signed release build. It is safe to install and has been built with the same security standards as the web platform.

**App highlights:**
- 🔒 GitHub OAuth works fully inside the app
- 📶 Offline detection with retry screen
- 🔄 Swipe to refresh
- ⬇️ File download support via Android DownloadManager
- 🔙 Hardware back button navigates history

---

## 🧩 Technology Streams

GitExplorer organizes the entire GitHub ecosystem into **84 precision-mapped technology streams**. Each stream maps to hundreds of GitHub topics for maximum coverage.

<details>
<summary><strong>View all 84 streams</strong></summary>

<br/>

| # | Stream | Focus Area |
|---|--------|-----------|
| 1 | 🧠 AI / ML / LLM | Machine learning, deep learning, LLMs, AI tools |
| 2 | 🛡️ Cybersecurity / Hacking | Pentesting, ethical hacking, security tools |
| 3 | ⛓️ Blockchain / Crypto | DeFi, NFTs, smart contracts, trading bots |
| 4 | 🎮 Game / XR / Metaverse | Game dev, VR/AR, 3D graphics |
| 5 | 🌐 Web / Dev / Cloud | Frontend, backend, full-stack, DevOps |
| 6 | 🤖 Bots / Automation | Telegram, Discord, RPA, workflow automation |
| 7 | 📱 Mobile / App Dev | Android, iOS, React Native, Flutter |
| 8 | 📊 Data / Analytics / BI | Data science, analytics, visualization |
| 9 | 🔌 Embedded / IoT / Hardware | Microcontrollers, firmware, hardware hacking |
| 10 | 🖥️ Operating Systems | Low-level, kernel, OS development |
| 11 | 🛠️ Dev Tools / Productivity | IDEs, CLI tools, developer utilities |
| 12 | 🎨 Design / UI / Creative Tech | UI frameworks, design systems, creative coding |
| 13 | 🎓 Education / Learning | Courses, tutorials, learning platforms |
| 14 | ⚛️ Quantum / Advanced Computing | Quantum algorithms, HPC |
| 15 | 🌐 Networking / Infrastructure | Protocols, networking tools |
| 16 | 🧬 AI Research / AGI | Frontier AI research, AGI projects |
| 17 | 🏗️ System Architecture | Scalability, distributed systems |
| 18 | 💀 Advanced Exploitation | Offensive security research |
| 19 | 🔐 Cryptography | Applied crypto, cryptanalysis |
| 20 | 🔒 AI Security | Adversarial ML, model security |
| 21 | ☁️ Cloud Native | Platform engineering, Kubernetes |
| 22 | 🔬 Digital Forensics | DFIR, memory forensics |
| 23 | 🚀 SaaS / Product Engineering | SaaS patterns, product infrastructure |
| 24 | 🤖 Agentic AI | Autonomous agents, multi-agent systems |
| 25 | 🦾 Robotics / Embodied AI | Physical AI, robotics frameworks |
| 26 | 🖼️ Frontend / Modern UI | React, Vue, Svelte, modern UI patterns |
| 27 | 🌱 Sustainable Tech | Green computing, carbon-aware engineering |
| 28 | 🔧 DevOps / SRE | CI/CD, observability, site reliability |
| 29 | 👓 AR / VR / Spatial | Spatial computing, mixed reality |
| 30 | ⚡ Edge / Fog Computing | Edge inference, on-device models |
| ... | *54 more specialized streams* | *Covering every corner of modern tech* |

</details>

---

## 🔒 Why GitExplorer Is Not Open Source

This is a deliberate and considered decision, not an oversight. Here is why:

<table>
<tr>
<td width="50%">

### 🛡️ Security
The platform integrates with GitHub's OAuth system and manages API tokens. Exposing the implementation details would create attack surface for token theft, rate-limit abuse, and OAuth flow manipulation.

</td>
<td width="50%">

### ⚙️ Infrastructure Protection
GitExplorer uses a custom multi-token rotation engine, caching layer, and query optimization system built over months of iteration. Making this public would allow trivial copying without the investment.

</td>
</tr>
<tr>
<td width="50%">

### 🏗️ Stability Guarantee
Closed source means controlled deployments. Every change is tested and verified before reaching users. There are no forks running untested versions that could confuse or mislead users.

</td>
<td width="50%">

### 🚀 Product Integrity
GitExplorer is a curated product experience. Open sourcing it would fragment the ecosystem, leading to unmaintained forks, broken clones, and a degraded perception of what GitExplorer actually is.

</td>
</tr>
</table>

> This model is used by many respected developer tools — **Figma, Notion, Linear, Vercel, Raycast** — who provide exceptional free products while keeping their source private. GitExplorer follows the same philosophy: **build something great, make it free, keep it maintained.**

---

## 🔐 Security Philosophy

GitExplorer was designed with security at its core:

- **🍪 httpOnly Cookies** — GitHub OAuth tokens are stored exclusively in httpOnly, Secure, SameSite cookies. JavaScript cannot access them under any circumstance.
- **🚫 No localStorage for secrets** — Sensitive data never touches client-side storage.
- **🔀 Server-side proxying** — All GitHub API calls are proxied through server-side routes. API keys never reach the client.
- **🛡️ Safe Browsing** — Android app has Google Safe Browsing enabled via WebViewFeature.
- **🔒 HTTPS only** — Network security config blocks all cleartext HTTP traffic.
- **🐛 No debug in production** — WebView remote debugging is disabled in release builds.
- **📋 Minimal permissions** — The Android app requests only the permissions it actually needs.

---

## 🗺️ Roadmap

<table>
<tr>
<td width="33%">

### ✅ v1.0 — Shipped
- 84 technology streams
- GitHub OAuth
- Star / Fork / Clone
- Trending engine
- Android APK
- Mobile-optimized UI
- Bookmark system

</td>
<td width="33%">

### 🔄 v1.1 — In Progress
- [ ] Repository comparison view
- [ ] Personal dashboard
- [ ] Saved stream preferences
- [ ] Email digest of trending repos
- [ ] PWA / installable web app
- [ ] Improved offline support

</td>
<td width="33%">

### 🔮 v2.0 — Planned
- [ ] AI-powered recommendations
- [ ] Custom stream builder
- [ ] Team workspaces
- [ ] GitHub notifications integration
- [ ] iOS app
- [ ] Browser extension
- [ ] API for developers

</td>
</tr>
</table>

> Have a feature idea? [Open an issue](https://github.com/akarshxs/gitexplorer/issues) — roadmap priorities are influenced by community feedback.

---

## 🤝 Contributing

GitExplorer is closed source, so **code contributions are not accepted**. However, your input genuinely shapes the product:

<table>
<tr>
<td width="33%" align="center">

### 🐛 Bug Reports
Found something broken?<br/>
[Open a bug report →](https://github.com/akarshxs/gitexplorer/issues/new)

</td>
<td width="33%" align="center">

### 💡 Feature Requests
Have an idea?<br/>
[Request a feature →](https://github.com/akarshxs/gitexplorer/issues/new)

</td>
<td width="33%" align="center">

### ⭐ Show Support
Find it useful?<br/>
[Star this repo →](https://github.com/akarshxs/gitexplorer)

</td>
</tr>
</table>

**When reporting issues, please include:**
- Browser / Android version
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if possible

---

## ❓ FAQ

<details>
<summary><strong>Is GitExplorer really free?</strong></summary>
<br/>
Yes. GitExplorer is 100% free to use — no subscription, no freemium paywall, no hidden costs. Both the web app and Android APK are free.
</details>

<details>
<summary><strong>Do I need a GitHub account?</strong></summary>
<br/>
No. You can browse all 84 streams, search repositories, and explore without any account. A GitHub account is only required if you want to star or fork repositories directly from GitExplorer.
</details>

<details>
<summary><strong>Is my GitHub token safe?</strong></summary>
<br/>
Yes. GitExplorer stores your GitHub OAuth token in an httpOnly cookie — meaning JavaScript (including any browser extensions or injected scripts) cannot access it. All API calls are made server-side. Your token is never sent to the client.
</details>

<details>
<summary><strong>Why is the source code private?</strong></summary>
<br/>
See the full explanation in the <a href="#-why-gitexplorer-is-not-open-source">Why Not Open Source</a> section above. Short answer: security, infrastructure protection, and product integrity.
</details>

<details>
<summary><strong>Can I self-host GitExplorer?</strong></summary>
<br/>
No. Since the source code is private, self-hosting is not supported. The official instance at akarshxo.org is the only deployment.
</details>

<details>
<summary><strong>How is GitExplorer different from GitHub's own Explore page?</strong></summary>
<br/>
GitHub's Explore page shows a single generic trending list. GitExplorer provides 84 domain-specific streams, each mapped to hundreds of precise topics, with advanced filters, OAuth-powered actions, full mobile support, and a significantly cleaner UI.
</details>

<details>
<summary><strong>Is the Android app on the Play Store?</strong></summary>
<br/>
Not yet. The APK is available as a direct download. Play Store publishing is on the roadmap.
</details>

<details>
<summary><strong>How often is the data updated?</strong></summary>
<br/>
Repository data is fetched live from GitHub's API with a 5-minute cache per query. Trending data is recalculated on each request based on recent star velocity.
</details>

---

## 📄 License

```
GitExplorer — Proprietary License

Copyright (c) 2026 Akarsh. All rights reserved.

This software and its source code are proprietary and confidential.
The compiled application (web and Android) is made freely available
for personal and professional use at no cost.

You MAY:
  ✅ Use the GitExplorer web application at akarshxo.org
  ✅ Install and use the GitExplorer Android APK
  ✅ Share the link to GitExplorer with others

You MAY NOT:
  ❌ Access, copy, modify, or distribute the source code
  ❌ Reverse engineer the application
  ❌ Claim ownership or authorship of any part of GitExplorer
  ❌ Use GitExplorer's design, branding, or architecture
     to build competing products

The GitExplorer name, logo, and brand identity are trademarks
of Akarsh and may not be used without explicit written permission.
```

---

## 👨‍💻 Author & Maintainer

<div align="center">

<img src="https://github.com/akarshxs.png" width="80" style="border-radius: 50%" alt="Akarsh" />

### Akarsh

*Builder · Developer · Designer*

[![GitHub](https://img.shields.io/badge/GitHub-akarshxs-181717?style=flat-square&logo=github)](https://github.com/akarshxs)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-akarshx-0a66c2?style=flat-square&logo=linkedin)](https://linkedin.com/in/akarshx)
[![Instagram](https://img.shields.io/badge/Instagram-akarshxs-e1306c?style=flat-square&logo=instagram)](https://instagram.com/akarshxs)

> *"I built GitExplorer because I was frustrated with how hard it was to discover great open source projects. I wanted something that felt as good as the best developer tools — fast, beautiful, and actually useful."*

</div>

---

## 💬 Support & Contact

| Channel | Purpose | Link |
|---------|---------|------|
| 🐛 GitHub Issues | Bug reports, feature requests | [Open Issue](https://github.com/akarshxs/gitexplorer/issues) |
| 📸 Instagram | Updates, previews, announcements | [@akarshxs](https://instagram.com/akarshxs) |
| 💼 LinkedIn | Professional inquiries | [akarshx](https://linkedin.com/in/akarshx) |
| 🐙 GitHub | Follow for updates | [@akarshxs](https://github.com/akarshxs) |

---

## ❤️ Support the Project

GitExplorer is free to use and costs real money to run. If it has been useful to you, consider supporting it:

| Method | Address |
|--------|---------|
| **BTC** | `bc1qxj94mthr9j3dhvg4829a5zf5cnc53zxw6vjtaw` |
| **LTC** | `ltc1qa9qxcd8wvxwf3hqu8tuf4up8fncv9gzgjeyye5` |
| **UPI** | `takarsh88@okaxis` |

Every contribution — no matter how small — goes directly into keeping the platform running and building new features.

---

<div align="center">

<br/>

**[🌐 Launch GitExplorer](https://akarshxo.org)** · **[📱 Download APK](#-android-apk)** · **[⭐ Star this repo](https://github.com/akarshxs/gitexplor)**

<br/>

*Built with ❤️ by [Akarsh](https://github.com/akarshxs) · Free to use · Closed source · Always improving*

<br/>

![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=akarshxs.gitexplorer)

</div>
