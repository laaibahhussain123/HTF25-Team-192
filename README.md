# HTF25-Team-192

Read me
# Chefly — Instant Recipe Generator (Hackathon Submission)

**Team:** [Chefly]  
**Project type:** No-code prototype (Glide) + Automation (Make.com) + AI  
**Hackathon:** CBIT Hacktober fest 
**Submitted by:** [Laaibah , Rabia , himaja , Haacni]

---

## Live demo
Glide app link (live): see `https://chefly.glide.page` in this repo.

---

## Summary
Chefly helps users turn available ingredients (typed or photographed) into quick, tasty recipes. Users submit ingredients via a simple mobile interface (Glide). Submissions are stored in a Google Sheet that Make.com watches; Make.com sends ingredient data to an AI recipe generator and writes back the suggested recipes. The Glide app displays those recipes with steps, calories, and substitutions.

---

## Why we chose no-code
We prioritized building a **working prototype with a complete data flow** within the hackathon timeframe. Glide allowed us to quickly create a polished mobile UI; Google Sheets served as a shared data store; Make.com handled automation and API calls to the AI. This allowed us to demonstrate UX, logic, and AI integration end-to-end.

---

## Architecture (brief)
1. Glide UI (mobile) — user enters ingredients or uploads an image → writes row to Google Sheet.
2. Google Sheet — acts as the primary data bridge (rows: ingredients, image URL, timestamp).
3. Make.com — watches the sheet; when a new row appears, it:
   - If text ingredients: send to AI recipe API.
   - If image: send image URL to vision model → extract ingredients → send to AI.
   - Writes recipe name, ingredients list, steps, calories back to Google Sheet (or a separate sheet).
4. Glide reads the sheet(s) and shows recipes to the user.

(See `architecture.png` for visual diagram.)

---

## How to run / reproduce
1. Open the Glide app link in `APP_LINK.txt`.
2. Sign-in if required (we use "Public with email" for demo).
3. On **Upload** tab: type ingredients or upload an ingredient photo → Submit.
4. The Google Sheet connected is: `google_sheet_template.csv` (sample format).
5. Make.com scenario (export/screenshot in repo) shows modules used: Google Sheets watch, HTTP request to AI, Google Sheets update.

---

## Files in this repo
- `APP_LINK.txt` — public Glide link
- `google_sheet_template.csv` — sheet headers and sample rows
- `make_scenario_export.json` — Make.com export or a screenshot if JSON not available
- `screenshots/` — in-app screenshots (home, upload form, recipes list, recipe card)
- `architecture.png` — simple diagram of the flow
- `team_roles.txt` — who built what
- `future_work.txt` — planned improvements

---


---

## Future work and scaling
See `future_work.txt` for next steps. Highlights:
- Replace Glide → React Native + backend for full control and code repository
- Deploy a single backend to host AI integration (instead of Make.com)
- Improve image recognition accuracy and provide ingredient confidence scores
- Offline caching & push notifications

---

## Contact
For questions, demos, or to see the full flow live, contact:
- Laaibah laaibahuhussain34@gmail.com
