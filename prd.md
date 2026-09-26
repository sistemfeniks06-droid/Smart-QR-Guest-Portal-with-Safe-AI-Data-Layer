---
doc: prd
status: approved
---

# Product Requirements Document (PRD): Smart QR Guest Portal with Safe AI Data Layer

## Problem Statement & Context
Hospitality venues frequently face two major pain points:
1. Physical table QR codes often point to slow, static PDFs or unmanaged links that cannot be dynamically updated without expensive reprint costs.
2. Dissatisfied guests leave 1-star public Google reviews before staff can resolve their issue, while satisfied guests rarely take the initiative to leave positive ratings.

This project delivers a high-speed, mobile-optimized guest portal with dual-channel sentiment review routing and an embedded AI-discoverable JSON-LD metadata layer.

## User Personas & Flows
- **Guest Persona (Diner/Visitor):**
  - Scans physical tabletop QR code with a smartphone camera.
  - Lands on an ultra-lightweight (<500ms) welcome portal.
  - Taps once to copy/connect to guest Wi-Fi.
  - Browses the venue's digital menu cards smoothly.
  - Taps a rating button:
    - If 4 or 5 stars: Guided to the public Google Maps review URL.
    - If 1 to 3 stars: Directed to a private WhatsApp direct message with the on-duty manager for immediate resolution.
- **Venue Manager Persona:**
  - Protects the venue's public Google rating.
  - Intercepts customer dissatisfaction internally in real time.
  - Exposes venue schema data (hours, location, menu) cleanly to search engines and AI crawlers.

## What We're Building (POC Requirements)
1. **Header & Venue Identity:** Venue name, branding, operating status, and quick-contact info.
2. **One-Tap Wi-Fi Module:** Direct display of SSID with a 1-tap "Copy Password" / connect trigger.
3. **Interactive Menu Viewer:** Clean, fast-loading modal/accordion showing categorized food and beverage items with prices.
4. **Sentiment-Based Feedback Router:**
   - 5-star rating flow -> links to Google Business profile review URL.
   - Low-star rating flow -> generates a pre-formatted WhatsApp message for instant manager intervention.
5. **Safe AI Data Layer (JSON-LD):** Embedded Schema.org `Restaurant` / `LocalBusiness` structured data containing geo coordinates, operating hours, and service metadata.

## Look and Feel
- Minimalist Scandinavian hospitality design.
- High contrast, mobile-first cards with neutral and dark accents.
- Tactile feedback on tap, zero unnecessary popups or tracking banners.

## Product Decisions & Tradeoffs
- **Vanilla Web Stack vs. Frameworks:** Built with standard HTML5, CSS3, and JavaScript to guarantee instant mobile load times and eliminate build-pipeline failures.
- **Direct Links vs. Database Backend:** Uses direct URL routing protocols (`https://`, `wa.me/`, `wifi:`) to ensure 100% uptime with zero server maintenance costs.

## Deferred From POC
- Backend order checkout and online card payment gateway.
- Multi-language auto-translation toggle.

## Non-Goals
- User account creation, authentication, or profile tracking.
- Native mobile app distribution via App Store or Google Play.

## Open Questions
- None blocking implementation. Proceed to technical spec.
