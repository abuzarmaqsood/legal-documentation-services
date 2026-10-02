# Frontend Design Document (MVP)

# Project

**Legal Documentation Services**

Professional Translation, Typing & Court Documentation

---

# Vision

The website should feel like a premium law firm's website—not a generic freelancer portfolio.

The design should immediately communicate:

- Trust
- Professionalism
- Experience
- Simplicity
- Premium quality

The website's primary objective is to encourage visitors to contact the service provider for quotations through WhatsApp, Email, or a Contact Form.

---

# Design Philosophy

The website should feel like a combination of:

- Premium Law Firm
- Corporate Consulting Firm
- Luxury Professional Services

Avoid:

- Bright playful colors
- Cartoon illustrations
- Rounded bubbly UI
- Startup-style landing pages

Instead focus on:

- Elegant typography
- Clean spacing
- Large imagery
- Premium animations
- Professional color palette
- Strong visual hierarchy

The user should immediately think:

> "This person is experienced, trustworthy, and handles important legal documents professionally."

---

# Visual Theme

Style:

Modern Luxury

Minimal

Professional

Premium

Elegant

Timeless

---

# Color Palette

Primary

```
Deep Navy

#0F172A
```

Secondary

```
Dark Slate

#1E293B
```

Accent

```
Gold

#C8A96A
```

Background

```
#FFFFFF
```

Light Background Sections

```
#F8FAFC
```

Borders

```
#E5E7EB
```

Text

```
Primary

#111827
```

Secondary

```
#6B7280
```

Success

```
#15803D
```

---

# Typography

Heading Font

```
Cormorant Garamond
```

Elegant serif typography suitable for legal and professional branding.

---

Body Font

```
Inter
```

Modern, readable, and clean.

---

Typography Hierarchy

Hero Heading

```
64px
```

Section Heading

```
42px
```

Card Heading

```
24px
```

Body

```
18px
```

Small Text

```
16px
```

---

# Layout

Maximum Width

```
1280px
```

Section Padding

Desktop

```
120px
```

Tablet

```
80px
```

Mobile

```
60px
```

---

# Navigation

Sticky Navbar

Transparent initially.

Changes to solid background on scroll.

Contains:

- Logo
- Services
- Languages
- Workflow
- FAQs
- Contact

Right Side

Primary CTA

```
Get a Quote
```

Navbar Animation

Smooth background transition.

Shadow appears after scrolling.

---

# Hero Section

The most important section.

Large premium layout.

Two-column design.

Left

- Large heading
- Short description
- Experience badge
- CTA buttons

Right

Professional law-themed illustration or image.

Initially:

- Law books
- Court files
- Legal documents
- Gavel
- Fountain pen

Later:

Replace with the service provider's professional photograph.

---

Hero Heading

```
Professional Translation,
Typing &
Court Documentation
```

---

Subtitle

Emphasize:

- 20+ years of experience
- High Court
- Supreme Court
- All Courts
- Individuals
- Law Firms

---

Buttons

Primary

```
Get a Quote
```

Secondary

```
WhatsApp
```

---

Background

Subtle gradient.

Large blurred gold decorative shapes.

---

Animations

Hero fades upward.

Buttons scale on hover.

Background elements move slowly.

---

# Statistics Section

Simple premium cards.

Examples

```
20+

Years of Experience
```

```
3+

Languages
```

```
All

Courts Covered
```

```
100%

Personal Service
```

Cards slightly elevate on hover.

---

# Services Section

Grid layout.

Large premium cards.

Each card contains

- Icon
- Title
- Description

Services

- Legal Translation
- Legal Typing
- Affidavits
- Court Petitions
- Judgments
- Agreements
- Certificates

Hover

Soft shadow

Border glow

Icon animation

---

# Languages Section

Three premium cards.

English

Hindi

Urdu

Later

Easy to add more languages.

Cards have subtle hover animations.

---

# Workflow Section

Horizontal timeline.

```
Submit Request

↓

Upload Documents

↓

Receive Quotation

↓

Translation / Typing

↓

Delivery
```

Each step animated while scrolling.

---

# Why Choose Us

Premium feature cards.

Examples

- 20+ Years Experience
- Individual Attention
- Legal Document Expertise
- All Courts Covered
- Confidential Handling
- Quick Communication

Hover

Lift

Glow

Icon animation

---

# Document Types

Grid

Examples

- Affidavits
- Judgments
- Agreements
- Certificates
- Court Petitions
- Legal Notices
- Contracts
- Miscellaneous Legal Documents

---

# Testimonials

Initially

Static placeholders.

Later

Replace with actual client testimonials.

Cards should resemble luxury review cards.

---

# FAQ

Accordion layout.

Smooth open/close animation.

Examples

- Which languages are supported?
- How do I send documents?
- How long does translation take?
- How do I receive my documents?
- How are quotations calculated?

---

# Contact Section

The primary conversion section.

Contains

Large heading

Short description

Professional contact form.

Fields

- Name
- Email
- Phone
- Source Language
- Target Language
- Message
- Upload Documents

Buttons

Submit Request

WhatsApp

Email

No office address.

No working hours.

---

# Footer

Minimal.

Contains

Website Name

Quick Links

Contact Information

Phone

WhatsApp

Email

Copyright

---

# Buttons

Primary

Deep Navy background.

Gold hover.

Secondary

Outline button.

Premium hover animation.

---

# Cards

Rounded corners

```
20px
```

Soft shadows.

Large padding.

Border animation.

Hover lift.

---

# Forms

Minimal.

Large fields.

Clear validation.

Premium focus state.

Rounded inputs.

Subtle shadows.

---

# Animations

Keep animations elegant.

Avoid flashy effects.

Use:

- Fade Up
- Fade Left
- Fade Right
- Scale
- Staggered Cards
- Slow Floating Background Shapes
- Smooth Hover Elevation
- Smooth Page Transitions

Animation duration

```
300–600ms
```

---

# Responsiveness

Fully responsive.

Desktop First.

Support

Desktop

Laptop

Tablet

Mobile

No horizontal scrolling.

Navigation becomes hamburger menu on mobile.

---

# Accessibility

- High color contrast
- Keyboard accessible
- Visible focus states
- Semantic HTML
- Proper heading hierarchy
- Alt text for images

---

# SEO

The website should be optimized around these keywords:

- Legal Translation Services
- Legal Documentation Services
- Court Document Translation
- Legal Typing Services
- English Hindi Translation
- Hindi English Translation
- Urdu Translation
- Court Documentation
- High Court Translation
- Supreme Court Translation
- Affidavit Translation
- Agreement Translation
- Legal Language Translation
- Professional Legal Translator
- Legal Document Typing

Include:

- Meta Title
- Meta Description
- Open Graph Tags
- Structured Data (JSON-LD)
- Sitemap
- Robots.txt
- Canonical URL

---

# Performance Goals

- Lighthouse Score above 95
- Lazy loading for images
- Optimized assets
- Responsive images
- Code splitting
- Tree shaking
- Fast initial load

---

# Component Structure

```
src/

components/

    common/

        Button

        Section

        Container

        Card

        Badge

    layout/

        Navbar

        Footer

    sections/

        Hero

        Stats

        Services

        Languages

        Workflow

        WhyChooseUs

        DocumentTypes

        Testimonials

        FAQ

        Contact

assets/

styles/

router/

views/

App.vue
```

---

# Future Enhancements (Not in MVP)

When the platform grows, the frontend can be extended with:

- Customer Login
- Order Tracking
- File History
- Dashboard
- Translator Portal
- Online Payments
- Live Chat
- Multi-language Website
- Dark Mode
- AI Translation Assistant
- Client Reviews
- Blog
- Knowledge Base
- Admin Panel

These features are intentionally excluded from the MVP to keep the first version clean, focused, and easy to maintain.

<!-- New additions below -->

## Table of Contents
- Vision
- Design Philosophy
- Visual Theme
- Color Palette
- Typography
- Layout
- Navigation
- Hero Section
- Statistics Section
- Services Section
- Languages Section
- Workflow Section
- Why Choose Us
- Document Types
- Testimonials
- FAQ
- Contact Section
- Footer
- Buttons
- Cards
- Forms
- Animations
- Responsiveness
- Accessibility
- SEO
- Performance Goals
- Component Structure
- Implementation Notes
- Design Tokens
- JSON-LD (Structured Data)
- Next Steps

## Design Tokens (CSS variables)
Add these to a root stylesheet or design system token file for consistency.

```css
:root {
  /* Colors */
  --color-primary: #0F172A;      /* Deep Navy */
  --color-secondary: #1E293B;    /* Dark Slate */
  --color-accent: #C8A96A;       /* Gold */
  --color-bg: #FFFFFF;
  --color-bg-light: #F8FAFC;
  --color-border: #E5E7EB;
  --color-text: #111827;
  --color-text-muted: #6B7280;
  --color-success: #15803D;

  /* Typography */
  --font-heading: "Cormorant Garamond", serif;
  --font-body: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;

  /* Radii & Elevation */
  --radius-card: 20px;
  --shadow-soft: 0 6px 20px rgba(15, 23, 42, 0.08);

  /* Spacing */
  --max-width: 1280px;
  --section-padding-desktop: 120px;
  --section-padding-tablet: 80px;
  --section-padding-mobile: 60px;
}
```

## JSON-LD (Structured Data) — example
Place this in the main HTML <head> or generated head of the app (adjust values).

```json
{
  "@context": "https://schema.org",
  "@type": "ProfessionalService",
  "name": "Legal Documentation Services",
  "url": "https://your-domain.example",
  "logo": "https://your-domain.example/assets/logo.png",
  "description": "Professional Translation, Typing & Court Documentation — High Court and Supreme Court expertise.",
  "telephone": "+91-XXXXXXXXXX",
  "sameAs": [
    "https://www.linkedin.com/in/your-profile"
  ],
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "City",
    "addressRegion": "Region",
    "addressCountry": "Country"
  }
}
```

Meta tags checklist (add to each page):
- meta title (primary keywords)
- meta description (concise, <160 chars)
- og:title, og:description, og:image, og:url
- canonical link
- robots (index, follow) or page-specific

## Implementation Notes
- Use lazy-loading for images and srcset for responsive images.
- Optimize hero and large images (WebP/AVIF).
- Use semantic HTML and aria attributes for accessibility.
- Navbar: transparent -> solid on scroll; add prefer-reduced-motion support for animations.
- Forms: client-side validation + server-side validation; accept file uploads with size/type limits.
- Lighthouse target: aim for critical CSS, code-splitting, and image optimization.
- Provide sitemap.xml and robots.txt at site root.

## Next Steps (MVP priority)
1. Scaffold project structure (components/layout/sections as listed).
2. Implement global tokens and base styles.
3. Build Navbar, Hero, Contact sections (primary conversion flow).
4. Prepare placeholder images and content for Services/Docs.
5. Add meta tags, JSON-LD, sitemap and robots.
6. Run Lighthouse, iterate until >95 score.