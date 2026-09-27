# EcoCollect — Waste Collection Request Web App

**EcoCollect** is a lightweight, responsive waste collection request prototype built with **React** and **Tailwind CSS**. It uses browser **localStorage** for instant, zero-backend data persistence.

---

## 🚀 Quick Start

No installation, build step, or Node.js required! 

1. **Directly open** [`index.html`](file:///c:/Users/Noora%20Excellence/Documents/dhiraj%20hackathon/index.html) in any browser (Chrome, Edge, Firefox, Brave, Safari).
2. Alternatively, double-click [`start-app.bat`](file:///c:/Users/Noora%20Excellence/Documents/dhiraj%20hackathon/start-app.bat).

## 🎨 Visual Aesthetics & Micro-Animations

- **Glassmorphism Design**: Frosted glass panels (`backdrop-blur-xl bg-white/88 border border-white/60`) and subtle multi-point radial gradient background mesh.
- **Micro-Animations & Keyframes**:
  - `animate-fadeInUp`: Smooth staggered page-level entrance on tab switches.
  - `animate-popIn`: Bouncy entrance for modals and dialogs.
  - `animate-float`: Ambient slow floating orbs and icons.
  - `btn-shimmer`: Light sweep shine effect on primary action buttons.
  - `animate-celebrate`: Confetti celebration overlay with animated floating eco-badges upon verified bookings and OTP verification.
- **Card Hover Physics**: 3D lift with category-specific colored glowing drop shadows (blue, amber, emerald, purple, teal).
- **Modern Typography**: Google Fonts (`Plus Jakarta Sans` and `Inter`) for clean, crisp readability.

---

## 🌟 Features Overview

### 👤 User Side (4 Pages)

1. **Home Page**
   - **App Name**: "EcoCollect"
   - **User Welcome & Verification Status**: Displays current user's authenticated mobile status, eco-points, and saved addresses shortcut.
   - **Call-to-Action Buttons**:
     - "Request Waste Pickup" (navigates to request form)
     - "View My Requests" (navigates to submitted pickups)
     - "Manage Profile & Addresses" (navigates to profile)
     - "Schedule Waste Pickup Now" (quick workflow CTA)
     - "Frequently Asked Questions" (opens interactive modal)
   - **Interactive Category Showcase**:
     - All 5 category cards (`Plastic`, `Paper`, `Organic`, `E-Waste`, `Other`) are fully clickable buttons that immediately open the request form with that category pre-selected.

2. **Request Pickup Page (with Strong Validations & Auth)**
   - **Mobile Number Authentication**:
     - Validates 10-digit mobile number format (`^[0-9]{10}$`).
     - Real OTP verification flow with 4-digit verification code, countdown timer, auto-fill demo button, and "✓ Mobile Authenticated" badge.
     - Automatically prompts OTP verification modal if the mobile number is unverified upon submission.
   - **Doorstep Address Validation & Geolocation**:
     - Structured address fields: House/Flat No, Street/Road, Landmark (optional), City, State, and PIN code.
     - Strict format checks: PIN code must be 5 or 6 digits, City must contain valid letters, Street & Flat must meet minimum length criteria.
     - **Detect GPS Button**: Uses HTML5 Geolocation API with realistic fallback to detect and authenticate current physical coordinates.
     - **Saved Addresses Dropdown**: 1-click auto-fill from user's saved Profile addresses (Home, Office, etc.).
   - **Interactive Buttons & Controls**:
     - **Auto-Fill Demo**: Fills realistic verified sample test data with 1 click for instant testing.
     - **Category Quick Selector Pills**: 1-click pill buttons for Plastic, Paper, Organic, E-Waste, Other.
     - **Cancel Button**: Returns safely to the home screen.
     - **Submit Pickup Request**: Validates all fields, requires mobile authentication, persists to `localStorage`, increments user Eco-Points (+50 pts), and navigates to "My Requests".

3. **My Requests Page**
   - **Filter Buttons**: `All`, `Pending`, `Scheduled`, `Completed`, `Cancelled` with live count badges.
   - **Schedule New Pickup Button**: Quick CTA to book another pickup.
   - **Card-Level Action Buttons**:
     - **Track & Details (Eye icon)**: Opens a live 4-step progress tracker modal with full address, contact details, and printable collection slip.
     - **Cancel Pickup (Rose button)**: Allows users to cancel pending or scheduled pickups with live state update.
     - **Book Again (Sparkles button)**: Clones completed/cancelled pickup details to re-book in 1 click.
     - **Delete (Trash button)**: Permanently removes completed/cancelled requests from `localStorage`.

4. **User Profile Page (`Profile`)**
   - **Personal Info Card**: Name, email, member since date, and authenticated phone badge with "Edit Profile" form.
   - **Mobile Authentication Manager**: Shows current verified mobile number with an option to trigger OTP re-verification.
   - **Eco-Impact Scoreboard**:
     - Total Recycled Waste (KG)
     - Eco-Reward Credits (Pts)
     - Completed Pickups count
     - Carbon Footprint Saved (KG CO₂)
   - **Saved Addresses Manager**:
     - View, add, edit, or delete saved addresses.
     - Mark default address for instant 1-click checkout.
     - Add New Address modal with full validation.

---

### 🛡️ Admin Side (1 Dashboard Page)

- **Admin Dashboard Page**
  - **Clickable Metric Filter Cards**:
    - Clicking `Total Requests`, `Pending`, `Scheduled`, or `Completed` instantly filters the table to that subset.
  - **Top Toolbar Buttons**:
    - **New Pickup**: Creates a pickup request directly from Admin.
    - **Export CSV**: Triggers a direct browser download of all pickup records as a formatted `.csv` spreadsheet.
    - **Reset Demo**: Restores original sample records anytime.
    - **Purge Done**: Cleans up archived completed/cancelled records.
  - **Search & Filter**: Search with instant clear (`✕`) button; filter by status tab.
  - **Table Row Action Buttons**:
    - **View Details (Eye icon)**: Opens the full tracking & printable ticket modal.
    - **Quick "Schedule" Button**: One-click approval for Pending requests.
    - **Quick "Complete" Button**: One-click completion for Scheduled requests.
    - **Status Dropdown**: Live status update with real-time `localStorage` sync.
    - **Delete (Trash button)**: Removes any row with a confirmation check.

---

## 📁 Project Structure

```
dhiraj hackathon/
├── index.html        # Complete React + Tailwind single-page application
├── start-app.bat     # One-click launcher for Windows
├── README.md         # Documentation and instructions
└── vendor/           # Offline library assets (React, ReactDOM, Babel, Tailwind)
```
