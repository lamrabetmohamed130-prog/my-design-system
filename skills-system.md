# My Web Design System v1.0

## IDENTITY
- Theme: Dark Premium SaaS
- Font: 'Segoe UI', Arial, Helvetica, sans-serif
- Base size: 17px
- Line height: 1.78
- Zero JavaScript required
- Zero external fonts
- Single breakpoint: 620px

## COLOR TOKENS
- --bg-base: #080b14
- --bg-alt: #0c1020
- --bg-deep: #06080f
- --bg-card: #0c1320
- --bg-footer: #050710
- --accent: #00d4ff
- --accent-hover: #33ddff
- --accent-dim: rgba(0,212,255,0.12)
- --accent-border: rgba(0,212,255,0.15)
- --accent-border-hover: rgba(0,212,255,0.38)
- --text-white: #ffffff
- --text-body: #c0cce0
- --text-secondary: #8da8c4
- --text-muted: #5a7080
- --text-footer: #3a5060
- --green: #20c55a
- --red: #ff4d4d
- --amber: #ffa000
- --gold: #ffd000

## TYPOGRAPHY SCALE
- H1: clamp(2rem, 5.5vw, 3.3rem) | weight 900 | color #ffffff | letter-spacing -0.02em
- H2: clamp(1.5rem, 3.8vw, 2.3rem) | weight 800 | color #ffffff
- H3: clamp(1.1rem, 2.5vw, 1.45rem) | weight 700 | color #00d4ff (ALWAYS accent)
- Body: 17px | weight 400 | color #c0cce0 | line-height 1.78
- Stat number: 1.9rem | weight 900 | color #00d4ff
- Price display: 2.4rem | weight 900 | color #00d4ff
- Badge: 0.73rem | weight 700 | uppercase | color #00d4ff
- Pill: 0.8rem | weight 700 | uppercase | border-radius 50px

## SPACING SYSTEM (4px base grid)
- --sp-1: 4px
- --sp-2: 8px
- --sp-3: 13px
- --sp-4: 18px
- --sp-5: 22px
- --sp-6: 26px
- --sp-7: 38px
- --sp-8: 52px
- --sp-9: 64px (section padding desktop)
- --sp-10: 86px (hero padding)
- Section padding mobile: 44px 0
- Container gutter: 22px
- Card padding: 26px 20px
- CTA box padding: 38px 30px desktop / 26px 16px mobile

## LAYOUT SYSTEM
- .container: max-width 860px (ALL editorial content)
- .wide: max-width 1140px (footer, link cloud only)
- Section alternation: #080b14 → #0c1020 → #080b14 → #0c1020
- CTA interrupt background: #06080f (sits OUTSIDE section elements)
- Card grid: repeat(auto-fit, minmax(230px, 1fr)) gap 18px
- Mobile breakpoint: 620px (only one)

## BORDER RADIUS
- --r-sm: 7px (link chips)
- --r-md: 11px (table wrapper)
- --r-lg: 13px (cards, TOC)
- --r-xl: 16px (CTA box)
- --r-pill: 50px (pill badge)
- --r-callout: 0 10px 10px 0 (highlight boxes - flat left edge)

## GRADIENTS
- Hero bg: radial-gradient(ellipse at 20% 60%, rgba(98,0,234,0.12) 0%, transparent 55%), radial-gradient(ellipse at 75% 25%, rgba(0,145,234,0.1) 0%, transparent 55%), linear-gradient(160deg, #04060f 0%, #080d1e 50%, #030810 100%)
- Table header: linear-gradient(90deg, #0b1630, #0d1d3a)
- Btn primary: linear-gradient(90deg, #00c4f0, #0088cc)
- Btn green: linear-gradient(90deg, #20c55a, #10843a)
- Top bar: linear-gradient(90deg, #6200ea, #0091ea)
- CTA box: linear-gradient(135deg, #0a1228 0%, #07101f 100%)
- Step circle: linear-gradient(135deg, #00c4f0, #0077aa)

## PAGE STRUCTURE (always follow this order)
1. Top Offer Bar (gradient bg, strikethrough price)
2. Hero (layered gradient bg, pill + h1 + chips)
3. Breadcrumb nav
4. Stat Strip (4-6 metrics)
5. [CONTENT LOOP START]
6. section bg #080b14
7. section.alt bg #0c1020
8. CTA Interrupt div bg #06080f
9. [REPEAT until end]
10. Link Cloud (.wide container)
11. Footer (.wide container)

## CTA PLACEMENT (5 mandatory points)
1. After "why this product" explanation section
2. After comparison table or feature grid
3. After setup/how-to guides (intent peak)
4. After customer reviews (trust peak)
5. After FAQ — final close

## COMPONENTS

### TOP OFFER BAR
HTML: <div class="topbar">⚡ OFFER — Name: <s>£OLD</s> <strong>£NEW/yr</strong> · Benefit · Free Trial</div>
CSS: background linear-gradient(90deg,#6200ea,#0091ea), padding 13px 20px, font-weight 700, color #fff

### HERO
Structure: pill badge → h1 (with .accent span) → hero-sub paragraph → hero-chips flex row
Key: ::after pseudo fade matches next section background exactly
Pill: border-radius 50px, rgba(0,212,255,0.1) bg, 1px solid rgba(0,212,255,0.25) border
Chip: rgba(255,255,255,0.04) bg, 1px solid rgba(0,212,255,0.15) border, border-radius 8px

### CTA BOX
HTML: <div class="cta-box"><h3>Headline</h3><div class="price-big"><s>£OLD</s> £NEW<span>/yr</span></div><div class="price-note">Note</div><p>Copy</p><div class="btn-group">...</div></div>
CSS: gradient bg, border 1px solid rgba(0,212,255,0.2), border-left 4px solid #00d4ff, border-radius 16px
Variants: border-left-color #00d4ff default | #20c55a success | #ffa000 warning
Rule: max 3 buttons per btn-group

### BUTTONS
btn-blue: gradient(#00c4f0,#0088cc), color #000, shadow 0 4px 24px rgba(0,196,240,0.32)
btn-green: gradient(#20c55a,#10843a), color #fff, shadow 0 4px 20px rgba(32,197,90,0.28)
btn-outline: transparent bg, border 2px solid #00d4ff, color #00d4ff
All buttons: font-weight 800, padding 15px 30px, border-radius 9px, transition transform 0.14s box-shadow 0.14s
Hover: translateY(-2px) + expanded shadow
Button order: [btn-blue primary] [btn-outline secondary] [btn-green channel]

### FEATURE CARDS
HTML: <div class="grid"><div class="card"><div class="card-ic">🏆</div><h3>Title</h3><p>Desc</p></div></div>
Grid: repeat(auto-fit, minmax(230px, 1fr)) gap 18px
Card: bg #0c1320, border 1px solid rgba(0,212,255,0.12), border-radius 13px
Hover: border rgba(0,212,255,0.38) + translateY(-3px)
card h3 color: #e8eef8 (near-white, NOT accent - inside cards h3 is title not section marker)

### CALLOUT BOXES
box-info: border-left 4px solid #00d4ff, bg rgba(0,212,255,0.06), text #98b8cc
box-warn: border-left 4px solid #ffa000, bg rgba(255,160,0,0.06), text #c8a860
box-success: border-left 4px solid #20c55a, bg rgba(32,197,90,0.06), text #7ac890
All: border-radius 0 10px 10px 0, padding 18px 22px, margin 26px 0

### NUMBERED STEPS
HTML: <ol class="steps"><li><strong>Title</strong><span>Description</span></li></ol>
CSS: counter-reset s, counter-increment s, ::before content counter(s)
Circle: 38px, border-radius 50%, gradient bg, color #000, flex-shrink 0
Separator: border-bottom 1px solid rgba(255,255,255,0.05), last-child none

### DATA TABLE
Wrapper: overflow-x auto, border-radius 11px, border 1px solid rgba(0,212,255,0.13)
thead th: gradient bg, color #00d4ff, border-bottom 2px solid rgba(0,212,255,0.25)
.tr-best: color #fff, font-weight 700, first-child color #00d4ff
.yes: color #00d4ff, font-weight 700
.no: color #ff4d4d
Even rows: bg rgba(0,212,255,0.025)
Hover rows: bg rgba(0,212,255,0.05)

### REVIEW CARDS
HTML: <div class="rev-card"><div class="rev-stars">★★★★★</div><p class="rev-text">"Quote"</p><div class="rev-name">— Name, City</div></div>
rev-stars: color #ffd000
rev-text: color #9aacc0, font-style italic, font-size 0.93rem
rev-name: color #506070, font-size 0.82rem

### FAQ (STATIC - always visible for SEO)
HTML: <div class="faq"><div class="faq-q"><div class="faq-question">Q?</div><div class="faq-answer">A.</div></div></div>
faq-q: bg #0c1220, border 1px solid rgba(0,212,255,0.13), border-radius 10px
faq-question: padding 18px 22px, color #e4eaf6, font-weight 700
faq-answer: padding 16px 22px, color #96a8bc, border-top 1px solid rgba(0,212,255,0.1), bg #070d1a

### BADGE (inline in headings)
HTML: <span class="badge">LABEL</span>
CSS: font-size 0.73rem, font-weight 700, padding 3px 11px, border-radius 5px, bg rgba(0,212,255,0.12), border 1px solid rgba(0,212,255,0.28), color #00d4ff, uppercase

### STAT STRIP
HTML: <div class="stats"><div class="stat"><div class="stat-n">VALUE</div><div class="stat-l">Label</div></div></div>
stats: display flex, flex-wrap wrap, bg #060910, borders top+bottom 1px solid rgba(0,212,255,0.08)
stat: flex 1 1 130px, text-align center, padding 26px 16px, border-right 1px solid rgba(0,212,255,0.07)
stat-n: 1.9rem, weight 900, color #00d4ff
stat-l: 0.78rem, color #5a7080, uppercase, letter-spacing 0.09em

### LINK CLOUD
HTML: <div class="link-cloud"><a href="/page/" class="lchip">Topic</a></div>
lchip: bg #0c1320, border 1px solid rgba(0,212,255,0.13), border-radius 7px, padding 8px 16px, color #7a9ab4
Hover: border rgba(0,212,255,0.4), color #00d4ff

### TOC
HTML: <div class="toc"><div class="toc-title">📋 Table of Contents</div><ol>...</ol></div>
CSS: bg #0b1220, border 1px solid rgba(0,212,255,0.14), border-radius 13px, padding 24px 28px
toc-title: color #00d4ff, 0.82rem, font-weight 800, uppercase, letter-spacing 0.12em
Links: color #7a9ab4, hover color #00d4ff

## CSS SKILLS REFERENCE

### Fluid Typography
font-size: clamp(MIN, PREFERRED_VW, MAX);

### Auto-reflow Grid
grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));

### GPU-only Transitions
transition: transform 0.14s, box-shadow 0.14s;
NEVER transition: width, height, padding, margin

### Hero Section Fade
.hero::after { content:''; position:absolute; bottom:-1px; left:0; right:0; height:60px; background:linear-gradient(to bottom, transparent, #080b14); pointer-events:none; }

### CSS Counter Steps
.steps { counter-reset: s; }
.steps li { counter-increment: s; display:flex; gap:16px; }
.steps li::before { content:counter(s); min-width:38px; height:38px; border-radius:50%; display:flex; align-items:center; justify-content:center; }

### Price Anchor Display
.price-big s { font-size:1.3rem; color:#4a5e70; font-weight:400; }

## CONVERSION PSYCHOLOGY RULES
- Always show crossed-out price BEFORE live price
- Risk reversal phrases: "No credit card" · "No contract" · "Cancel anytime" · "Free trial"
- Social proof: use specific name + city + outcome (not generic)
- Urgency: "Limited-time" language without fake countdown timers
- FAQ addresses exact objections that stop purchase
- Max 3 buttons per CTA group

## CTA COPY FORMULA
- Headline: [Emoji] [Benefit hook] — [Risk reduction phrase]
- Price: [Crossed-out old] → [New price] [/period]
- Sub-note: [Saving] · [Benefit] · [No credit card required]
- Body: one sentence urgency or social proof
- Buttons: [Primary btn-blue] [Secondary btn-outline] [Channel btn-green]

## SEO REQUIREMENTS (every page)
- lang attribute on html tag
- meta description 150-160 chars with primary keyword
- meta robots: index, follow
- canonical link tag
- og:title, og:description, og:url, og:type
- twitter:card summary_large_image
- Article schema JSON-LD in head
- FAQPage schema JSON-LD (text must match HTML exactly)
- One H1 only, keyword in first 10 words
- Breadcrumb nav element
- Internal link cloud at page bottom
- dateModified updated on every edit

## PERFORMANCE RULES
- System fonts only — zero external font loading
- All UI via CSS/gradients/emoji — zero image requests for UI
- Zero JavaScript required for full page
- Only transition GPU-compositable properties
- pointer-events none on decorative pseudo-elements

## NAMING CONVENTIONS
- Blocks: .card .btn .stat .hero .toc .faq
- Elements: .card-ic .stat-n .stat-l .faq-question .faq-answer
- Modifiers: .btn-blue .btn-green .btn-outline .box-info .box-warn .box-success
- States: .yes .no .tr-best .accent .alt
- Containers: .container (860px) .wide (1140px)
