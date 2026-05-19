# RevHounds Website — Product Requirements Document
Version 1.0 | May 2026

---

## 1. Overview

### 1.1 Purpose
Replace the existing Wix Premium Light site at revhounds.com with a self-hosted static site deployed on Cloudflare Pages. The new site must improve lead generation, present a more polished brand image, and eliminate recurring Wix subscription costs.

### 1.2 Background
The current site was built in 2018 on Wix. It is functional but visually dated, not optimized for conversion, and limited by the Wix platform in terms of performance and future customization. RevHounds is a two-person boutique consultancy — the site needs to do the selling.

### 1.3 Goals
- **Primary**: Drive qualified inbound leads (contact form submissions, phone calls)
- **Secondary**: Establish credibility with boutique/luxury hotel owners and asset managers
- **Tertiary**: Be easy to maintain without a developer (HTML/CSS editable by any competent IDE)

---

## 2. Scope

### In Scope
- Single-page website (index.html) with four sections: Home, Services, About, Contact
- Hosted on Cloudflare Pages (free tier)
- Contact form via Formspree (free tier, 50 submissions/month, no backend)
- Mobile-responsive layout
- SEO basics (title, meta description, OG tags)
- Accessibility basics (semantic HTML, alt text, keyboard nav)

### Out of Scope (V1)
- Blog / content marketing
- Client portal
- CRM integration
- Analytics beyond basic Cloudflare Web Analytics
- Multi-language support

---

## 3. Users

| Persona | Description |
|---------|-------------|
| **Hotel Owner / GM** | Boutique property, 10–100 rooms. Looking for a trusted partner, not a large agency. Values expertise, responsiveness, and personal attention. |
| **Asset Manager** | Evaluating revenue management performance; wants to see credentials, system experience, methodology. |
| **Referral visitor** | Someone sent the URL by a colleague. Will glance at About + Contact. Needs to feel immediately confident. |

---

## 4. Functional Requirements

### 4.1 Navigation
- Fixed top navigation bar
- Links: Home, Services, About, Contact
- Smooth scroll to each section on click
- Mobile hamburger menu at < 768px
- Logo links to #home

### 4.2 Hero Section (#home)
- Full-viewport height
- Background: dark atmospheric image with overlay
- Headline: "RELENTLESS PURSUIT OF REVENUE"
- Sub-headline: "Boutique revenue management consulting for independent and luxury hotels"
- Primary CTA button: "Get a Free Consultation" → scrolls to #contact
- Secondary CTA: "Our Services" → scrolls to #services

### 4.3 Services Section (#services)
Three service pillar cards:

**Revenue Management**
- Task Force Revenue Management
- Booking Pace Analysis
- Competitive Price Review
- Group Pricing Analysis
- Digital Media Strategy
- Renovation Schedule Optimization
- Sales and Revenue Training

**Distribution Services**
- Rate Loading
- GDS Rate Mapping
- Third Party Management
- Rate Audits
- Website Optimization

**Systems Implementation**
- Revenue System Implementation
- New PMS & CRS Installations
- Development of Analytics Reporting
- Business Intelligence Activation

Below the cards: collapsible/expanded list of all systems experience (PMS, RMS, CRS, BI, Sales, Accounting) — mirrors current site content.

### 4.4 About Section (#about)
- "Who We Are" intro paragraph (existing copy, updated)
- Team cards: Emily Garcia, Artem Lukinov, Pinto (Co-CEO Hound), Bentley (Co-CEO Hound)
- Each card: photo, name, title, 2–3 sentence bio

### 4.5 Contact Section (#contact)
- Heading: "Start the Conversation"
- Sub-copy: encourage first consultation
- Form fields: Name (required), Email (required), Phone (optional), Hotel Name (optional), Message (required)
- Submit via Web3Forms (Access Key to be supplied)
- On success: inline thank-you message (no page reload)
- On error: inline error message
- Also show: contactus@revhounds.com | 925-289-9291

### 4.6 Footer
- Logo
- Copyright: ©2026 RevHounds LLC
- Nav links repeated
- "Site by [blank]" optional

---

## 5. Non-Functional Requirements

| Requirement | Target |
|-------------|--------|
| Performance | Lighthouse score ≥ 90 (Performance, Accessibility) |
| Mobile | Fully usable at 375px viewport width |
| Hosting cost | $0/month (Cloudflare Pages free tier) |
| Form delivery | Formspree free tier (50 submissions/month) |
| Load time | < 2s on 4G (no heavy images without optimization) |
| Browser support | Chrome, Safari, Firefox, Edge — last 2 major versions |

---

## 6. Content Requirements

All content preserved from existing site with the following updates:
- Copyright year updated to 2026
- Remove "©2018 by RevHounds" footer (replace with "©2026 RevHounds LLC")
- Hero updated with more lead-gen-focused CTA language
- Team bios: keep as-is (Artem to update if desired in V2)
- Systems list: retain all existing entries

---

## 7. Technical Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 (semantic) |
| Styles | CSS3 with custom properties (no framework) |
| JS | Vanilla JS (no React, no bundler) |
| Fonts | Google Fonts — Cormorant Garamond + DM Sans |
| Icons | Inline SVG or Unicode where needed |
| Form | Formspree REST API (fetch POST, free tier 50/mo) |
| Hosting | Cloudflare Pages |
| Domain | revhounds.com (transfer DNS to Cloudflare) |
| Analytics | Cloudflare Web Analytics (privacy-friendly, free) |

---

## 8. Deployment Checklist

- [ ] Sign up at formspree.io, create "RevHounds Contact" form → get endpoint URL
- [ ] Replace `YOUR_FORMSPREE_ENDPOINT` in index.html with actual URL
- [ ] Verify Formspree confirmation email sent to contactus@revhounds.com and click the link
- [ ] Optimize and compress hero background image
- [ ] Add team photos to `/assets/` folder
- [ ] Push to GitHub repo
- [ ] Connect GitHub repo to Cloudflare Pages
- [ ] Add custom domain in Cloudflare Pages settings
- [ ] Verify DNS propagation
- [ ] Test contact form end-to-end
- [ ] Run Lighthouse audit
- [ ] Cancel Wix Premium Light subscription

---

## 9. Future Enhancements (V2 backlog)

- Case studies / client testimonials section
- Cloudflare Web Analytics dashboard
- Blog (simple Markdown-based, no CMS)
- LinkedIn / social links
- Updated team headshots
- SEO meta improvements and sitemap.xml

---

*Document owner: Artem Lukinov, RevHounds LLC*
*Last updated: May 2026*
