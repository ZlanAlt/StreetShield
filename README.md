# StreetShield – Smart Pedestrian Safety Navigator

---

## Overview

StreetShield is a safety-first walking navigation platform that prioritizes secure routes over the shortest paths. It evaluates multiple real-world factors such as street lighting, past incident data, congestion levels, weather conditions, and user-submitted reports to recommend safer walking directions. The system combines a mobile application with backend intelligence to deliver real-time safety scoring, route insights, and emergency assistance features.

---

## Technology Stack

Mobile Application
- React Native + Expo

Backend
- Node.js + Express
- MongoDB (stores incident records, lighting data, and user reports)

External Integrations
- TomTom Routing & Traffic APIs
- OpenWeather API
- Gemini for AI-based incident classification
- ElevenLabs for voice-enabled safety assistance
- Cloudinary for image upload and storage
- Twilio for SOS SMS alerts

Deployment
- Backend hosted on Render

---

## Backend Setup

1. Clone the repository

git clone <repo-link>
cd backend

2. Create a `.env` file and add the following environment variables (replace placeholders with actual values)

MONGODB_URI="<your_mongo_string>"
JWT_SECRET="<secret>"

TOMTOM_API_KEY="<key>"
GEMINI_API_KEY="<key>"

CLOUDINARY_CLOUD_NAME="<name>"
CLOUDINARY_API_KEY="<key>"
CLOUDINARY_API_SECRET="<secret>"

TWILIO_ACCOUNT_SID="<sid>"
TWILIO_AUTH_TOKEN="<token>"
TWILIO_FROM_NUMBER="<number>"

EMAIL_USER="<email>"
EMAIL_PASS="<app_password>"
DEFAULT_COUNTRY_CODE=91

3. Install dependencies

npm install

4. Run backend locally

npm run dev

5. Live backend endpoint (optional)

https://safewalk-3sv0.onrender.com/

---

## Expo App Setup

1. Navigate to the mobile app directory

cd native

2. Create a `.env` file with the following values

EXPO_PUBLIC_TOMTOM_API_KEY=<tomtom_key>
EXPO_PUBLIC_ELEVENLABS_AGENT_ID=<agent_id>

3. Install dependencies and start the app

npm install
expo start

---

## Backend Selection Inside App

Location: native/src/api/api.js

For local development:

const YOUR_LOCAL_IP = "YOUR_LOCAL_IPV4_ADDRESS"
const BACKEND_PORT = 5000
const BASE_URL = `http://${YOUR_LOCAL_IP}:${BACKEND_PORT}/api`

To use the deployed backend:

const BASE_URL = "https://safewalk-3sv0.onrender.com/api"
