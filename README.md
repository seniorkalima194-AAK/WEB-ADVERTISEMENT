<div align="center">
![Header](https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:8e44ad,100:d4af37&height=220&section=header&text=Luxe%20Decor&fontSize=56&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Premium%20Decoration%20%26%20Event%20Styling%20%E2%80%94%20Digital%20Experience&descAlignY=58&descSize=18)
 
[![Made with React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white&style=for-the-badge)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-Build-646CFF?logo=vite&logoColor=white&style=for-the-badge)](https://vitejs.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind-CSS-06B6D4?logo=tailwindcss&logoColor=white&style=for-the-badge)](https://tailwindcss.com)
[![Framer Motion](https://img.shields.io/badge/Framer-Motion-0055FF?logo=framer&logoColor=white&style=for-the-badge)](https://www.framer.com/motion)
[![GSAP](https://img.shields.io/badge/GSAP-ScrollTrigger-88CE02?logo=greensock&logoColor=white&style=for-the-badge)](https://gsap.com)
[![Figma](https://img.shields.io/badge/Design-Figma-F24E1E?logo=figma&logoColor=white&style=for-the-badge)](https://figma.com)
 
**Status:** 🎨 Design Phase &nbsp;|&nbsp; **Priority:** Frontend Experience &nbsp;|&nbsp; **Backend:** Deferred (Phase 2)
 
</div>
---
 
## 📖 Table of Contents
 
- [Vision](#-vision)
- [Business Scope](#-business-scope)
- [Site Structure](#-site-structure)
- [User Journey](#-user-journey)
- [Design Philosophy](#-design-philosophy)
- [Tech Stack](#-tech-stack)
- [Animation Ownership](#-animation-ownership-read-this-before-writing-code)
- [Architecture (Future Backend)](#-architecture-future-backend)
- [Development Roadmap](#-development-roadmap)
- [Performance Budget](#-performance-budget-non-negotiable)
- [Getting Started](#-getting-started)
---
 
## 🎯 Vision
 
> *"If the decorator can create a website experience this beautiful, imagine what they can create in real life."*
 
A visually immersive frontend for a decoration & event styling business — built to communicate **creativity, elegance, professionalism, and trust** before a single word is read.
 
**Not a static business site.** A portfolio-first, motion-driven brand experience.
 
---
 
## 🏢 Business Scope
 
| | Products | Services |
|---|---|---|
| 🎀 | Wedding decoration materials | Wedding decoration |
| 🪟 | Curtains | Event decoration |
| 🏺 | Vases | Interior decoration |
| 💡 | Lighting | Space styling |
| 🪑 | Furniture | Special occasion decoration |
| 🎪 | Event equipment | — |
| 🖼️ | Wall decorations | — |
 
**Product catalogue, cart, and payments are explicitly Phase 2** — do not let scope creep pull e-commerce into the frontend-first phase.
 
---
 
## 🗺️ Site Structure
 
```
Home → Services → About Us → Portfolio → Why Choose Us → Testimonials → Contact
```
 
## 🔄 User Journey
 
```mermaid
flowchart TD
    A["🏠 Home<br/>Cinematic first impression"] --> B["🛠️ Services<br/>Interactive service cards"]
    B --> C["📖 About Us<br/>Scroll storytelling"]
    C --> D["🖼️ Portfolio<br/>Masonry gallery + filtering"]
    D --> E["⭐ Why Choose Us<br/>Animated stats"]
    E --> F["💬 Testimonials<br/>Carousel + social proof"]
    F --> G["📩 Contact<br/>CTA + WhatsApp / Email"]
 
    style A fill:#8e44ad,color:#fff
    style B fill:#7d3c98,color:#fff
    style C fill:#6c3483,color:#fff
    style D fill:#5b2c6f,color:#fff
    style E fill:#4a235a,color:#fff
    style F fill:#d4af37,color:#000
    style G fill:#1a1a2e,color:#fff
```
 
---
 
## 🎨 Design Philosophy
 
| Principle | Meaning |
|---|---|
| **Visual First** | High-quality imagery, typography, and composition carry the brand — not copy. |
| **Animation With Purpose** | Every animation guides attention, reveals content, or adds depth. Never decorative-only. |
| **Premium Simplicity** | `Minimalism + Creativity + Animation + Elegance` — restraint is part of luxury, not the opposite of it. |
| **Strong Storytelling** | The scroll is a narrative arc, not a list of sections. |
 
---
 
## 🧰 Tech Stack
 
| Layer | Technology | Purpose |
|---|---|---|
| 🧱 Core | React + Vite | App shell, fast dev/build |
| 🎨 Styling | Tailwind CSS + CSS | Utility-first + custom fine control |
| 🎬 Micro-interactions | Framer Motion | Hover, layout transitions, component-level motion |
| 🎥 Scroll & Timeline | GSAP + ScrollTrigger | Pinned sections, parallax, cinematic sequences |
| 🖱️ Smooth Scroll | Lenis | Inertia scrolling — **must be synced to GSAP** (see below) |
| 🖼️ Sliders | Swiper | Testimonials, galleries, mobile carousels |
| 🧿 Icons | Lucide React | Consistent interface iconography |
| 🧊 3D (Phase 1.5, conditional) | React Three Fiber / Spline | Only if a specific hero/product moment justifies the payload cost |
| 🗂️ Design | Figma | Wireframes → high-fidelity → prototype |
| ⚙️ Future Backend | Python, FastAPI, PostgreSQL | Deferred — see architecture below |
 
## ⚠️ Animation Ownership (read this before writing code)
 
Stacking Framer Motion, GSAP, and Lenis without boundaries produces jank and fights over the same elements. Fixed division of labor:
 
- **Framer Motion** → component-level micro-interactions (buttons, hover states, small layout shifts)
- **GSAP + ScrollTrigger** → all scroll-driven animation (reveals, pinning, parallax, cinematic sequences)
- **Lenis** → scroll physics only, explicitly wired to ScrollTrigger's update loop — never left to run independently alongside ScrollTrigger
No element is animated by more than one library at a time.
 
---
 
## 🏗️ Architecture (Future Backend)
 
```mermaid
flowchart LR
    A["⚛️ React Frontend"] -->|REST API| B["⚡ FastAPI Backend"]
    B -->|SQL| C["🐘 PostgreSQL"]
 
    style A fill:#61DAFB,color:#000
    style B fill:#009688,color:#fff
    style C fill:#336791,color:#fff
```
 
Introduced **after** the frontend experience, brand identity, and content structure are locked — not before.
 
---
 
## 🚀 Development Roadmap
 
```mermaid
flowchart TD
    S1["1️⃣ Understand the Brand"] --> S2["2️⃣ Research Inspiration"]
    S2 --> S3["3️⃣ Design System"]
    S3 --> S4["4️⃣ Wireframes"]
    S4 --> S5["5️⃣ High-Fidelity UI"]
    S5 --> S6["6️⃣ Prototype"]
    S6 --> S7["7️⃣ Frontend Structure"]
    S7 --> S8["8️⃣ Implement UI"]
    S8 --> S9["9️⃣ Basic Interactions"]
    S9 --> S10["🔟 Animations"]
    S10 --> S11["1️⃣1️⃣ Premium Effects"]
    S11 --> S12["1️⃣2️⃣ Responsive QA"]
    S12 --> S13["1️⃣3️⃣ Performance Pass"]
    S13 --> S14["1️⃣4️⃣ Backend Dev"]
 
    style S1 fill:#1a1a2e,color:#fff
    style S14 fill:#d4af37,color:#000
```
 
---
 
## ⚡ Performance Budget (non-negotiable)
 
A slow "premium" site reads as amateur, not luxury. Fixed targets, checked at every phase — not left to Layer 6:
 
| Metric | Target |
|---|---|
| Largest Contentful Paint (LCP) | < 2.5s on 4G |
| Total JS (pre-code-split) | < 300kb |
| Hero media | Compressed/responsive `<picture>` or adaptive video, never a raw 4K asset |
| Animation | 60fps or degrade gracefully — no motion at the cost of scroll jank |
 
---
 
## 🏁 Getting Started
 
```bash
git clone <repo-url>
cd luxe-decor-frontend
npm install
npm run dev
```
 
### Prerequisites
 
- Node.js ≥ 18
- npm
- Figma access (for design handoff)
---
 
<div align="center">
![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:8e44ad,100:d4af37&height=100&section=footer)
