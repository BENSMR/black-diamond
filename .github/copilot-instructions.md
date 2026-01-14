# Black Diamond Ltd - AI Agent Instructions

## Project Overview
A single-page website for **Black Diamond Ltd**, a global commodities brokerage and market integration company with offices in Dubai, Tunisia, India, and Bulgaria.

**Purpose:** Marketing site with service information and client inquiry form submission.

**Tech Stack:** Static HTML/CSS (no build tools or frameworks)

---

## Architecture & Structure

- **Root:** `index.html` - Single monolithic HTML file containing all markup, styles, and form logic
- **CNAME:** DNS configuration file for GitHub Pages custom domain (blackdiamondltd.com)
- **Hosting:** GitHub Pages (no backend infrastructure)

### Key Sections
1. **Hero Section** - Company branding, office locations, value proposition
2. **Services Grid** - Two service offerings (Brokerage Services, Market Integration)
3. **Inquiry Form** - Contact form using Formspree for email routing
4. **Brand Footer** - Links to sister companies (Aura Sphere CRM, Krystalis Care)

---

## Important Patterns & Conventions

### CSS Structure
- **Design System:** Custom CSS variables for consistent theming
  - `--gold: #c5a059` (brand accent color)
  - `--bg: #050505` (dark background)
  - `--surface: #0f0f0f` (card background)
  - `--text: #ffffff` (primary text)
- **Styling Approach:** Inline `<style>` tag with utility-like classes (no external stylesheets)
- **Brand Style:** Luxury/corporate aesthetic with letter-spacing, Montserrat font, dark theme

### Form Handling
- **Platform:** Formspree (formspree.io) - serverless form submission
- **Form ID:** `mkyayrzo` (production endpoint)
- **Fields:** Name, Email, Primary Interest (dropdown), Requirements (textarea)
- **Note:** Formspree automatically handles email routing to configured inbox

### Links & Routing
- All links use absolute domain URLs: `https://blackdiamondltd.com/...`
- Navigation is minimal (no navbar) - hero leads to form below the fold

---

## GitHub Pages Deployment

### Current Setup
- **Repository:** public (required for Pages)
- **Branch:** `main` (source for GitHub Pages)
- **Custom Domain:** `blackdiamondltd.com`

### DNS Configuration (Required on Domain Registrar)
Add these **A records** pointing to GitHub Pages IP addresses:
```
A 185.199.108.153
A 185.199.109.153
A 185.199.110.153
A 185.199.111.153
```
Or use **CNAME** if registrar allows:
```
CNAME BENSMR.github.io
```

### Deployment Process
1. Push to `main` branch → GitHub Pages auto-publishes `index.html`
2. CNAME file routes traffic from blackdiamondltd.com to the site
3. No build step required; changes live within seconds

---

## Development Workflow

### Making Changes
1. Edit `index.html` directly (all content in one file)
2. Test locally by opening file in browser
3. Commit to `main` branch
4. Push to GitHub - site updates automatically

### Common Updates
- **Services:** Edit `.box` div content in main-content section
- **Colors/Theme:** Update `:root` CSS variables
- **Form Fields:** Modify `<select>` options or textarea placeholder
- **Links:** Update `href` attributes (keep domain consistent as `https://blackdiamondltd.com/...`)

---

## External Dependencies

### Third-Party Services
- **Google Fonts:** Montserrat font (CDN link in `<head>`)
- **Unsplash:** Hero background image (dynamic image URL)
- **Formspree:** Email form backend

### Critical Form ID
- Formspree ID `mkyayrzo` handles all inquiry submissions - **do not change without updating form configuration at formspree.io**

---

## Notes for Future Development

- **No JavaScript:** Site is pure HTML/CSS (consider adding JS only if interactivity needed)
- **Accessibility:** Minimal semantic HTML - consider adding landmarks (`<header>`, `<nav>`, `<section role="main">`) if expanding
- **Sister Sites:** Links to Aura Sphere CRM and Krystalis Care should maintain consistent URL pattern
- **Mobile:** Responsive grid with `minmax(320px, 1fr)` - test on various screen sizes when modifying layout
