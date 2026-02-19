# portfolio
# 🔴 STRANGER THINGS PORTFOLIO — COMPLETE BUILD PROMPT
### Full Specification for Rebuilding This Dark Horror-Tech AI Engineer Portfolio

---

## ⚠️ BEFORE YOU START — INFORMATION YOU MUST COLLECT

Before pasting this prompt into Claude, fill in every `[ ]` placeholder below.
Claude cannot guess your links, images, or personal details — you must provide them.

---

## 📋 PERSONAL INFORMATION CHECKLIST

### 👤 Basic Details
| Field | Your Value |
|---|---|
| Full Name | `[YOUR FULL NAME]` e.g. AIOSHI CHOWDHURY |
| Degree | `[YOUR DEGREE]` e.g. B.Tech / B.E. |
| Subject | `[YOUR SUBJECT]` e.g. Computer Science & Engineering |
| College | `[YOUR COLLEGE NAME]` |
| CGPA | `[YOUR CGPA]` |
| Graduation Year | `[YEAR]` |

### 📞 Contact (optional — only add if you want them visible)
| Field | Your Value |
|---|---|
| Phone | `[+91-XXXXXXXXXX]` |
| Email | `[yourname@gmail.com]` |

---

## 🔗 LINKS YOU MUST PROVIDE

### Social Media
```
LinkedIn  →  https://linkedin.com/in/[YOUR-USERNAME]
GitHub    →  https://github.com/[YOUR-USERNAME]
LeetCode  →  https://leetcode.com/[YOUR-USERNAME]
```

### Certifications
```
Notion / Google Drive / any page link  →  https://[YOUR-CERT-LINK]
```

### Projects (for each project, provide):
```
Project 1 Name      →  [NAME]
Project 1 Link      →  https://[github / colab / live link]
Project 1 Tools     →  Python, TensorFlow, etc.
Project 1 Desc      →  [2-3 line description]

Project 2 Name      →  [NAME]
Project 2 Link      →  https://[link]
...repeat for all projects
```

### People I Follow (for each person, provide):
```
Person 1 Name       →  [NAME]
Person 1 Role       →  [Job Title / Platform]
Person 1 Bio        →  [2-line description]
Person 1 LinkedIn   →  https://linkedin.com/in/[username]
Person 1 Photo      →  [Upload the image file separately]

...repeat for all 4 people
```

---

---

# 🚀 THE FULL PROMPT — PASTE THIS INTO CLAUDE

---

## PROMPT STARTS BELOW

---

Create a **fully responsive, single-file HTML portfolio website** using only HTML, CSS, and vanilla JavaScript (no frameworks).

The visual theme must be a **Stranger Things–inspired dark horror sci-fi aesthetic** — "Entering the Upside Down: An AI Engineer's Control Room."

Do NOT copy any copyrighted Stranger Things logos or licensed fonts. Instead, recreate the aesthetic using freely available Google Fonts and CSS techniques.

---

## 🎨 COLOR SYSTEM & FONTS

```
Background:   #0a0a0a  (deep black)
Card BG:      rgba(59,10,10,0.25)  (dark crimson tint)
Primary Red:  #ff0033  (neon blood red — all glows, borders, accents)
Dark Red:     #8b0000  (gradient base)
Crimson:      #3b0a0a  (card fills)
Blue Accent:  #4fc3f7  (very subtle — glitch effect only)
Text:         #f5f0e8  (bright off-white — ALL text must be bold and clearly legible)
```

**Google Fonts to import:**
- `Bebas Neue` — all section headings, hero name, card titles
- `Oswald` (weight 500–700) — all body text, descriptions, labels
- `Share Tech Mono` — tags, tools, dates, monospace labels

---

## 🌌 BACKGROUND & ATMOSPHERE

Build the background using a `<canvas>` element (id="bg-canvas") fixed behind all content:

1. **Fog base** — `ctx.fillStyle = 'rgba(10,5,5,0.2)'` on each frame for trailing fog
2. **Radial red glow** — centered radial gradient, `rgba(139,0,0,0.06)` fading to transparent
3. **Star field** — 250 stars with perspective projection (z-depth) drifting slowly inward, colored `#cc4444` (dark red stars, not white)
4. **Floating spores** — 180 particles drifting slowly upward like Upside Down ash. Colors: mix of `#ff0033`, `#8b0000`, `#ffffff`
5. **Lightning flash** — random red screen flash (`rgba(255,0,51,0.06)`) every 4–8 seconds, lasting ~8 frames

**Overlay effects (CSS only):**
- CRT scanlines via `body::after` — `repeating-linear-gradient` with `rgba(255,0,51,0.018)` every 4px
- Scroll parallax: canvas star field shifts slightly with `window.scrollY`

---

## 🖱️ GLOBAL INTERACTIONS

- **Custom cursor**: Red glowing dot (14px) + outer ring (40px) that follows mouse — use `#cur` and `#cur-ring` divs
- **Scroll progress bar**: Fixed 3px bar at top, `linear-gradient(90deg, #8b0000, #ff0033)` with red glow
- **Section fade-in**: All sections start `opacity:0; transform:translateY(35px)` and transition in when entering viewport (IntersectionObserver, threshold 0.1)
- **Smooth scroll**: `html { scroll-behavior: smooth; }`

---

## 🔤 TEXT ANIMATIONS

### Glitch effect (keyframes — apply to hero name and nav logo):
```css
@keyframes glitch {
  0%,100% { text-shadow: 0 0 30px #ff0033; transform: none; }
  20%     { text-shadow: -3px 0 #4fc3f7, 3px 0 #ff0033; transform: translate(-1px,0); }
  40%     { text-shadow: 3px 0 #4fc3f7, -3px 0 #ff0033; transform: translate(1px,0); }
  60%     { text-shadow: -2px 0 #ff0033; transform: translate(-1px,1px); }
  80%     { text-shadow: 2px 0 #4fc3f7; transform: translate(1px,-1px); }
}
```

### Flicker effect (apply to nav logo and section titles):
```css
@keyframes flicker {
  0%,100% { opacity:1; }
  91% { opacity:1; } 92% { opacity:0.6; }
  93% { opacity:1; } 95% { opacity:0.8; } 96% { opacity:1; }
}
```

### Typing effect (hero subtitle):
- JavaScript loop cycling through an array of role phrases
- Display in `Share Tech Mono`, red color, red glow text-shadow
- Blinking red cursor (`|`)

---

## 🧭 NAVBAR

- Fixed, full-width, `backdrop-filter: blur(16px)`, `background: rgba(10,10,10,0.85)`
- Bottom border: `1px solid rgba(255,0,51,0.2)`
- Logo: **Bebas Neue**, large letter-spacing, red color, flicker animation
- Nav links: Oswald 700, uppercase, letter-spacing 3px
- Hover: red color + red glow text-shadow + animated red underline (width expands from 0 to 100%)

**Nav links (in order):**
Home · Education · Projects · Skills · Certifications · Awards · Following

---

## 👤 HERO SECTION

- Full viewport height, flex column, centered, text-align center
- Radial dark red background glow behind content

### Profile Image:
- 200×200px circular `<img>` with `object-fit: cover`
- Wrapped in `.profile-wrap` with two child divs:
  - `.glow-spin` — conic gradient ring (`conic-gradient(#ff0033, #3b0a0a, #ff0033, #660000, #ff0033)`) rotating with `spin` animation
  - `.glow-mask` — solid `#0a0a0a` circle that masks inner edge of ring
- Image border: `2px solid rgba(255,0,51,0.4)` with `pulse-glow` animation
- **Image placeholder**: `src="profile.jpg"` — user uploads their own photo

### Hero Text:
```
Name:     [YOUR FULL NAME]          ← Bebas Neue, clamp(2.8rem,7vw,5.5rem), white, glitch + flicker
Subtitle: [DEGREE] · [COLLEGE]     ← Oswald 600, letter-spacing 3px
```

### Typing phrases (customize these):
```javascript
const phrases = [
  'AI Engineer',
  'ML Developer',
  'Deep Learning Researcher',
  'Exploring the Unknown'
];
```

### Social Buttons:
- Three buttons: **LinkedIn**, **GitHub**, **LeetCode**
- Style: outlined red border, Oswald 700, uppercase, letter-spacing
- Hover: red fill sweeps from left (scaleX transform), text turns black
- Links:
  ```
  LinkedIn  →  https://linkedin.com/in/[YOUR-USERNAME]
  GitHub    →  https://github.com/[YOUR-USERNAME]
  LeetCode  →  https://leetcode.com/[YOUR-USERNAME]
  ```

---

## 🎓 EDUCATION SECTION

**Layout:** Vertical red glowing timeline (left border line with red glow)

Each entry: `.t-item` card with:
- Left `::before` pseudo-element: red glowing dot (16px circle, `pulse-glow`)
- Fields: Year range, School name (Bebas Neue), Degree/stream (Oswald), Score (Bebas Neue, large, red glow)
- Hover: slide right `translateX(8px)` + border brightens

**Your entries:**
```
[INSTITUTION 1]
Degree: [B.Tech / B.E. / etc.]
Stream: [Computer Science & Engineering]
Score:  CGPA [X.X]
Years:  [20XX — 20XX]

[INSTITUTION 2]
Exam:   [CBSE 12th / HSC / etc.]
Score:  [XX%]
Year:   [20XX]

[INSTITUTION 3]
Exam:   [CBSE 10th / SSC / etc.]
Score:  [XX%]
Year:   [20XX]
```

---

## 🚀 PROJECTS SECTION

**Layout:** CSS Grid, `repeat(auto-fit, minmax(460px, 1fr))`, gap 1.5rem

Each `.proj-card`:
- Dark crimson background, red border (0.25 opacity)
- `::before` — red line sweeps across top on hover
- `::after` — diagonal red glow overlay on hover
- Hover: `translateY(-5px)` + red border + red box-shadow
- Large faded number (Bebas Neue, 3rem, 0.1 opacity) in top-right corner
- **VHS glitch** on project number when card is hovered
- **3D tilt effect** on mousemove (perspective rotateX/rotateY)

Each card contains:
- Project number (01, 02, 03, 04...)
- Project title (Bebas Neue, letter-spacing 3px)
- Tool tags (Share Tech Mono, red border/color, small)
- Description (Oswald 500, 1rem, 1.7 line-height)
- Link button (Share Tech Mono, red color, underline, hover turns white)

**Provide for each project:**
```
Title:       [PROJECT NAME]
Tools:       [comma-separated list]
Description: [2–3 sentences]
Link label:  → VIEW ON GITHUB / → VIEW ON COLAB / → VIEW PUBLICATION
Link URL:    https://[your link]
```

---

## 💻 SKILLS SECTION

**Layout:** CSS Grid, `repeat(auto-fit, minmax(300px, 1fr))`, 3 columns

Each `.skill-cat`:
- Category heading: Bebas Neue, red color, red glow, letter-spacing 5px
- Skill bars: 4px height, `background: rgba(255,255,255,0.06)` track
- Fill: `linear-gradient(90deg, #8b0000, #ff0033)`, red box-shadow
- Animate from width 0 → target % when section enters viewport (IntersectionObserver)

**Your skills (set percentage 0–100):**
```
Languages:
  Python         [XX%]
  Java           [XX%]
  SQL            [XX%]

Core Subjects:
  Machine Learning   [XX%]
  Deep Learning      [XX%]
  OOPs               [XX%]

Tools & Platforms:
  Google Colab / Jupyter  [XX%]
  Power BI                [XX%]
  AWS Cloud               [XX%]
```

---

## 🏆 CERTIFICATIONS SECTION

**Layout:** CSS Grid, `repeat(auto-fit, minmax(230px, 1fr))`

Each `.cert-card`:
- Dark crimson tinted background, red border
- Small red triangle (`▲`) in top-right corner
- Hover: red border, red box-shadow, `translateY(-3px)`
- Font: Oswald 600 for cert name, Share Tech Mono for issuer

**Your certifications:**
```
[CERTIFICATION NAME]    — [ISSUER PLATFORM]
[CERTIFICATION NAME]    — [ISSUER PLATFORM]
... (add as many as needed)
```

**Certifications link:**
```
View all certificates  →  https://[YOUR NOTION / DRIVE LINK]
```

---

## 🏅 ACHIEVEMENTS SECTION

**Layout:** Flexbox wrap

Each `.badge`:
- Dark crimson background, red border (0.3 opacity)
- Flex row: emoji icon + text
- Hover: red border, red background tint, scale(1.02)
- Font: Oswald 700, textbold color

**Your achievements:**
```
[EMOJI]  [Achievement description]
[EMOJI]  [Achievement description]
... (add as many as needed)
```

---

## 👥 PEOPLE I FOLLOW SECTION

**Layout:** CSS Grid, 2×2 (2 columns, 2 rows), `max-width: 860px`, centered

Each `.follow-card`:
- Dark crimson background, red border
- Flex column, centered, text-align center
- Red line sweeps across top on hover
- Hover: red border glow, `translateY(-6px)`

Each card contains:
- **Circular photo** (110×110px) with spinning red conic gradient ring (same as hero profile)
- **Name** (Bebas Neue, letter-spacing 4px) — glitch animation on hover
- **Role** (Share Tech Mono, red color, uppercase, small)
- **Bio** (Oswald 500, 0.95rem, 1.65 line-height)

**Provide for each of the 4 people:**
```
Person 1:
  Name:   [FULL NAME]
  Role:   [Job Title / Platform]
  Bio:    [2-line description]
  Photo:  [Upload image file — will be embedded as base64]
  LinkedIn: https://linkedin.com/in/[username]   ← optional, for card link

Person 2:
  Name:   [FULL NAME]
  Role:   [Job Title / Platform]
  Bio:    [2-line description]
  Photo:  [Upload image file]
  LinkedIn: https://linkedin.com/in/[username]

Person 3: ...
Person 4: ...
```

**Footer tagline** (bold, red glow):
```
"...and many more minds shaping the future that I continuously follow."
```

---

## 🎵 BACKGROUND MUSIC

- `<audio id="bgm" loop>` tag with `src="background-music.mp3"`
- Does NOT autoplay (browser policy) — user clicks the button to start
- Floating circular button fixed bottom-right: 58px circle, red border, dark background, `backdrop-filter: blur`
- Shows 🔇 when off, 🔊 when playing
- `pulse-glow` animation plays on button when music is active
- **To use:** Place your MP3 file in the same folder as the HTML and name it `background-music.mp3`

---

## 🦶 FOOTER

- `border-top: 1px solid rgba(255,0,51,0.15)`
- Font: Share Tech Mono, 0.78rem, dim white, letter-spacing 3px
- Text: `▲ [YOUR NAME] · AI ENGINEER · INTO THE UPSIDE DOWN · [YEAR] ▲`

---

## 📱 RESPONSIVE (MOBILE)

At `max-width: 768px`:
- Hide navbar links (hamburger menu optional)
- Single column grid for projects and follow cards
- Hero name font-size reduced to 2.5rem
- Reduce section padding to 5rem 1.5rem

---

## 🖼️ FILES TO PREPARE BEFORE BUILDING

Collect all of these before starting:

| File | Description |
|---|---|
| `profile.jpg` | Your profile photo (any size — will be cropped circular) |
| `background-music.mp3` | Ambient/synthwave/horror audio file for background loop |
| `person1.jpg` | Photo of Person 1 in "People I Follow" |
| `person2.jpg` | Photo of Person 2 |
| `person3.jpg` | Photo of Person 3 |
| `person4.jpg` | Photo of Person 4 |

> 💡 **Tip:** Upload all image files directly in your Claude message. Claude will embed them as base64 inside the HTML so the final file is completely self-contained — no external files needed.

---

## 🔗 COMPLETE LINKS CHECKLIST

Copy this checklist and fill it before pasting the prompt:

```
═══════════════════════════════════════════
         PORTFOLIO LINKS CHECKLIST
═══════════════════════════════════════════

SOCIAL:
[ ] LinkedIn   →  https://linkedin.com/in/________
[ ] GitHub     →  https://github.com/__________
[ ] LeetCode   →  https://leetcode.com/__________

CERTIFICATIONS:
[ ] Cert page  →  https://________________

PROJECTS:
[ ] Project 1  →  https://________________
[ ] Project 2  →  https://________________
[ ] Project 3  →  https://________________
[ ] Project 4  →  https://________________

PEOPLE I FOLLOW (LinkedIn):
[ ] Person 1   →  https://linkedin.com/in/________
[ ] Person 2   →  https://linkedin.com/in/________
[ ] Person 3   →  https://linkedin.com/in/________
[ ] Person 4   →  https://linkedin.com/in/________

PUBLICATION (if any):
[ ] DOI / URL  →  https://________________
```

---

## ✅ FINAL INSTRUCTION TO CLAUDE

End your prompt with:

> "Generate the complete, single-file `index.html` with all CSS and JavaScript inline.
> Embed all uploaded images as base64 data URIs directly in the HTML.
> The file must be fully self-contained — no external file dependencies except Google Fonts and `background-music.mp3`.
> Make all text **bold and clearly visible** against the dark background.
> Match the dark horror sci-fi Stranger Things aesthetic throughout every section."

---

## 📌 QUICK REFERENCE — WHAT THIS PORTFOLIO CONTAINS

| Section | Content |
|---|---|
| Hero | Photo · Name · Animated typing subtitle · Social buttons |
| Education | Timeline with 3 entries (college + 2 school boards) |
| Projects | 4 project cards with tools, description, links |
| Skills | 3 categories with animated red progress bars |
| Certifications | Card grid with all certs + link to full cert page |
| Achievements | Badge row with emoji + description |
| People I Follow | 2×2 grid with photos, names, bios |
| Footer | Name + year tagline |
| Global | Animated canvas bg · Custom cursor · Scroll bar · Music toggle |

---

*Document generated from the actual working Stranger Things portfolio built with Claude · 2026*
