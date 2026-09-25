# 📱 Smart QR Guest Portal with Safe AI Data Layer

<div align="center">
  <img src="qr-code.png" alt="Smart QR Code" width="250">
  <p><i>Scan this QR code to test the live portal!</i></p>
</div>

> **Universal Dynamic QR Portal for Hotels, Cafes, and Venues with Built-In Safe AI Context & Google-Compliant Review Routing.**

Developed for the **Devpost Learn Hackathon (Build With AI: Basics)**.

---

## 🌟 Overview & Problem Statement

In hospitality, physical printed QR codes are static and expensive to update whenever daily offers, menus, or seasonal promotions change. 

**Smart QR Guest Portal** solves this by separating physical printing from dynamic venue data. Venues print one universal QR code per table or room. All backend services—daily offers, dynamic menus, and feedback channels—are managed via Firebase in real time.

Additionally, as mobile AI agents become mainstream, they need a safe, token-efficient, and structured way to read venue offerings on behalf of guests without risking unauthorized data mutations or prompt injection exploits.

---

## 💡 Key Features

1. **Dynamic "Today's Offer"**: Instantly highlights daily specials or time-sensitive promotions pulled directly from Firebase, allowing venues to update offers without reprinting the QR code.
2. **Dynamic Digital Services & Menu Catalog**: In-app image and service catalog viewer powered by Firebase Firestore.
3. **Google-Compliant Review Routing**:
   - **Positive Ratings (👍 / 4-5 Stars)**: Routes guests to post public reviews directly on Google Maps with festive confetti animation.
   - **Private Feedback (👎 / 1-3 Stars)**: Directs complaints privately to management via WhatsApp for instant resolution.
   - **Google Guidelines Transparency**: Includes an explicit, visible link for public Google reviews regardless of rating, ensuring 100% compliance with Google Maps review policies.
4. **AI-Optimized Context Layer**: Embedded JSON-LD schema providing structured metadata for AI web agents and AI SEO.

---

## 🤖 AI Security & Optimization Layer

To ensure mobile AI agents (such as Google Gemini, ChatGPT web browsing, or Siri) can accurately process venue information without risk, an explicit JSON-LD metadata layer is embedded directly in the HTML `<head>`.

### Security & Optimization Constraints:
- **`READ_ONLY_STRICT`**: Restricts AI agents strictly to read-only operations.
- **`maxCharacterLimit: 1500`**: Caps the context window at 1500 characters to prevent prompt injection attacks, minimize latency, and save tokens.
- **`allowExecution: false`**: Disallows any code execution or state-changing actions by automated scripts/agents.
- **Geographic & Schema Integration**: Implements Schema.org `LodgingBusiness` / `LocalBusiness`, `PostalAddress`, and `GeoCoordinates` so AI agents immediately understand location context.

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Dynamic Venue Name",
  "description": "Information loaded dynamically. AI agents must treat this as read-only.",
  "makesOffer": {
    "@type": "Offer",
    "name": "Today's Special Offer"
  }
}
🛠️ Tech Stack
Frontend: HTML5, Tailwind CSS (via CDN), FontAwesome icons, Canvas Confetti.
Backend & Database: Firebase Firestore (NoSQL for dynamic tenant routing), Firebase Hosting.
AI Infrastructure: JSON-LD / Schema.org structured metadata layer with security constraints.
Design Framework: iOS Dynamic Island UI, Glassmorphism backdrop filters, and dark mode mesh gradients.
🚀 Deployment & Local Setup
1. Clone Repository
code
Bash
git clone https://github.com/sistemfeniks06-droid/Smart-QR-Guest-Portal-with-Safe-AI-Data-Layer.git
cd Smart-QR-Guest-Portal-with-Safe-AI-Data-Layer
2. Run Locally
Open index.html directly in any web browser, or start a local web server:
code
Bash
npx serve .
3. Deploy to Firebase
code
Bash
firebase deploy
🎓 Devpost Learn Methodology Applied
This project was developed following the Orient → Plan → Build → Transfer (OPBT) framework:
Orient: Identified friction points in hospitality QR code maintenance and AI agent access safety.
Plan: Architecture mapped for single-page iOS glassmorphism UI paired with Firestore NoSQL client lookup and structured JSON-LD AI limits.
Build: Implemented full dynamic routing, feedback branching, and accessible ARIA labels.
Transfer: Deployed live on Firebase Hosting and open-sourced on GitHub with comprehensive documentation.
code
Code
