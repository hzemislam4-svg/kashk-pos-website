---
name: Kashk POS Pro — Download Landing
description: A thermal-receipt download page for the Kashk POS Pro point-of-sale app.
colors:
  paper: "#f6f2e7"
  paper-2: "#efeadd"
  ink: "#1c1a16"
  ink-2: "#4c463c"
  red: "#c22a22"
  red-deep: "#9e1f18"
  glow: "#f2c14e"
  backdrop: "#171310"
  backdrop-2: "#221b14"
typography:
  display:
    fontFamily: "'Cairo', Tahoma, 'Segoe UI', sans-serif"
    fontSize: "clamp(30px, 9vw, 40px)"
    fontWeight: 900
    lineHeight: 1.15
    letterSpacing: "-0.01em"
  title:
    fontFamily: "'Cairo', Tahoma, 'Segoe UI', sans-serif"
    fontSize: "19px"
    fontWeight: 900
  body:
    fontFamily: "'Cairo', Tahoma, 'Segoe UI', sans-serif"
    fontSize: "14.5px"
    fontWeight: 600
    lineHeight: 1.75
  label:
    fontFamily: "'IBM Plex Mono', Consolas, monospace"
    fontSize: "11.5px"
    fontWeight: 700
    letterSpacing: "2px"
  grand-total:
    fontFamily: "'IBM Plex Mono', Consolas, monospace"
    fontSize: "40px"
    fontWeight: 700
    lineHeight: 1
rounded:
  sm: "3px"
  md: "4px"
  lg: "6px"
  pill: "99px"
spacing:
  xs: "6px"
  sm: "10px"
  md: "14px"
  lg: "22px"
  xl: "26px"
components:
  button-red:
    backgroundColor: "{colors.red}"
    textColor: "#fff7ee"
    rounded: "{rounded.sm}"
    padding: "12px 18px"
  button-red-hover:
    backgroundColor: "{colors.red-deep}"
  button-ink:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.paper}"
    rounded: "{rounded.sm}"
    padding: "12px 18px"
  button-ink-hover:
    backgroundColor: "#000000"
  item-card:
    backgroundColor: "{colors.paper-2}"
    rounded: "{rounded.md}"
    padding: "16px 18px 18px"
  link-chip:
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "7px 13px"
---

# Design System: Kashk POS Pro — Download Landing

## Overview

**Creative North Star: "The Morning Receipt"**

The page is a single thermal-receipt printout from a small-shop kiosk: warm cream paper that glows against a dark storefront backdrop, cut with perforation teeth, and torn from the roll at the bottom. Every element is a real receipt object — a header stamp, two "line items" (the Android APK and the iPhone install), a features block that reads like a price list, a grand total rendered in cash-register mono, a barcode, and a "thank you" closer. Nothing on the page breaks the illusion of paper: even focus states behave like a fresh ink stamp.

Personality is honest, retro, and warm — one small merchant speaking to another. Density is medium: receipt-lazy spacing, generous line-height, but no wasted decoration. The mood is calm confidence, not hype.

**Key Characteristics:**
- A single paper tape on a dark ambient backdrop; the paper is the only light source.
- Perforation, dashes, dots, and torn edges as the only "borders".
- Red ink as the only accent, used sparingly for price, marks, and stamp moments.
- Cairo for everything human; IBM Plex Mono for machine/cash-register moments.
- Print-on-scroll: blocks snap in one line at a time, like a receipt being printed.

## Colors

One warm cream paper, one warm ink, and one red stamp ink. Everything else is a shadow or a tint of these.

### Primary
- **Red Stamp** (#c22a22): the accent — prices, feature marks, the "grand total" value, the header "PRO" stamp, and the underline that prints under section titles. Press-state deepens to #9e1f18. Rarity is the point: it never fills areas, only marks moments.

### Neutral
- **Warm Paper** (#f6f2e7): the receipt surface. Variant **Old Paper** (#efeadd) backs the two line-item cards. All text sits on paper.
- **Warm Ink** (#1c1a16): the primary text color and the barcode color. **Soft Ink** (#4c463c): secondary text (taglines, descriptions, totals). Dotted leaders and dashed rules use ink at 35–50% opacity.
- **Focus Amber** (#f2c14e): the keyboard-focus ring — a visible "marker pen" outline (3px, 2px offset) that survives on any surface.
- **Storefront Backdrop** (#171310 → #221b14): the warm near-black page background, with faint amber radial glows that suggest the shop's interior light.

### Named Rules
**The Single Ink Rule.** Red appears on ≤5% of any screen. The fewer red moments, the more each one means.
**The Paper Boundary Rule.** The tape never shares its surface with the backdrop — either you're on paper or you're in the dark storefront. Never place paper-colored UI on the dark backdrop; give it a real paper edge or nothing.

## Typography

**Display Font:** Cairo (with Tahoma, Segoe UI fallbacks) — warm, geometric, native to Arabic.
**Body Font:** Cairo.
**Label/Mono Font:** IBM Plex Mono (with Consolas fallback) — cash-register moments only.

**Character:** Cairo carries all human voice, bold and steady; the mono face speaks only as the machine printing the receipt. The pair sells the small-shop honesty: a person wrote it, a register printed it.

### Hierarchy
- **Display** (900, clamp 30px→40px, 1.15, -0.01em): the app name at the top of the tape. The "PRO" mark inside turns red.
- **Headline** (900, 16px): section titles ("المميزات", "خصوصيتك") — small caps of authority, with a red underline that prints on scroll.
- **Title** (900, 19px): the line-item labels (أندرويد / آيفون) and their prices.
- **Body** (600, 14.5px, 1.75): feature rows and item descriptions, max ~65ch.
- **Label** (Plex Mono, 700, 10–12px, +2px letter-spacing when used as caption): ticket meta, version, file size, barcode caption.
- **Grand Total** (Plex Mono, 700, 40px): the "0 د.ج" moment — the single most important number on the tape, rendered like a cash register.

### Named Rules
**The Machine Voice Rule.** IBM Plex Mono is reserved for register numbers and ticket meta. Never set human prose in mono.

## Layout

A single centered column on a min(520px, 100%) tape, hugged by `padding: clamp(16px, 4vw, 48px)` on the page body. The tape's inner padding rhythm is 22px top/bottom, 26px sides (narrowing to 18px under 420px).

Vertical rhythm, top to bottom: header stamp → ticket meta (dashed rule above) → line-item cards (2px dashed outline, 14px apart) → dashed-rule feature block → totals → dashed grand-total box → privacy trust lines → dashed footer links → barcode → thank-you → torn edge.

Responsive: below 420px, action buttons inside each item stack to full width. The rest of the tape is intrinsically fluid — flex leaders absorb the slack. Everything is RTL; leaders and separators are mirrored accordingly.

## Elevation & Depth

Almost no elevation — the design is tonal. The paper is lit, the backdrop is dark, and that light difference is the primary depth cue. Shadows appear only at the tape's physical edges:

### Shadow Vocabulary
- **Tape drop** (`0 24px 60px -18px rgba(0,0,0,.7), 0 6px 22px rgba(0,0,0,.45)` + `inset 0 1px 0 rgba(255,255,255,.5)`): the paper's mass floating in the dark shop.
- **Torn-edge cast** (`filter: drop-shadow(0 3px 3px rgba(0,0,0,.25))`): the bottom tear physically lifts off the roll.
- **Button hard shadow** (`0 2px 0` the button's deep color): the tactile "pressable key" of the register.

### Named Rules
**The Paper Is Flat Rule.** Surfaces never stack with soft shadows. Shadow only ever reads as *the paper's own thickness* — under the tape and under the tear. The one exception is the button's 2px mechanical press.

## Shapes

Form language is "cut paper": nearly-square, slightly-rounded, punched and torn. Radius is a whisper, never a statement.

- **Tape top**: 6px — the paper's own folded corner.
- **Buttons**: 3px — a register key.
- **Item cards, pro note, grand box**: 4px — clean ticket cards.
- **Link chips**: fully round (99px) pills — the only "designed" object, letting the copy inside stay tactile.
- **Perforation**: teeth (2px dots on 6px rhythm) run down both tape sides; the item cards each carry a punched half-dot at the top edge.
- **Barcode**: a repeating 90° ink-line stripe with a soft mask, standing in for a real barcode.
- **Torn edge**: a jagged clip-path bottom, cut at 45°-like steps, wearing the paper's drop-shadow.

## Components

### Buttons
- **Shape:** 3px radius, inline-flex with 8px icon gap, 12px 18px padding, weight 800, 15px.
- **Primary (Red):** red paper-stamp background, cream text, hard 2px shadow of the deep red; hover deepens to #9e1f18 and lifts 1px; active presses down 1px. Used only for "تحميل APK" and the WhatsApp install action — two red moments.
- **Secondary (Ink):** ink background, paper text; hover goes black. Used for "اقرأ دليل الاستخدام".
- **Focus:** 3px amber outline at 2px offset — the marker-pen state.

### Cards (Line Items)
- **Corner Style:** 4px.
- **Background:** old paper (#efeadd) against the paper tape — the only tonal layering allowed.
- **Border:** 2px dashed ink at 35% — a cut-ticket outline, not a box.
- **Internal Padding:** 16px 18px 18px.
- **Signature detail:** a 12px punched half-circle at the top-right edge, echoing the tape's perforation.

### Chips (Footer Links)
- **Style:** transparent, ink text, 1.5px dashed? no — 1.5px solid ink at 45%, fully round; hover inverts to ink fill / paper text.
- **State:** hover and focus only (amber focus ring).

### Grand Total Box
- The receipt's climax: 2px dashed outline, centered, Plex Mono 40px red value ("0 د.ج") — the "price of the download".

### Section Titles
- Flex with a dashed rule filling the remaining width, plus a red underline that *prints* (scaleX from the right, 0.8s) the moment the section scrolls into view.

## Do's and Don'ts

### Do:
- **Do** keep every surface either paper (#f6f2e7 family) or dark backdrop (#171310 family) — never mix, never invent a third theme.
- **Do** use red only to mark moments: prices, checks, the PRO stamp, the grand total. If a screen shows red, let it be the single reason the eye stops there.
- **Do** print with dotted leaders and dashed rules instead of box borders when a separator is needed.
- **Do** let IBM Plex Mono carry every number that smells like a register: version, size, total, barcode caption.
- **Do** keep the receipt grammar — header, items, totals, thank-you — intact in any future section you add.

### Don't:
- **Don't** add soft card shadows, gradients inside the tape, or elevation stacking — the paper is flat; only its physical edges cast.
- **Don't** set human prose in IBM Plex Mono, or the machine voice is lost.
- **Don't** enlarge radii into rounded-modern territory; a 3–6px whisper keeps the cut-paper fiction.
- **Don't** place red on more than a couple of interactive moments per viewport.
- **Don't** break RTL mirroring: leaders, perforation, and the print direction all originate from the right.
