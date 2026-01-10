# RAGEDESIGNER.COM - TEMPLATE REFERENCE
## Source of Truth for All Page Components
**Last Updated:** January 10, 2026
**Source File:** index.html (SHA: 3487b90c4703e12510c6d098c424396332180255)

---

## ⚠️ CRITICAL: READ BEFORE EDITING ANY PAGE

When editing ANY page on ragedesigner.com:
1. **DO NOT reconstruct header/footer from memory**
2. **COPY the exact HTML from this reference**
3. **Only modify page-specific content (title, meta, body)**

This prevents the "fix one thing, break another" pattern.

---

## 🎨 CSS VARIABLES (Required in every page)

```css
:root {
    --charcoal-blue: #1A2332;
    --logo-blue: #325d74;
    --copper: #B7704F;
    --white: #ffffff;
    --light-gray: #f5f5f5;
    --logo-blue-light: rgba(50,93,116,0.1);
    --charcoal-medium: rgba(26,35,50,0.85);
    --charcoal-light: rgba(26,35,50,0.6);
    --text-xs: 0.688rem;
    --text-sm: 0.875rem;
    --text-base: 1rem;
    --text-md: 1.125rem;
    --text-lg: 1.25rem;
    --text-xl: 1.563rem;
    --text-2xl: 1.953rem;
    --text-3xl: 2.441rem;
    --text-4xl: 3.052rem;
    --text-5xl: 3.815rem;
    --leading-tight: 1.25;
    --leading-normal: 1.6;
    --leading-relaxed: 1.75;
    --space-1: 8px;
    --space-2: 16px;
    --space-3: 24px;
    --space-4: 32px;
    --space-5: 40px;
    --space-6: 48px;
    --space-7: 56px;
    --space-10: 80px;
    --space-12: 96px;
    --space-15: 120px;
    --nav-height: 70px;
    --shadow-sm: 0 1px 3px rgba(26,35,50,0.08);
    --shadow-md: 0 4px 12px rgba(26,35,50,0.06);
    --shadow-lg: 0 8px 24px rgba(26,35,50,0.08);
    --shadow-xl: 0 12px 32px rgba(26,35,50,0.1);
}
```

**Key Color Difference from Other Sites:**
- ragedesigner uses `--logo-blue` (#325d74) as primary action color
- ragedesigner uses `--copper` (#B7704F) as accent/secondary
- Other sites (whatisaframework, howtoframework) use `--primary` (#E67E50 orange)

---

## 📋 REQUIRED META TAGS

⚠️ **CURRENT ISSUE:** Missing og:image tag. This needs to be fixed.

Every page MUST include these in `<head>`:

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[PAGE TITLE] | RageDesigner</title>
<meta name="description" content="[PAGE DESCRIPTION]">
<meta property="og:title" content="[PAGE TITLE]">
<meta property="og:description" content="[PAGE DESCRIPTION]">
<meta property="og:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/Rage-designer-landing-page-cover.png">
<meta property="og:url" content="https://ragedesigner.com/[PAGE-SLUG]">
<meta property="og:type" content="website">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/Rage-designer-landing-page-cover.png">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**Default OG Image:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/Rage-designer-landing-page-cover.png`

---

## 🔝 CANONICAL HEADER

### Header HTML Structure
```html
<nav id="navbar">
    <a href="/" class="logo-link">
        <span class="logo-text">RAGE<span>DESIGNER</span></span>
    </a>
    <div class="nav-links">
        <a href="/portfolio.html">Portfolio</a>
        <a href="/blog/">Blog</a>
        <a href="https://app.ragedesigner.com/contact/" class="nav-cta">Get Started</a>
    </div>
</nav>
```

### Header CSS (Required)
```css
nav { background: rgba(255,255,255,0.98); backdrop-filter: blur(10px); padding: var(--space-2) var(--space-6); border-bottom: 1px solid var(--logo-blue-light); position: fixed; top: 0; left: 0; right: 0; z-index: 100; box-shadow: var(--shadow-sm); display: flex; justify-content: space-between; align-items: center; height: var(--nav-height); transition: all 0.3s ease; }
nav.scrolled { box-shadow: var(--shadow-md); }
.logo-link { display: flex; align-items: center; text-decoration: none; }
.logo-text { font-size: var(--text-xl); font-weight: 700; color: var(--charcoal-blue); letter-spacing: 0.05em; }
.logo-text span { color: var(--logo-blue); }
.nav-links { display: flex; align-items: center; gap: var(--space-4); }
.nav-links a { color: var(--charcoal-light); text-decoration: none; font-weight: 500; transition: color 0.2s ease; position: relative; }
.nav-links a:not(.nav-cta)::after { content: ''; position: absolute; bottom: -4px; left: 0; width: 0; height: 2px; background: var(--logo-blue); transition: width 0.3s ease; }
.nav-links a:not(.nav-cta):hover::after { width: 100%; }
.nav-links a:hover { color: var(--logo-blue); }
.nav-cta { display: inline-block; background: var(--logo-blue); color: var(--white) !important; padding: 12px var(--space-3); font-size: var(--text-sm); font-weight: 600; border-radius: 8px; transition: all 0.3s ease; border: 2px solid var(--logo-blue); }
.nav-cta:hover { background: transparent; color: var(--logo-blue) !important; transform: translateY(-2px); }

@media (max-width: 768px) {
    nav { padding: var(--space-2) var(--space-3); }
    .nav-links a:not(.nav-cta) { display: none; }
    .nav-cta { padding: 10px var(--space-2); font-size: var(--text-xs); }
}
```

### ⚠️ HEADER NOTES:
- ragedesigner uses TEXT logo (RAGE<span>DESIGNER</span>), not image logo
- "RAGE" is charcoal-blue, "DESIGNER" is logo-blue
- Nav CTA goes to `https://app.ragedesigner.com/contact/` (note trailing slash)
- No mobile hamburger menu currently implemented (links hidden on mobile except CTA)

---

## 🔻 CANONICAL FOOTER

### Footer HTML Structure
```html
<footer>
    <div class="footer-content">
        <div class="footer-brand">
            <div class="footer-logo">
                <img src="https://app.ragedesigner.com/wp-content/uploads/2021/02/ragedesigner1.png" alt="RageDesigner">
            </div>
            <p>Strategic Design & Marketing Intelligence since 1999. Building systems that compound.</p>
        </div>
        <div class="footer-column">
            <h4>Services</h4>
            <ul>
                <li><a href="/foundation-services.html">Foundation Services</a></li>
                <li><a href="/integrated-solutions.html">Integrated Solutions</a></li>
                <li><a href="/consulting.html">Strategic Consulting</a></li>
            </ul>
        </div>
        <div class="footer-column">
            <h4>Resources</h4>
            <ul>
                <li><a href="/portfolio.html">Portfolio</a></li>
                <li><a href="/blog/">Blog</a></li>
                <li><a href="https://whatisaframework.com" target="_blank">What Is A Framework?</a></li>
            </ul>
        </div>
        <div class="footer-column">
            <h4>Connect</h4>
            <ul>
                <li><a href="https://app.ragedesigner.com/contact/">Contact</a></li>
                <li><a href="https://app.ragedesigner.com/newsletter-sign-up/">Newsletter</a></li>
            </ul>
        </div>
    </div>
    <div class="footer-bottom">
        <p>© 2026 RageDesigner</p>
    </div>
</footer>
```

### Footer CSS (Required)
```css
footer { padding: var(--space-10) var(--space-3) var(--space-5); background: #0f151d; color: var(--white); }
.footer-content { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: var(--space-6); margin-bottom: var(--space-7); }
.footer-brand .footer-logo { margin-bottom: var(--space-3); }
.footer-brand .footer-logo img { height: 50px; width: auto; }
.footer-brand p { color: rgba(255,255,255,0.6); font-size: var(--text-base); margin-bottom: 0; }
.footer-column h4 { color: var(--white); font-size: var(--text-base); font-weight: 600; margin-bottom: var(--space-3); }
.footer-column ul { list-style: none; }
.footer-column li { margin-bottom: var(--space-2); }
.footer-column a { color: rgba(255,255,255,0.6); text-decoration: none; font-size: var(--text-base); transition: color 0.2s ease; }
.footer-column a:hover { color: var(--copper); }
.footer-bottom { text-align: center; padding-top: var(--space-5); border-top: 1px solid rgba(255,255,255,0.1); }
.footer-bottom p { font-size: var(--text-sm); margin-bottom: 0; color: var(--copper); }

@media (max-width: 1024px) {
    .footer-content { grid-template-columns: 1fr 1fr; gap: var(--space-5); }
}
@media (max-width: 768px) {
    .footer-content { grid-template-columns: 1fr; text-align: center; }
}
```

### ⚠️ CRITICAL FOOTER NOTES:
- **Footer background:** `#0f151d` (darker than charcoal-blue)
- **Footer link hover color:** `var(--copper)` (#B7704F) - NOT orange
- **Copyright text color:** `var(--copper)` (#B7704F)
- **Contact link:** `https://app.ragedesigner.com/contact/` (WITH app. prefix)
- **4-column grid layout** on desktop
- Uses image logo in footer (different from text logo in header)

---

## 🔘 BUTTON STYLES

### Primary Button (Logo Blue)
```css
.btn-primary { display: inline-block; background: var(--logo-blue); color: var(--white); padding: var(--space-2) var(--space-6); font-size: var(--text-md); font-weight: 600; text-decoration: none; border-radius: 8px; transition: all 0.3s ease; border: 2px solid var(--logo-blue); box-shadow: 0 4px 16px rgba(50,93,116,0.3); }
.btn-primary:hover { background: transparent; color: var(--logo-blue); transform: translateY(-3px); box-shadow: 0 8px 24px rgba(50,93,116,0.4); }
```

### Secondary Button (Copper)
```css
.btn-secondary { display: inline-block; background: transparent; color: var(--white); padding: var(--space-2) var(--space-6); font-size: var(--text-md); font-weight: 600; text-decoration: none; border-radius: 8px; transition: all 0.3s ease; border: 2px solid var(--copper); }
.btn-secondary:hover { background: var(--copper); color: var(--white); transform: translateY(-3px); box-shadow: 0 8px 24px rgba(183,112,79,0.3); }
```

### Card Button (Copper fill)
```css
.btn-card { display: inline-block; background: var(--copper); color: var(--white); padding: 14px var(--space-4); font-size: var(--text-sm); font-weight: 600; text-decoration: none; border-radius: 8px; text-align: center; transition: all 0.3s ease; border: 2px solid var(--copper); }
.btn-card:hover { background: transparent; color: var(--copper); transform: translateY(-2px); }
```

---

## ✅ CHECKLIST: Before Deploying Any Page

- [ ] CSS variables include all required values
- [ ] og:image meta tag present (CURRENTLY MISSING IN INDEX - FIX NEEDED)
- [ ] twitter:image meta tag present
- [ ] Header HTML matches this reference exactly
- [ ] Footer HTML matches this reference exactly
- [ ] Contact links use `https://app.ragedesigner.com/contact/` (with app. prefix)
- [ ] Footer hover color is copper (#B7704F), NOT orange
- [ ] Logo text: "RAGE" in charcoal-blue, "DESIGNER" in logo-blue

---

## 🚫 KNOWN BAD PATTERNS (Do Not Use)

### Wrong Contact URL:
```html
<!-- BAD - missing app. prefix -->
<a href="https://ragedesigner.com/contact">Contact</a>

<!-- GOOD - correct URL with app. prefix -->
<a href="https://app.ragedesigner.com/contact/">Contact</a>
```

### Wrong Footer Colors:
```html
<!-- BAD - using orange instead of copper -->
.footer-column a:hover { color: var(--orange); }

<!-- GOOD - ragedesigner uses copper -->
.footer-column a:hover { color: var(--copper); }
```

### Missing og:image:
```html
<!-- BAD - no social sharing image -->
<head>
    <title>Page Title</title>
    <!-- missing og:image - causes ugly social shares -->
</head>
```

---

## 📁 FILE LOCATIONS

- **Logo (Footer):** `https://app.ragedesigner.com/wp-content/uploads/2021/02/ragedesigner1.png`
- **Default OG Image:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/Rage-designer-landing-page-cover.png`
- **Hero Background:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/Rage-designer-landing-page-cover.png`

---

## 🔗 CROSS-SITE LINKS

This site links to:
- whatisaframework.com (What Is A Framework?)
- app.ragedesigner.com/contact/ (Contact forms - WordPress)
- app.ragedesigner.com/newsletter-sign-up/ (Newsletter - WordPress)

**Note:** ragedesigner.com (GitHub Pages) links to app.ragedesigner.com (WordPress) for forms and dynamic content.

---

## 🔄 VERSION HISTORY

| Date | Change | Source |
|------|--------|--------|
| 2026-01-10 | Initial template reference created | index.html SHA: 3487b90c |

---

## ⚠️ KNOWN ISSUES TO FIX

1. **Missing og:image tags** - index.html needs og:image and twitter:image meta tags
2. **No mobile navigation** - Currently hides nav links on mobile, only shows CTA

---

*This is the source of truth. When in doubt, copy from here.*
