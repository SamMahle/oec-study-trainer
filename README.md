# OEC Study Trainer

A lightweight, study tool for **Outdoor Emergency Care (OEC)** prep. It runs as a single static HTML file and supports custom JSON decks. Missed items go back in the queue (“see it again”), known items move to the Known bin.

> **Why this exists:** Fast, offline-friendly drilling with concise, instructor-style explanations tuned for OEC/EMS topics (hypothermia, ICS, legal, airway/oxygen, shock, neuro, and acronym expansions).

---

## Features

- **Shepard-style flow:** `See it again` for misses, `I knew it` for hits
- **Learn / Exam modes:** Peek in Learn; hide until answered in Exam
- **Import / Export:** Load your own JSON; `Export All` writes a cleaned deck
- **Light / Dark themes:** Toggle in the header; persisted in localStorage
- **Local progress:** Saved in your browser (no server needed)
- **Acronym expansions:** AVPU/APVU, SAMPLE, OPQRST, PERRL/A, DCAP-BTLS, ABCDE, etc.

---

## Quick Start (Local)

1) **Files in this repo**
   - `index.html` — the app (single static page)
   - `decks/oec_deck_instructor_v6_acronyms.json` — starter deck with improved explanations

2) **Open in VS Code** → *File → Open Folder…* → select this repo.

3) **Run it** (pick one)
   - **Live Server** (VS Code extension): Right-click `index.html` → **Open with Live Server**
     Browser opens at something like `http://127.0.0.1:5500/`
   - **Python tiny server**:
     ```bash
     # macOS / Linux
     python3 -m http.server 8000

     # Windows (PowerShell)
     py -m http.server 8000
     ```
     Open: http://localhost:8000

4) **Use it**
   - Import a deck from the left sidebar (**Replace deck on import** if you want to overwrite)
   - Click **Start / Continue** and drill
   - Missed? use **See it again**. Nailed it? **I knew it**
   - **Export All** to save an upgraded deck JSON (with cleaner explanations)

> Opening `index.html` directly with `file://` sometimes limits browser features—using a local server is recommended.

---

## Deck Format (JSON)

Top-level: **array** of card objects.

### Multiple Choice
```json
{
  "q": "A patellar fracture affects which part of the body?",
  "choices": ["The tibia", "The hip", "The elbow", "The knee"],
  "correct": 3,
  "type": "mc",
  "explain": "Remember: the patella is the kneecap, so a patellar fracture is an injury to the knee.",
  "category": "Chapter 6 Test Bank"
}