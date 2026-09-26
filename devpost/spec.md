---
doc: spec
status: approved
---

# Smart QR Guest Portal with Safe AI Data Layer — Technical Spec

## How This Works, In Plain Language
The system is an ultra-fast, zero-friction mobile web application accessed via tabletop QR codes. When a guest scans the code, their phone browser loads index.html instantly without installing any app. The guest can copy Wi-Fi credentials with one tap, browse the menu, and leave sentiment-driven feedback (4-5 stars route to Google Reviews; 1-3 stars route to manager WhatsApp). Schema.org JSON-LD microdata provides machine-readable venue details to AI search agents.

## The Core Journey Through the System
1. Guest scans QR code -> Browser opens index.html.
2. Guest taps Wi-Fi -> Password copies to clipboard with visual confirmation.
3. Guest taps Menu -> Modal/view opens with categorized food and drinks.
4. Guest rates experience:
   - High score (4-5 stars) -> Opens Google Maps Reviews page.
   - Low score (1-3 stars) -> Opens pre-filled WhatsApp chat to manager.
5. Search engines / AI crawlers -> Read embedded JSON-LD metadata directly from head.

## Stack
- Frontend: HTML5, modern CSS3, Vanilla JavaScript (ES6+).
- Metadata: Schema.org / JSON-LD for local business SEO.
- External Integrations: Google Reviews URL, WhatsApp Click-to-Chat (wa.me).
- Hosting: Static web hosting (Cloud Shell preview, GitHub Pages, Firebase Hosting).

## Where It Runs and How Someone Tries It
- Any modern mobile or desktop browser (Chrome, Safari, Firefox).
- Local preview via terminal: python3 -m http.server 8080.
- Hackathon submission deliverables: Public GitHub repo, devpost/ planning artifacts, and 1-3 min video screen demo.

## Look and Feel
- Clean, modern Scandinavian hospitality palette (dark slate background, high contrast cards, tactile buttons).
- Native system fonts for zero latency loading.

## Components
- Header: Venue name, operating status, and quick contact.
- Wi-Fi Module: SSID display with one-tap clipboard copy.
- Digital Menu: Categorized food and drink accordion/modal.
- Sentiment Feedback Router: Interactive star rating routing logic.
- Safe AI Data Layer: Embedded JSON-LD structured data block.

## Data Model
Static configuration object in JavaScript and Schema.org Restaurant JSON-LD in HTML head.

## Important Failure Modes
- Clipboard blocked: Displays clear fallback text for manual Wi-Fi copy.
- Slow network: Entire page is under 20KB for near-instant rendering.

## What Was Simplified and Why
- Pure static HTML/CSS/JS used instead of complex frontend frameworks (React/Vue) for instant mobile loading and zero build-step errors.
