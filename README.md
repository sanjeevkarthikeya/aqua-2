# AQUA INTELLIGENCE
### Predictive Water Infrastructure Management Platform

AQUA INTELLIGENCE is an enterprise-grade civic technology platform designed for citizens, resident welfare associations (RWAs), commercial establishments, municipal field engineers, and government administrators. It connects citizen reports with proactive municipal infrastructure management and AI-powered predictive risk intelligence.

---

## 1. Core Architecture & Modules

- **Public Citizen Portal (`/`, `/citizen-login`, `/report`)**: Allows citizens and local residents to log waterlogging, pipeline leaks, and water quality concerns with camera capture, device upload, and automatic GPS coordinate stamping.
- **Interactive All-India & Regional GIS Map (`/public-map`)**: Visualizes aggregated ward-level hotspots and problem markers across Karnataka (Bengaluru, Mysuru, Mangaluru, Hubballi, Belagavi, etc.) with strict PII isolation.
- **Government Admin Command Center (`/admin`)**: Provides central municipal oversight, underground GIS asset mapping (pipelines, valves, manholes), AI complaint clustering, risk scoring, and work order assignment.
- **Field Worker Portal (`/worker`)**: Mobile-first technician desk for inspecting assigned work orders, recording true GPS fault points, and uploading repair verification proof.
- **Multilingual Support**: Real-time site-wide translation in English, Telugu (తెలుగు), Hindi (हिन्दी), and Kannada (కన్నడ/ಕನ್ನಡ).

---

## 2. Environment Variables

Copy `.env.example` to `.env` (never commit `.env` or secrets):

```bash
cp .env.example .env
```

Required variables:
- `GEMINI_API_KEY`: Server-side API key for Gemini AI text and image triage.
- `APP_URL`: Hosting service URL for self-referential links and OAuth callbacks.
- `VITE_GOOGLE_MAPS_API_KEY`: Google Maps Platform API key for map rendering and geocoding.

---

## 3. Getting Started & Development

### Prerequisites
- Node.js (v18+)
- npm or pnpm

### Installation & Execution
```bash
# Install dependencies
npm install

# Run development server (Express + Vite middleware on port 3000)
npm run dev
```

### Build & Production
```bash
# Build production bundle
npm run build

# Start production server
npm start
```

---

## 4. Testing & Quality Assurance

```bash
# Run type check
npm run lint
```

---

## 5. Security & Privacy Safeguards

- **Attribute-Based Access Control (ABAC)**: Protected routes (`/admin`, `/worker`, `/community`, `/owner/dashboard`) enforce Firebase Authentication and verified roles.
- **PII Isolation**: Citizen contact details, precise GPS coordinates, and internal technician logs are strictly shielded or aggregated on public GIS maps.
- **Server-Side AI Proxy**: Gemini API calls are routed securely through backend Express endpoints (`/api/*`), preventing API key exposure on the client.
