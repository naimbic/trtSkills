# trtdigitals.com — Build Plan

## Overview
Build the global flagship website for trtDigital (Google Partner Premier agency) — a Next.js 14+ App Router, TypeScript, Tailwind CSS, Framer Motion, PostgreSQL/Prisma, full-stack application with admin dashboard, multi-step forms, SEO/AEO/GEO optimization, and Coolify deployment.

## Skill Loading (Progressive)
- **Stage 1-3**: `vibecoding-webapp-swarm` — Design system + core pages + backend
- **Stage 4**: `docx` — PDF collateral (agency portfolio, Google Ads guide)
- **Stage 5**: `vibecoding-webapp-swarm` continued — Admin dashboard + tracking + deployment

## Execution Stages

### Stage 1: Project Scaffolding & Design System
- Next.js 14+ App Router project setup with TypeScript
- Tailwind CSS with full design token system (colors, spacing, typography, motion)
- Prisma schema + PostgreSQL setup
- Docker + docker-compose for local dev
- Folder structure: app router, components, lib, prisma, public, types
- Design tokens: dark-theme-first, #111827 anchor, full color palette
- Typography: display + body fonts (Latin + Arabic-ready variable)
- Inline SVG icon system (custom, consistent stroke width)
- Animation tokens (Framer Motion + GSAP config)

### Stage 2: Backend Infrastructure
- Prisma schema: Lead, NewsletterSubscriber, AuditRequest, PageView, NotFoundHit, Admin
- NextAuth.js setup for admin dashboard auth
- API routes: form submissions, 404 logging, page view tracking
- Server actions for form handling
- Email/notification webhooks (SMTP + Slack)
- Input validation (zod schemas)
- Rate limiting + spam protection (honeypot)

### Stage 3: Core Pages (Design + Build)
- **Layout**: Header (sticky smart CTA), Footer (full sitemap + offices)
- **Home**: Hero with animated stats counter, proof bar, services preview, case study cards, testimonials, CTA sections
- **Services Hub**: All 7 service pillars with cards
- **Service Pages**: Individual pages for SEO, Paid Search, Social Ads, Web Dev, AEO/GEO, Analytics, Consulting
- **Case Studies Index**: Grid with before/after metrics
- **Case Study Detail Pages**: Kafarat Plus, MAP.ma, Doina.ch, Retro Plus, Pilimpi, GIZ Morocco
- **About**: Timeline, leadership, offices map, values
- **Contact**: Multi-step qualification form (service → budget → timeline → country/contact)
- **Free Audit**: High-intent landing page with audit form
- **Certifications**: Badge wall
- **Industries**: Sector pages
- **Pricing**: Transparent ranges + budget CTA
- **Resources/PDFs**: Downloadable collateral
- **Glossary**: SEO/SEA/AEO/GEO terms for LLM citability
- **Blog**: MDX-based content pipeline
- **Legal**: Privacy, Terms, Cookie Policy

### Stage 4: SEO/AEO/GEO Layer
- Structured data (JSON-LD): Organization, LocalBusiness×4, Service, FAQPage, etc.
- llms.txt at root for AI crawlers
- Sitemap.xml + robots.txt
- Core Web Vitals optimization
- Hreflang scaffold for future locales

### Stage 5: Admin Dashboard
- Auth-gated /admin route
- Leads inbox (filterable/sortable table)
- Traffic overview (first-party analytics)
- 404 report
- Form conversion funnel visualization
- Modular DashboardCard/DataTable components

### Stage 6: Tracking & Deployment
- GTM/GA4 integration (env-driven)
- Google Ads conversion tracking
- Hotjar integration
- Cookie consent banner (GDPR/CCPA)
- Dockerfile (multi-stage production)
- docker-compose.yml
- Coolify deployment docs
- .env.example

### Stage 7: QA & Polish
- Cross-browser/device responsiveness
- Accessibility audit (WCAG 2.1 AA)
- Performance audit (Lighthouse ≥ 95)
- Form/tracking verification

## Key Technical Decisions
- Next.js 14 App Router, TypeScript, React Server Components
- Tailwind CSS + design tokens (no magic values)
- Framer Motion (components) + GSAP (scroll sequences) + Lenis (smooth scroll)
- Prisma + PostgreSQL
- NextAuth.js for admin auth
- MDX for blog/case study content
- next/image with AVIF/WebP
- Inline SVG icons only (no icon fonts)
- Dark-mode-first design
