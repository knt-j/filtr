# Filter.im Clone — Implementation Tasks

Reference: `reference/PROMPT.md` and `reference/images/1.png` through `31.png`

---

## TASK 1: Hero Shrink Animation
**Status**: TODO
**Reference**: Images 1, 2

- [ ] Hero starts at full 100vw × 100vh, NO border-radius
- [ ] As user scrolls (0–200px), hero scales down to ~93% width and gets `border-radius: var(--section-radius)` (~20px)
- [ ] Hero stays sticky at top during transition
- [ ] Hero has `background-color` matching the section, rounded card look when shrunk
- [ ] After shrink, page scrolls normally revealing next section underneath

Implementation: JS scroll listener on `window`, apply `transform: scale()` and `border-radius` to `.hero` inner card. Or use CSS `scale()` with a scroll-driven animation.

---

## TASK 2: Vertical Grid Lines
**Status**: TODO
**Reference**: Images 2, 3

- [ ] 5 vertical lines creating 6-column grid
- [ ] Lines are subtle (1px, ~10-15% white opacity)
- [ ] Lines have gradient mask: `mask-image: linear-gradient(to bottom, transparent 0%, #000 15%, #000 85%, transparent 100%)`
- [ ] Lines animate IN with upward reveal (wipe from bottom) when What We Do section enters viewport
- [ ] Lines persist throughout the page (fixed or scroll-relative positioning within a full-height container)

Implementation: Add `#grid-lines` div with 5 child divs. Position as `position: fixed` or a tall `position: sticky` container. Use IntersectionObserver to trigger reveal animation.

---

## TASK 3: Featured Project Cards — New Animation
**Status**: TODO
**Reference**: Images 5–11

### 3a: Card entry from bottom (grow upward)
- [ ] Card starts at bottom of viewport, small (e.g., height 35%, centered horizontally)
- [ ] As card's scroll zone is entered, it grows upward to fill full viewport
- [ ] The card-inner has `transform: scaleY(0.35) translateY(30%)` initially → `scaleY(1) translateY(0)` at full
- [ ] Transition is smooth, driven by scroll position (JS rAF loop)

### 3b: Top and bottom blur on card edges
- [ ] Card has vignette blur at top and bottom edges during growth
- [ ] Use CSS pseudo-elements or `mask-image` gradient on `.featured-project-card-inner`
- [ ] The blur/fade is prominent (30-40px from each edge)

### 3c: Fall-behind exit effect
- [ ] When the NEXT card starts growing, current card applies: `transform: scale(0.92)`, `filter: brightness(0.7)`, `transition: all 0.4s`
- [ ] Effect: current card appears to push backward in z-space
- [ ] LAST CARD (card 4, Web Design) does NOT get this effect — stays in place

### 3d: z-index and sticky still work
- [ ] Still use `position: sticky; top: 0` for each card wrap
- [ ] Increasing z-index so new cards stack on top
- [ ] The "fall behind" effect via CSS class added by JS

---

## TASK 4: Filter Studio → Growing Panel Display
**Status**: TODO
**Reference**: Images 12–19

### 4a: "Filter Studio" initial state
- [ ] Section shows "Filter" text (left) and "Studio" text (right) on same line, centered
- [ ] No video/panel initially
- [ ] Both on a dark background (the spotlight inner card)

### 4b: Growing panel between text
- [ ] A panel container appears between "Filter" and "Studio"
- [ ] Panel starts TINY (like 8rem × 6rem)
- [ ] As user scrolls, panel GROWS in both height and width
- [ ] Panel shows 2-3 columns of project images/videos
- [ ] Images cycle as user scrolls (different client videos appear at different scroll positions)
- [ ] "Filter" and "Studio" text get pushed outward horizontally as panel widens

### 4c: Text hides behind panel
- [ ] When panel is large enough, "Filter" and "Studio" text are BEHIND the panel (z-index lower)
- [ ] Panel's edges coincide with the 2 innermost vertical grid lines

### Panel videos to cycle through (in order of appearance):
1. Guidebook / analytics UI (early)
2. Sperm Racing video
3. Street scene / city
4. Rhythm "Your Market." 
5. Crypto/finance content
6. Multiple client images

---

## TASK 5: Discover Section — Large Text + Circular Mask
**Status**: TODO
**Reference**: Images 20–23

### 5a: Large client name text
- [ ] Client names displayed at VERY LARGE font size (clamp(4rem, 10vw, 8rem) or larger)
- [ ] Vertically stacked list
- [ ] Names overflow viewport height (scroll-driven list movement)
- [ ] Active client (in center viewport zone) is WHITE, others GRAY (opacity: 0.3)
- [ ] List scrolls UPWARD as user scrolls page

### 5b: Circular/elliptical background mask
- [ ] Client background image/video shows through a LARGE CIRCLE/ELLIPSE mask
- [ ] The circle is in the center of the section
- [ ] Creates a "portal" effect where the background is visible only within the circle
- [ ] CSS: `clip-path: ellipse(40% 45% at 50% 50%)` on the background layer

### 5c: Thumbnail cards on right side
- [ ] 3 thumbnail cards positioned at right side (~75-80% from left)
- [ ] Cards appear to be at: y=10%, y=35%, y=65% of section height
- [ ] Each card shows a project image (small, ~200px wide)
- [ ] Cards cycle/change per client

### 5d: "Discover" label
- [ ] Small "DISCOVER" label at left side (position: absolute, left: 5%)
- [ ] Stays visible during scroll

---

## TASK 6: Discover → Reviews Card Transition
**Status**: TODO
**Reference**: Images 24–28

- [ ] Last Discover thumbnail card animates: moves from its position → center of screen → integrates into review row
- [ ] This requires the thumbnail's position to be tracked and animated independently
- [ ] Possible approach: Use CSS transition + JS to move the card to the center during the scroll between sections
- [ ] The "In their words." header and Rive icon appear as the card settles

Implementation: This may be simplest as a fixed-position card that moves with scroll, then becomes static in the reviews section layout.

---

## TASK 7: Reviews → Gallery Radial Blur Transition
**Status**: TODO
**Reference**: Images 29–31

- [ ] At the bottom of the reviews section, a radial white glow/blur expands from center
- [ ] CSS: `radial-gradient(ellipse at center, rgba(255,255,255,0.9) 0%, transparent 60%)` overlay
- [ ] OR: a white circular div that scales up from size 0 to 200vw
- [ ] This white expansion acts as the transition into the Gallery section (which is white bg)
- [ ] Triggered by IntersectionObserver as gallery section enters viewport

---

## IMPLEMENTATION ORDER

1. [ ] **TASK 2**: Grid lines (needed to understand layout for cards)
2. [ ] **TASK 1**: Hero shrink (establishes the visual language)
3. [ ] **TASK 3**: Featured project card animation (most complex scroll behavior)
4. [ ] **TASK 4**: Filter Studio growing panels (most visually complex section)
5. [ ] **TASK 5**: Discover section large text + circular mask
6. [ ] **TASK 6**: Discover→Reviews card transition
7. [ ] **TASK 7**: Reviews→Gallery radial blur

---

## NOTES FOR FUTURE SESSIONS

- All reference images are at `/home/jj/projects/filter/reference/images/`
- The HTML file is at `/home/jj/projects/filter/index.html`
- Dev server runs on `http://localhost:8090/` (start with `python3 -m http.server 8090`)
- The file is very large (250k+ tokens) — always use `offset+limit` when reading
- Key CSS sections: lines 1-285 (styles), key HTML sections read previous notes
- NEVER use /tmp for storage — use project directory or `/home/jj/projects/filter/`
