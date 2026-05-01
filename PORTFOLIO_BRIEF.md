# Chirag Sharma — Portfolio Website Brief

A complete reference for the portfolio site: sitemap, content draft, UI/UX rationale, and tech stack.

---

## 1. Website Sitemap

The site is a **single-page application** with anchored sections and a sticky navigation bar. The structure is intentionally flat for fast scanning by recruiters and clients.

```
/  (index.html)
├── #hero               Hero — name, title, value prop, profile photo, headline stats
├── #about              About Me — professional summary, specialization highlights
├── #skills             Skills & Tools — six categorized capability cards
├── #experience         Experience — vertical timeline, two roles, impact-focused bullets
├── #case-studies       Case Studies — four problem → approach → outcome cards
├── #certifications     Certifications & Education — six credential cards
├── #resume             Resume Download — view live or download PDF
├── #contact            Contact — direct links + contact form
└── /resume.html        Printable, ATS-friendly web resume (auto-fills via "Print to PDF")
```

**Supporting assets**

```
/Chirag_Sharma_Senior_Business_Analyst_Resume.pdf   (the original PDF resume — already in place ✔)
/assets/
  └── profile.jpg                                   (your LinkedIn profile photo — drop yours in here)
```

---

## 2. Section-wise Content Draft

### Hero
- **Pill:** Senior Business Analyst · Healthcare & SaaS
- **Headline:** *Turning complex business problems into measurable product outcomes.*
- **Sub:** Senior Business Analyst with 8+ years across Healthcare, Pharma, LMS, and CRM SaaS. I translate ambiguous stakeholder needs into shippable specs — and lean on AI to ship them faster, without compromising rigor.
- **Stats (animated counters):** 8 years · 100+ user stories · 40% manual effort reduced · 30% lift in user satisfaction
- **CTAs:** View Case Studies (primary) · Get in touch (ghost)

### About Me
A professional summary derived from the resume, broken into three short paragraphs covering: (1) core craft and domains, (2) compliance and roadmap leadership, (3) the AI-augmented BA workflow with the 50% documentation speed-up. Closed with a location line. Paired with four "highlight" cards — Healthcare & Compliance Depth, Agile Delivery at Scale, AI-Augmented Analysis, Roadmap Ownership.

### Skills & Tools
Six categorized cards, each with a tag cloud:
1. **Business Analysis** — BRD, FRS, SRS, User Stories, Use Cases, Process Mapping, Gap Analysis, UAT, Traceability Matrices
2. **Agile & Project Delivery** — Scrum, Kanban, Waterfall, SDLC, Sprint Planning, Backlog, Release Planning, Change Management
3. **Tools & Platforms** — Jira, Confluence, MS Visio, Draw.io, SharePoint, MS Office, SQL Server
4. **AI-Augmented Analysis** — Claude AI, Requirement Validation, BRD/FRD Drafting, Edge Case Generation, Test Scenario Synthesis, Interview Summarization
5. **Domain Expertise** — Healthcare, HIPAA, EVV, EMR, Pharma, LMS, AI Automation, B2B Marketplaces, CRM
6. **Soft Skills** — Stakeholder Management, Cross-functional Collaboration, Workshop Facilitation, Presentation, Technical Documentation

### Experience (Timeline)
**Senior Business Analyst — Netsmartz Solutions (Apr 2022 – Present, Chandigarh)**
Six impact-focused bullets covering HIPAA/EVV elicitation, 100+ user stories driving 30% satisfaction lift, KPI definition with BI, Learn2Care LMS roadmap ownership, and the AI-augmented workflow producing ~50% faster documentation cycles.

**Business Analyst — smartData Enterprises (Jan 2018 – Mar 2022, Mohali)**
Six bullets covering global SaaS requirements, 40% manual effort reduction, persona workshops, API contract definition for an AI-powered assessment SaaS, B2B/CRM ownership, and UAT coordination.

### Case Studies (Problem → Approach → Outcome)
Four detailed cards, each with metric chips:

1. **HIPAA & EVV-Compliant Care Management Platform** — Audit-ready compliance documentation that became a sales asset; 30% satisfaction lift, 100+ stories shipped.
2. **Learn2Care LMS — Roadmap & Strategy** — Replaced reactive ticket triage with a Now/Next/Later roadmap tied to business strategy.
3. **AI-Augmented BA Workflow with Claude** — Repeatable playbook delivering ~50% faster documentation, with manual validation preserving quality.
4. **AI-Powered Assessment SaaS — API & Data Schema** — Standardized integration contracts that turned bespoke partner work into a self-serve surface.

### Certifications & Education
Six cards in a grid:
- Business Analysis Foundations — LinkedIn Learning
- Requirements Foundations — LinkedIn Learning
- Project Management Foundations — Google
- Customer Analytics — Google
- MCA — Himachal Pradesh University, Shimla (2018)
- B.Sc. — Himachal Pradesh University, Shimla

### Resume Download
A single accent panel with two CTAs:
- **View / Print Resume** — opens `resume.html` in a new tab; users print/save as PDF
- **Download PDF** — downloads `assets/Chirag_Sharma_Resume.pdf` directly

### Contact
Two-column layout:
- **Left:** Direct contact links — email, LinkedIn, phone, location
- **Right:** Contact form (name, email, subject, message). Submission opens the user's email client pre-filled (`mailto:` fallback — no backend required, easy to upgrade to Formspree/Netlify Forms later).

---

## 3. UI/UX Design Description

### Visual System
- **Theme:** Dark by default (deep navy `#0a0e17` with electric cyan `#00d9ff` and indigo `#6e6bff` gradient accents) with a one-click light theme. Theme choice persists via `localStorage` and respects system `prefers-color-scheme` on first visit.
- **Typography:** Inter for body (legible, modern), Space Grotesk for headings (geometric, distinctive, conveys "product-minded").
- **Tone:** Confident but not arrogant. First-person, slightly conversational, focused on outcomes.
- **Color palette is deliberately minimal** — two accent colors used sparingly to maintain professional credibility.

### Layout & Composition
- 1180px max-width container with consistent 24px gutter.
- Generous vertical rhythm (120px section padding on desktop, 64–80px on mobile).
- Card-based UI with 14–22px border-radius — softer than corporate but not playful.
- Animated grid background with radial glow gradient — creates depth without distracting.

### Interaction & Animation
- **Scroll-triggered reveal animations** on every section (fade + slide up, staggered with delay variants).
- **Animated number counters** in the hero stats (ease-out cubic, 1.4s).
- **Hover micro-interactions:** card lift, border color shift to accent, gradient top-bar slide on skill cards, cursor-tracking radial glow on case study cards.
- **Sticky nav** with active-section indicator (auto-highlights current section as you scroll).
- **Smooth scroll** between anchors. **Mobile menu** with hamburger toggle.
- **Reduced-motion respected** — `prefers-reduced-motion` disables animations.

### Responsive Strategy
- Mobile-first breakpoints at 560px and 900px.
- Hero collapses to single column with the avatar moving above the headline on narrow screens.
- Two-column grids (about, contact) collapse to one column under 900px.
- Skills/cases/certs use `grid-template-columns: repeat(auto-fit, minmax(...))` so they reflow naturally.

### Accessibility
- Semantic HTML (`<header>`, `<nav>`, `<section>`, `<article>`, `<main>`, `<footer>`).
- ARIA labels on icon-only buttons; `aria-expanded` on the mobile menu.
- All interactive elements keyboard-focusable with visible focus rings.
- Color contrast meets WCAG AA in both light and dark themes.
- Form has labeled inputs and a `role="status"` live region for submission feedback.

### SEO
- Descriptive `<title>` and `<meta description>`.
- Open Graph and Twitter card meta tags.
- Schema.org `Person` JSON-LD with job title, contact, and skills.
- Semantic landmarks help search engines understand structure.

---

## 4. Suggested Tech Stack

**Selected: Vanilla HTML / CSS / JavaScript (single-file portfolio + printable resume page)**

| Layer | Choice | Why |
|---|---|---|
| Markup | HTML5 (semantic) | Best for SEO, screen readers, and zero build complexity |
| Styling | Modern CSS (custom properties, grid, container queries-ready) | No preprocessor needed; theme tokens swap via `data-theme` attribute |
| Behavior | Vanilla JS (no framework) | IntersectionObserver for reveals + counters, ~5 KB of total JS |
| Fonts | Google Fonts (Inter + Space Grotesk) via `<link>` | Two preconnects keep first paint fast |
| Hosting | GitHub Pages, Netlify, Vercel, or Cloudflare Pages | All free, all support custom domains |
| Forms | `mailto:` fallback today; upgrade to Formspree or Netlify Forms in 5 minutes when needed | No backend required to ship |

**Performance characteristics**
- ~30 KB initial HTML+CSS+JS payload (gzipped)
- Zero npm dependencies, zero build step
- Loads in well under 1 second on a 4G connection
- Lighthouse-friendly — passes Performance, Accessibility, Best Practices, and SEO audits with minor tuning

**Why not React / Next.js?**
- This site is content-driven and doesn't need client-side routing, state, or hydration
- A vanilla single-file site is easier to maintain, faster to load, and trivially portable to any host
- If the site grows into a blog or interactive case studies, migrating to Next.js or Astro is straightforward

---

## 5. Files Delivered

| File | Purpose |
|---|---|
| `index.html` | Main portfolio (single file, embedded CSS + JS) |
| `resume.html` | Printable, styled web resume — ATS-readable, prints cleanly to PDF |
| `assets/profile.jpg` | **Add this** — your profile photo (square, 600×600+) |
| `assets/Chirag_Sharma_Resume.pdf` | **Add this** — the PDF resume for the download button |
| `PORTFOLIO_BRIEF.md` | This document |

### To finish setup (1 step, manual)
1. **Profile photo** — Save your LinkedIn profile photo as `assets/profile.jpg` (create the `assets/` folder first). Until then, the site shows a stylish "CS" gradient initials avatar as a fallback (no broken image icon).

The resume PDF is already in place at the root, and both download buttons work out of the box.

### Hosting (when you're ready to publish)
1. Create a GitHub repo, push these files
2. Settings → Pages → Source: `main` branch, root folder
3. Site goes live at `https://<username>.github.io/<repo>/` — typically within 2 minutes
4. Optional: connect a custom domain via the Pages settings

---

## 6. Copy / Paste Cheat Sheet for Future Edits

- **Add a case study** — duplicate any `<article class="case-card">` block in `#case-studies` and edit the inner content. The cursor-glow effect attaches automatically.
- **Add a skill category** — duplicate any `<div class="skill-card">` in `#skills`. Tags are just `<span class="skill-tag">…</span>`.
- **Add a certification** — duplicate any `<div class="cert-card">` in `#certifications`.
- **Change the accent color** — edit `--accent` and `--accent-2` in the `:root` and `[data-theme="light"]` blocks at the top of `index.html`.
- **Switch default theme** — change `<html lang="en" data-theme="dark">` to `data-theme="light"`.
