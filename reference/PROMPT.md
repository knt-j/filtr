# Filter.im Clone — Complete Visual Specification

All reference images are in `reference/images/1.png` through `reference/images/31.png`.

---

## SECTION 1: HERO — Images 1, 2

**Image 1**: Hero is full viewport height and width. Dark gray/black background. Large phone mockup centered/right. "The studio behind the world's leading companies." bottom-left. CTA buttons. Brand logos (Octane, Coinbase, RedBull, Whop, Bland, Azura, Newmark, Cluely, HelloTrade, Figma, Klyra, Fragile) bottom-right. NO border-radius. Fills 100vw × 100vh.

**As user scrolls**: Hero SHRINKS — it gets border-radius and scale down, staying sticky at top. It transforms into a rounded card that fits between the vertical grid lines. The shrinking happens over ~200px of scroll.

**Image 2**: Hero has shrunk to ~90% width with large border-radius (~20px), dark rounded card. Below it: the vertical grid lines are visible (5 columns), and the What We Do section with Rive icon + large centered text is visible. A cursor dot (small gray circle) is visible — the custom cursor.

---

## SECTION 2: GRID LINES — Images 2, 3

**Image 2**: Grid lines appear below/after the hero. 5 vertical lines creating 6 columns. Lines are very subtle (near-transparent white or gray).

**Image 3**: Full view of grid lines. They FADE at top and bottom (gradient mask — transparent at extremes, visible in middle). This creates an infinite-feel column guide. The lines ANIMATE IN by revealing upward from the bottom (clip/reveal animation) a few seconds after the second section shows. The grid lines appear on EVERY SECTION throughout the page and fade top+bottom always.

---

## SECTION 3: FEATURED PROJECT CARDS — Images 5–11

The cards work COMPLETELY DIFFERENTLY from our current sticky stack:

**Entry animation (Images 4, 5, 6)**:
- Each card starts SMALL at the BOTTOM of the viewport (small card, like 30-40% of the viewport height)
- The card's content is visible but compressed/scaled
- As user scrolls, the card GROWS UPWARD to fill the full viewport height
- At the exact moment it fills its final space (touching top and bottom "lines"), it's at full size

**Image 5**: First card entering — "Filter is full stack" header still visible at top, small card at bottom starting to appear.

**Image 6**: Card has grown more — "Identities that get remembered." (label) at top-left, "Brand Design" title visible near bottom-left. Video visible on right. Card fills bottom ~70% of screen. Two visible column grid lines frame it.

**Image 7**: Card is almost full viewport height. **IMPORTANT**: There is a TOP BLUR and BOTTOM BLUR on the card — like gradient vignette/fade at both edges. When the card is in its growth phase, the top and bottom edges of the card are blurred/faded.

**Image 8**: Card has reached the top edge of viewport. Now FULLY REVEALED. When it touches the top (fills the viewport), any further scroll makes it "FALL BEHIND" — the card recedes in z-space (appears to push backwards/inward). It gets slightly smaller, darker, or blurred as if moving away from the user.

**Image 9**: Second card (Product Design with Coinbase finance app) starts appearing at the BOTTOM, small. Meanwhile first card (Brand Design) is FALLING BEHIND — it's still visible but darker/receded. Both visible simultaneously.

**Image 10**: Second card has grown more, now overlapping/covering the first card that continues to recede. Transition midpoint.

**Image 11**: LAST CARD (Web Design, laptop mockup). This card does NOT fall behind. It grows to fill the viewport and STAYS THERE as the final state. Web Design title at bottom-left, laptop photo on right.

**Key behavior summary**:
1. Card enters from bottom (small → grows upward to fill viewport)
2. Card has top+bottom blur/vignette during growth
3. When NEXT card starts, CURRENT card "falls behind" (push-back/scale effect)
4. LAST CARD (card 4) stays — does not fall behind

---

## SECTION 4: FILTER STUDIO → DISCOVER — Images 12–20

This section is completely different from our current implementation.

### Phase A: "Filter Studio" text appears (Image 12)
- Black background with the spotlight inner card
- "Filter Studio" text appears centered — just text, no video yet
- Plain centered text: "Filter" [space] "Studio"

### Phase B: Panels grow between text (Images 13–19)
As user scrolls, a PANEL/IMAGE DISPLAY appears BETWEEN "Filter" and "Studio":
- The panel starts VERY SMALL (tiny thumbnails)
- It GROWS in both HEIGHT and WIDTH as user scrolls
- The panel shows MULTIPLE project images/videos arranged in a 2-3 column grid
- The images CYCLE/CHANGE as user scrolls (different client projects appear at different scroll positions)
- "Filter" and "Studio" text get pushed to the extreme left and right as the panel widens
- The panel eventually gets so tall and wide that it hides the "Filter" and "Studio" text behind it (text goes BEHIND the panel)

**Image 13**: Small thumbnail panel between "Filter" and "Studio" — shows "Guidebook" app and analytics UI. 2 columns.
**Image 14**: Panel medium-sized. Shows different projects.
**Image 15**: Panel larger. Sperm Racing logo visible.
**Image 16**: Panel very large. Street scene and project overlays.
**Image 17**: Panel nearly full height. "Your Market." Rhythm text visible.
**Image 18**: Panel nearly full size. "Crypto..." text visible. Filter/Studio text pushed to far edges.
**Image 19**: Panel covers the Filter/Studio text. The text is BEHIND the panel. Two vertical lines (column lines) visible at left and right edges of the panels. This is the transition to Discover.

### Phase C: Discover section fades in (Image 20)
- Full-bleed dark background with client background image/video
- Client names displayed as VERY LARGE TEXT (8-10vw font size) — much larger than current
- Vertical list of clients
- Circular/elliptical mask — client background shows through a large circle
- "Discover" label at left
- Thumbnail cards on RIGHT side (3 cards, positioned at different heights)

---

## SECTION 5: DISCOVER SECTION — Images 20–23

**Image 20**: 
- "Trade" (partial left, gray) | "Coinbase" (active, white, center) | "Clanker" (right, gray)
- This looks like a HORIZONTAL TICKER or very large vertically-scrolling names
- Wait — looking more carefully: The client names are ENORMOUS (fills most of screen width each) and scrolling
- Right side: Two thumbnail cards (Mottbook and a purple/colorful one)
- Left side: "Discover" label
- Circular background texture/mask visible

**Image 21**:
- "Discover" label still visible
- Client list (vertically stacked, large): Figma, Coinbase, Cluely, Sperm Racing, Rhythm (active)
- CIRCULAR MASK visible — a large circle/oval clips the background image
- "id" visible at bottom-left (= end of "Liquid")
- Three thumbnail cards on right side in different vertical positions
- The text list is cut off with circular mask

**Image 22**:
- Rhythm is active client (white text)
- Three thumbnail cards on right: stacked vertically
- Background shows street scene / Rhythm brand visuals
- Client names (very large): partially cut off at top and bottom

**Image 23**:
- Liquid is the last/final active client
- Background: SPOT/able text visible (Liquid brand)
- One thumbnail card on right
- The section is about to end

---

## SECTION 6: DISCOVER → REVIEWS TRANSITION — Images 24–28

The THUMBNAIL CARD from the Discover section transitions into the Reviews section:

**Image 24**: One thumbnail card (computer/Mac) visible at top-right area. Section starting to exit.
**Image 25**: The thumbnail card is MOVING DOWN toward the center. Dark background.
**Image 26**: Card is now in the center of the screen, growing larger.
**Image 27**: Card is near the center, with the Rive icon and "In their words." text appearing above it. The card is becoming a review card.
**Image 28**: Reviews section fully revealed: Rive icon → "In their words." → Row of review cards. The card that traveled is now integrated as one of the review cards.

---

## SECTION 7: REVIEWS → GALLERY TRANSITION — Images 29–31

**Image 29**: At the bottom of the reviews section, a RADIAL BLUR effect appears. It's a bright white expanding radial glow/blur in the center of the screen. The review cards below are visible but starting to be obscured by the white glow.

**Image 30**: The radial blur is very intense — a bright white/blown-out ellipse/circle in the center. The Gallery section is starting to become visible below. This creates a dramatic "white flash" transition.

**Image 31**: Gallery Callout section fully visible. White background. Floating device images (800+ project images card, phone mockups, computer mockups). "See more of our work." centered text. "Explore Gallery" button.

---

## WHAT'S ALREADY WORKING (do not break)
- Custom cursor
- Top bar scroll shrink (logo → small "Filter" text)
- Hero section layout and content
- What We Do text with highlighted words and Rive icon
- "What We Ship" section header
- CTA section (pure white)
- Footer + Footer Reel
- Client Reviews (mostly correct)
- Gallery Callout (mostly correct)
