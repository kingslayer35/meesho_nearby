---
version: alpha
colors:
  primary: "#E20750"
  heading: "#231A5C"
  text: "#2B2533"
  muted: "#696475"
  canvas: "#F6F6F8"
  surface: "#FFFFFF"
  border: "#E8E6EC"
typography:
  ui:
    fontFamily: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif"
rounded:
  control: "8px"
  panel: "12px"
spacing:
  unit: "8px"
components:
  button:
    padding: "10px 16px"
---

# Meesho Nearby design

## Overview

A local shopping prototype for the Meesho DICE 3.0 concept. Help shoppers see the item, its current price, how far away it is, and what they are reserving. The supplied presentation establishes navy and pink. Keep the catalog familiar and the discount explanation secondary.

## Colors

`styles.css` is the canonical runtime token owner. This document mirrors its shared palette. `nearby.css` consumes those tokens for catalog-specific components. Runtime values are not generated from this file.

| Role | Runtime token | Value |
| --- | --- | --- |
| Primary action | `--acc` | `#E20750` |
| Heading and focus | `--navy`, `--focus` | `#231A5C` |
| Text | `--ink` | `#2B2533` |
| Secondary text | `--muted` | `#696475` |
| Canvas | `--bg` | `#F6F6F8` |
| Surface | `--surface` | `#FFFFFF` |
| Dividers | `--line` | `#E8E6EC` |

Use pink for reservation actions and current discounts. Success styling accompanies a visible reservation label. Expired offers retain readable content and disabled actions.

## Typography

The system sans serif stack in `--font-ui` serves headings, body, prices and controls. Prices carry the strongest hierarchy within a product card. Avoid remote fonts, decorative display faces and excessive uppercase copy.

## Layout

At desktop widths a compact price guide sits beside the catalog. The catalog is first in DOM order. At 800px and below the guide stacks below the products, so shoppers see the actual deals before the demo explanation. Products use three columns at wide widths, two below 1100px, and one below 350px. Keep product photographs inside a reserved image area; preserve their original proportions with `object-fit: contain`.

## Elevation & Depth

Flat white panels, thin borders and a quiet neutral canvas. Product photography carries the character. Avoid gradients, glass, floating decorations and oversized promotional banners.

## Shapes

Controls use `--radius-control` (8px); panels use `--radius-panel` (12px). Discount labels use a small 4px radius. No pill-shaped action buttons.

## Components

The existing `index.html` data and handlers remain the behavior authority. Preserve 10%, 17.5%, 25% discount tiers, 24/48/72-hour boundaries, 3/5km filtering, reservation state and the expired offer cutoff. The clock is an explicitly labelled demo control, not an actual inventory timer.

Native select ownership: the `#km` select keeps browser/OS-owned popup geometry and keyboard behavior. That platform behavior is accepted for this prototype. Scrollbar owner: global `styles.css`. Focus owner: the global `:focus-visible` rule. Product images are stored locally; sources are recorded in `assets/SOURCES.md`.

This single-screen prototype keeps its small canonical UI map here alongside the visual guidance.

| Capability | Canonical owner | Source of truth | Allowed variants | Verification |
| --- | --- | --- | --- | --- |
| Select/Listbox | Native `#km` select in index.html | Existing 3/5km filter and platform keyboard behavior | Native | Open popup, keyboard, filtering in browser |
| Scrollbar | Global rules in styles.css | Shared CSS tokens | Global | Computed styles and narrow page reflow |

## Do's and Don'ts

- Put the actual product and price before explanatory copy.
- Disclose that products were previously undelivered and are unopened.
- Keep the original customer's identity private.
- Keep the discount clock and both distance choices available.
- Add no inventory claims, reviews, extra controls, payment integration or business transitions.
- Keep all three prototypes on the same visual palette and component foundation.
