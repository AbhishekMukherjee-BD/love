# Soft Love Texture - Typography & Design System Specification

## 1. Aesthetic Inspiration & Pin Typography Analysis

After analyzing the aesthetics of your Pinterest pins (`https://pin.it/1yHkoJ9qz`, `https://in.pinterest.com/pin/51861833204761827/`, `https://pin.it/5jcoBTMCY`, etc.), the design language blends 4 distinct typographic layers:

1. **High-Elegance Romantic Serif (Headers & Titles):**
   - Inspired by classic love letters, editorial romance magazines, and vintage book typography.
   - Used for main section headers, page titles, and quote hero statements.
   
2. **Organic Handwritten Cursive Script (Love Notes & Polaroid Captions):**
   - Inspired by personal handwritten letters, tape stickers, and romantic memory annotations.
   - Gives the feeling of hand-annotated memories written directly onto the polaroids.

3. **Vintage Typewriter & Postcard Accent (Dates, Stamps & Micro-copy):**
   - Inspired by vintage postage stamps, postcard timestamps, and wax seal tags.
   - Adds authenticity and nostalgia to dates and location tags.

4. **Modern Minimalist Sans-Serif (UI Controls, Timers & Buttons):**
   - Clean, highly readable, touch-friendly UI elements for mobile devices.

---

## 2. Google Fonts Selection & Integration

Add the following `<link>` tag into the `<head>` of all HTML files (`index.html`, `memories.html`, `finale.html`):

```html
<!-- Google Fonts Import for Soft Love Texture Aesthetic -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Dancing+Script:wght@500;700&family=Caveat:wght@500;700&family=Courier+Prime:ital,wght@0,400;0,700;1,400&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

### Font Stack Mapping:
- **Display Serif (`--font-serif`):** `'Cormorant Garamond', 'Playfair Display', Georgia, serif`
- **Handwritten Script Primary (`--font-script`):** `'Dancing Script', 'Caveat', cursive`
- **Handwritten Note Secondary (`--font-casual`):** `'Caveat', cursive`
- **Vintage Typewriter (`--font-typewriter`):** `'Courier Prime', monospace`
- **Modern UI Sans (`--font-sans`):** `'Outfit', -apple-system, BlinkMacSystemFont, sans-serif`

---

## 3. OKLCH Soft Love Color Palette

```css
:root {
  /* Soft Love Texture Palette */
  --color-bg-base: oklch(98.5% 0.015 350);       /* Softest Cream Milk (#FFF8F9) */
  --color-bg-card: oklch(99.5% 0.008 340);       /* Pure Warm Card Base */
  --color-rose-blush: oklch(92% 0.05 350);       /* Gentle Rose Petal (#FFE3E8) */
  --color-rose-deep: oklch(58% 0.22 350);        /* Romantic Deep Rose (#E63956) */
  --color-velvet-berry: oklch(35% 0.16 350);     /* Deep Velvet Plum (#610A2B) */
  --color-warm-gold: oklch(85% 0.12 85);         /* Soft Gold Highlight (#F4D35E) */
  --color-text-primary: oklch(24% 0.04 350);     /* Deep Rose Graphite for text */
  --color-text-muted: oklch(52% 0.05 350);       /* Soft Muted Rose Brown */
  
  /* Glassmorphism & Shadow Tokens */
  --glass-bg: rgba(255, 248, 249, 0.72);
  --glass-border: 1px solid rgba(255, 227, 232, 0.5);
  --shadow-card: 0 12px 32px -8px rgba(97, 10, 43, 0.08), 0 4px 12px -2px rgba(0, 0, 0, 0.03);
  --shadow-polaroid: 0 16px 40px -10px rgba(0, 0, 0, 0.12), 0 2px 6px 0 rgba(0, 0, 0, 0.04);
}
```

---

## 4. Fluid Typography Scale & Baseline Rhythm

Vertical spacing adheres strictly to an **8px baseline grid** (8px, 16px, 24px, 32px, 48px, 64px) with fluid `clamp()` sizing for mobile responsiveness.

```css
:root {
  /* Fluid Sizing Tokens */
  --text-xs: clamp(0.75rem, 0.7rem + 0.25vw, 0.875rem);       /* 12px - 14px */
  --text-sm: clamp(0.875rem, 0.82rem + 0.3vw, 1rem);          /* 14px - 16px */
  --text-base: clamp(1rem, 0.95rem + 0.4vw, 1.125rem);       /* 16px - 18px */
  --text-lg: clamp(1.25rem, 1.15rem + 0.6vw, 1.5rem);        /* 20px - 24px */
  --text-xl: clamp(1.75rem, 1.5rem + 1.2vw, 2.25rem);        /* 28px - 36px */
  --text-hero: clamp(2.5rem, 2rem + 2.5vw, 3.75rem);         /* 40px - 60px */

  /* Line Heights */
  --lh-tight: 1.15;
  --lh-normal: 1.5;
  --lh-script: 1.35;
}
```

---

## 5. CSS Utility Classes for Pins & Overlay Typography

### A. Main Hero Title (`.title-hero-romantic`)
```css
.title-hero-romantic {
  font-family: var(--font-serif);
  font-size: var(--text-hero);
  font-weight: 600;
  font-style: italic;
  color: var(--color-velvet-berry);
  line-height: var(--lh-tight);
  letter-spacing: -0.02em;
  text-shadow: 0 2px 10px rgba(230, 57, 86, 0.15);
}
```

### B. Polaroid Handwritten Caption (`.note-handwritten`)
```css
.note-handwritten {
  font-family: var(--font-script);
  font-size: var(--text-lg);
  color: var(--color-text-primary);
  line-height: var(--lh-script);
  transform: rotate(-1.5deg);
}
```

### C. Stamp / Date Tag (`.stamp-date-tag`)
```css
.stamp-date-tag {
  font-family: var(--font-typewriter);
  font-size: var(--text-xs);
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--color-rose-deep);
  background: var(--color-rose-blush);
  padding: 4px 10px;
  border-radius: 4px;
  border: 1px dashed var(--color-rose-deep);
}
```

### D. Video Overlay Typography Container (Part 3 Scroll Video)
```css
.video-overlay-caption {
  position: absolute;
  padding: 16px 24px;
  background: var(--glass-bg);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: var(--glass-border);
  border-radius: 16px;
  box-shadow: var(--shadow-card);
  max-width: 85%;
  transition: opacity 0.4s cubic-bezier(0.16, 1, 0.3, 1), transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}

.video-overlay-caption h3 {
  font-family: var(--font-serif);
  font-size: var(--text-xl);
  color: var(--color-velvet-berry);
  margin-bottom: 6px;
}

.video-overlay-caption p {
  font-family: var(--font-script);
  font-size: var(--text-lg);
  color: var(--color-text-primary);
}
```

---

## 6. Motion & Easing Curves

```css
:root {
  --ease-soft-spring: cubic-bezier(0.175, 0.885, 0.32, 1.275);
  --ease-smooth-peel: cubic-bezier(0.16, 1, 0.3, 1);
  --ease-gentle-float: cubic-bezier(0.4, 0, 0.2, 1);
}
```
