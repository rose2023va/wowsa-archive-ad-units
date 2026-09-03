# WOWSA Archive Promotion Units

Six ready-to-paste HTML files for the WordPress article archive ad positions, sidebar, scraper and footer. Each file is self-contained: inline `<style>` scoped to a unique wrapper class, no build step, no external CSS or JS. Paste the whole file's contents into the existing Custom HTML widget for that position.

Approved design (navy `#0C2650`, ivory `#FAF7F2`, gold `#B5925C`, Cormorant Garamond over Karla), confirmed live and unchanged as of 3 September 2026. Full mockup and design rationale: https://claude.ai/code/artifact/7699c4ed-9536-41c5-b73e-a321fc775f8b

## Current strategy: capture, not sale

As of 3 September 2026, every unit leads to email capture. None link to a paid checkout. Quinn, 10:44am: *"Priority is email collection."* 11:12am: *"the goal is to not sell from ads on our site, it's to get emails and segment."* Coaches and organizers get sold to afterward, by correspondence, once they're identified through the signup.

Do not add a price, a checkout link, or a certification claim to any of these units without checking that this strategy is still current.

## The six files

| File | Slot | Size | Where | Destination |
|---|---|---|---|---|
| `slot-a-top-scraper.html` | A | 970 x 120 | Above the article title | `/learn/reading-risk`, coach framing |
| `slot-b-sidebar-banner.html` | B | 300 x 600 | Sidebar, top | `/learn/reading-risk`, organizer framing |
| `slot-c-sidebar-square.html` | C | 300 x 250 | Sidebar, below banner | `/learn/reading-risk` |
| `slot-d-bottom-scraper.html` | D | 970 x 120 | Below the article body | `/learn/courses/marathon-swimming` |
| `slot-e-sidebar-square-alt.html` | E | 300 x 250 | Sidebar, in place of C | `/learn/reading-risk` |
| `slot-f-footer-widget.html` | F | Fluid | Footer widget row, alongside "Top Open Water Swimming Books" and "Discover" | `/learn/reading-risk` |

**Two units per page, not five.** One from the top/bottom scraper pair (A or D) and one from the sidebar (B, C, or E). Running all five on one article crowds the read and trains readers to ignore them. C and E are two visual treatments of the same offer, light and dark, use one or the other in a given sidebar, not both.

All destination URLs were checked live on 3 September 2026 and returned 200.

## Header

There is no separate ad-widget slot in the header the way there is in the sidebar and footer. The only header-level mechanism currently live on the site is the **WOWSA Announcement Bar** plugin (`wowsa-announcement-bar`, one bar above the primary navigation, one message at a time). It is currently occupied by the WOWSA Awards 2026 nomination campaign, text "2026 WOWSA Awards nominations are now open," CTA to wowsaawards.com.

Using it for Reading Risk would replace that message, not add to it. Before building anything for the header, confirm with Quinn whether the Awards campaign is meant to still be running, and whether the announcement bar is the intended header placement at all, or whether a different header mechanism is wanted.

## Rollout order

1. **Global sidebar first.** Pick one sidebar unit (B, C, or E) and add it to the site-wide sidebar template. This alone reaches the 9,354 general-editorial pages that carry roughly two thirds of the archive's clicks.
2. **Conditional by category next.** Coach-tagged and profile pages get the coach-framed unit (A or B's coach copy), event and race pages get the organizer framing, safety and conditions pages get slot C or E. Same two-unit-per-page rule applies.
3. **In-content on the top pages last.** Add A and/or D inside the article body on the highest-traffic 100 pages, which carry about half of all archive clicks. Highest effort, highest return, do it last.

## Why HTML and CSS, not images

These are live markup, not exported banners. Copy, the destination link, or the price framing can change without new artwork. Each file's CSS is scoped under a unique wrapper class (`.wowsa-promo-a`, `.wowsa-promo-b`, etc.) specifically so it cannot collide with the Wilcity theme's own styles when pasted into a live widget. Do not remove the wrapper class or the scoping, and do not rename the classes to something shorter or more generic.

## The mark

Slots A, B and C carry the WOWSA association mark, applied as a CSS mask so it can be tinted to whatever color the unit needs, white on the navy units, navy on the cream one, from a single source image:

```
https://www.openwaterswimming.com/wp-content/uploads/2023/07/wowsa-white-logo.png
```

This file is already live in the WordPress media library, confirmed byte-identical to the asset used in the approved mockup. No certification seal appears anywhere in this set, because none of these units are selling a certification right now. Slots D and E carry no mark at all, D because a free course carries no certification claim, E because it repeats slot C's offer in a different treatment.

## Fonts

Georgia and system sans-serif fallbacks are declared but the primary faces are Cormorant Garamond (display) and Karla (body), matching the Learn design system. These are not loaded via `@font-face` in these files, since a WordPress Custom HTML widget should not be adding font requests. If the fonts are not already loaded site-wide, headlines will fall back to Georgia and body text to the system sans stack, which is an acceptable degradation, not a bug to fix here.

## Build notes, from the site audit

- The sidebar already runs `theia-sticky-sidebar`, so slot B and any sidebar unit follow the reader down the article at no extra cost, this is the theme's existing behavior and these files don't need to do anything to get it.
- The sidebar column is `col-md-4`, roughly 300 to 330px usable, so the 300px-wide units fit without scaling.
- Custom HTML widgets are already in use in this sidebar, confirmed by inspecting a live article, so these files drop into an existing widget slot rather than needing a new one.

## If something needs to change

Confirm against the current Notion implementation dashboard before changing colors, fonts, destinations, or the sell-vs-capture strategy: https://app.notion.com/p/3c890374ad9181ad9b18f7b4868774db. That page is the standing source of truth and is dated whenever something changes; a stale copy of this README is not.

American English throughout. No em dashes or en dashes anywhere in the copy.
