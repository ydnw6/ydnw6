<div align="center">

# Hi, I'm Jiongjiong 👋

### Full-Stack Developer · Cloudflare · Windows Tools

I build business systems on Cloudflare's edge, plus small Windows and browser tools that solve everyday problems.

<br/>

[![ydnw6](https://img.shields.io/badge/GitHub-ydnw6-181717?style=for-the-badge&logo=github)](https://github.com/ydnw6)
[![aaoqqqdd](https://img.shields.io/badge/GeekSlope-aaoqqqdd-181717?style=for-the-badge&logo=github)](https://github.com/aaoqqqdd)
![Cloudflare](https://img.shields.io/badge/Cloudflare-Developer-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)

</div>

---

## 👨‍💻 About Me

My work is split across two GitHub accounts:

- **[`ydnw6`](https://github.com/ydnw6)** — my own open-source tools: Windows desktop apps and a browser extension
- **[`aaoqqqdd`](https://github.com/aaoqqqdd)** — GeekSlope, a computer rental business: the rental platform, its website, the device client and the monitoring stack

What I spend most of my time on:

- ☁️ Serverless apps on **Cloudflare Workers, Pages and D1**
- 💳 Payment flows with **Stripe Checkout and Webhooks**, bank transfers and refunds
- 🖥️ Windows desktop tools in **C# / .NET**: global hotkeys, `SendInput`, Core Audio, Windows Services
- 🧩 Browser extensions (Manifest V3) with offline OCR
- 📡 Uptime monitoring and public status pages

---

## 🛠️ Tech Stack

<div align="center">

### Web

![TypeScript](https://img.shields.io/badge/TypeScript-000?style=for-the-badge&logo=typescript)
![JavaScript](https://img.shields.io/badge/JavaScript-000?style=for-the-badge&logo=javascript)
![Vue.js](https://img.shields.io/badge/Vue.js-000?style=for-the-badge&logo=vuedotjs)
![Hono](https://img.shields.io/badge/Hono-000?style=for-the-badge&logo=hono)
![HTML5](https://img.shields.io/badge/HTML5-000?style=for-the-badge&logo=html5)
![CSS3](https://img.shields.io/badge/CSS3-000?style=for-the-badge&logo=css3)

### Cloud & Backend

![Cloudflare](https://img.shields.io/badge/Cloudflare-000?style=for-the-badge&logo=cloudflare)
![SQLite](https://img.shields.io/badge/SQLite_/_D1-000?style=for-the-badge&logo=sqlite)
![Node.js](https://img.shields.io/badge/Node.js-000?style=for-the-badge&logo=nodedotjs)
![Stripe](https://img.shields.io/badge/Stripe-000?style=for-the-badge&logo=stripe)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-000?style=for-the-badge&logo=githubactions)

### Desktop & Extensions

![C#](https://img.shields.io/badge/C%23-000?style=for-the-badge&logo=dotnet)
![.NET](https://img.shields.io/badge/.NET-000?style=for-the-badge&logo=dotnet)
![Windows](https://img.shields.io/badge/Windows-000?style=for-the-badge&logo=windows)
![Chrome Extension](https://img.shields.io/badge/Chrome_Extension-000?style=for-the-badge&logo=googlechrome)

</div>

<div align="center">

`Workers` · `Pages` · `D1` · `Hono SSR` · `REST APIs` · `Webhooks` · `WinForms` · `Windows Service` · `Manifest V3` · `Tesseract.js` · `CI/CD`

</div>

---

## 🏢 GeekSlope — Computer Rental Platform

> Repositories under **[aaoqqqdd](https://github.com/aaoqqqdd)**. Four parts, one shared D1 database.

```text
              Cloudflare D1 (shared database)
                          │
        ┌─────────────────┼──────────────────┐
        │                 │                  │
   rent-web             rent              rent-app
   public website   platform & admin   Windows device client
   (Hono SSR)       (Workers + Hono)   (.NET 8, via /api/device-agent)

   monitorflare ── watches all of the above
```

### 💻 [rent](https://github.com/aaoqqqdd/rent) — Rental management system

The core platform. It runs the full rental lifecycle: application, contract, payment, delivery, return, refund.

- Customer, staff and admin workspaces with role-based access
- Online contract signing, with contract snapshots and integrity hashes
- Stripe Checkout and Webhooks, bank transfer proof review, account balance
- Deposits, cancellation refunds, damage and repair charges, invoices
- Referral program with tiered commission and withdrawals
- **C2C marketplace**: customers list their own laptops, admins review them and set the platform commission

`TypeScript` · `Hono` · `Cloudflare Workers` · `D1` · `Stripe`

### 🌐 [rent-web](https://github.com/aaoqqqdd/rent-web) — Marketing website

A separate Worker that reads live products, prices, stock and legal documents from the platform's D1 database.

- Server-side rendered, no build step, edge-cached
- `/apply` registers the visitor and creates a rental request in one step
- Live delivery quotes and booking via the **Zoom2u** API
- Referral page, gift cards, SEO and an agent-discovery API catalog

`TypeScript` · `Hono SSR` · `Cloudflare Workers` · `D1`

### 🖥️ [rent-app](https://github.com/aaoqqqdd/rent-app) — Windows device client

Installed on every rented laptop. Binds to the platform with a 6-digit code, then talks to it only over HTTPS.

- Heartbeat, hardware inspection snapshots before and after each rental
- Lease countdown overlay and expiry reminders
- Authorized remote commands, auto-update from GitHub Releases
- Runs as a Windows Service, ships with an Inno Setup installer

`C#` · `.NET 8` · `WinForms` · `Windows Service`

### 📡 [MonitorFlare](https://github.com/aaoqqqdd/monitorflare) — Uptime monitoring & status page

An enhanced fork of Uptime-Monitor that runs entirely on the Cloudflare free tier.

- HTTP / HTTPS, DNS, TCP checks, SSL certificate and domain expiry
- 9 notification channels plus 5 email providers
- Public or password-protected status page, incidents, maintenance, RSS, PWA
- Monitor detail pages with latency charts and 90-day uptime bars
- 9 interface languages

`Vue 3` · `Hono` · `Cloudflare Workers` · `D1` · `Pages`

---

## 🧰 Open-Source Tools

> Repositories under **[ydnw6](https://github.com/ydnw6)**. Free, single-file, MIT licensed.

### 🙈 [BossKey Lite · 一键隐身](https://github.com/ydnw6/BossKey-Lite)

A free boss key for Windows. One hotkey hides the windows of the programs you picked and mutes them; press it again and they come back.

- Mutes per-app through Core Audio and sends media pause
- Re-hides windows that pop up while hidden
- Restores hidden windows after a crash
- ~100 KB single exe, no install, no network

`C#` · `WinForms` · `Win32` · [⬇ Download](https://github.com/ydnw6/BossKey-Lite/releases/latest/download/BossKey-Lite.exe)

### ⌨️ [HumanTyper](https://github.com/ydnw6/HumanTyper)

A Windows auto-typer that types like a person: uneven rhythm, typos that get fixed, pauses to think.

- Chinese words typed through pinyin, English paced by WPM
- Scan-code mode for remote desktop, ToDesk, Sunlogin and VMs
- Pauses when you move the cursor and resumes when you put it back
- Reads the text back afterwards and fixes anything missed

`C#` · `.NET Framework` · `SendInput` · [⬇ Download](https://github.com/ydnw6/HumanTyper/releases/latest)

### 🔎 [xhs-hunter · 捡漏雷达](https://github.com/ydnw6/xhs-hunter)

A Chrome / Edge extension that watches Xiaohongshu for second-hand and free items by city and budget. Built for students living overseas.

- Several search tasks in parallel background tabs
- Reads prices like `💰 2199`, `1199🔪`, `A$1,300` and converts currencies
- Finds prices in the post body, the seller's comments or images (offline OCR)
- Skips sold posts, then pushes matches to ntfy, Bark, Telegram or ServerChan

`JavaScript` · `Manifest V3` · `Tesseract.js` · [⬇ Download](https://github.com/ydnw6/xhs-hunter/releases/download/latest/xhs-hunter-latest.zip)

---

## 📁 All Repositories

| Project | What it is | Stack | Account |
| --- | --- | --- | --- |
| [rent](https://github.com/aaoqqqdd/rent) | Rental management platform | TypeScript · Hono · D1 | aaoqqqdd |
| [rent-web](https://github.com/aaoqqqdd/rent-web) | GeekSlope marketing site | Hono SSR · D1 | aaoqqqdd |
| [rent-app](https://github.com/aaoqqqdd/rent-app) | Windows device client | C# · .NET 8 | aaoqqqdd |
| [BossKey-Lite](https://github.com/ydnw6/BossKey-Lite) | Windows boss key | C# · WinForms | ydnw6 |
| [HumanTyper](https://github.com/ydnw6/HumanTyper) | Human-like auto typer | C# · WinForms | ydnw6 |
| [xhs-hunter](https://github.com/ydnw6/xhs-hunter) | Second-hand deal finder extension | JavaScript · MV3 | ydnw6 |

---

## 📈 Activity

<div align="center">

<img
  src="https://github-readme-activity-graph.vercel.app/graph?username=ydnw6&theme=github-compact&hide_border=true&area=true"
  width="95%"
  alt="Contribution activity graph"
/>

</div>

---

## 🔨 Currently Building

- **GeekSlope** → C2C device marketplace · delivery integration · device client
- **Desktop tools** → BossKey · HumanTyper
- **xhs-hunter** → better price recognition and fewer requests

---

<div align="center">

### Build systems that solve real problems.

<br/>

![Profile Views](https://komarev.com/ghpvc/?username=ydnw6&style=flat-square&label=Profile+Views)

</div>
