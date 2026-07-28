# Google Maps Reviews Export Skill

## Goal
Extract your Google Maps place reviews from Google Takeout, save them on your computer, and make them easy to read or convert into CSV/Excel later.

## What to export from Google Takeout
In Google Takeout, select:

- **Maps (your places)**

This is the export that contains **place reviews** and starred places. The plain **Maps** export is not the one that usually contains your reviews.

## Expected files
After downloading and unzipping the Takeout archive, look for a folder like:

- `Takeout/Maps (your places)/`

Common files may include:

- `Reviews.json`
- `Saved Places.json`
- other Maps-related JSON files

## How to read the JSON files
JSON files are plain text. You can open them with:

- **Visual Studio Code**
- **Notepad++**
- any text editor
- a web browser for quick viewing

For easier reading, use a JSON formatter or open them in a code editor with pretty-printing.

## How to save your reviews on your computer
1. Download the Google Takeout ZIP.
2. Unzip it into a folder on your computer.
3. Open `Maps (your places)`.
4. Find `Reviews.json`.
5. Copy that file to a safe folder, such as:
   - `Documents/Google Maps Reviews/`
6. Keep the original ZIP as a backup.

## How to convert reviews into CSV
If you want the reviews in a spreadsheet format, use a small script to extract the key fields.

### Example Python script
```python
import json
import csv
from pathlib import Path

input_file = Path("Reviews.json")
output_file = Path("google_maps_reviews.csv")

with input_file.open("r", encoding="utf-8") as f:
    data = json.load(f)

rows = []

# Google Takeout structures can vary, so this script is intentionally flexible.
# It looks for common review-like fields and writes whatever it finds.
for item in data if isinstance(data, list) else data.get("reviews", []):
    rows.append({
        "place_name": item.get("title") or item.get("placeName") or item.get("name", ""),
        "rating": item.get("rating", ""),
        "date": item.get("date") or item.get("timestamp", ""),
        "review_text": item.get("text") or item.get("comment") or item.get("reviewText", ""),
        "url": item.get("url") or item.get("googleMapsUrl", ""),
    })

with output_file.open("w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["place_name", "rating", "date", "review_text", "url"])
    writer.writeheader()
    writer.writerows(rows)

print(f"Saved {len(rows)} rows to {output_file}")
```

## How to reuse this process later
When you want to save your reviews again:

1. Go to **Google Takeout**.
2. Select **Maps (your places)**.
3. Download the export.
4. Unzip it.
5. Find `Reviews.json`.
6. Save it in a dated folder, for example:
   - `Google Maps Reviews/2026-07-28/`
7. Optionally convert it to CSV for easier reading.

## GitHub sharing notes
If you want to share this workflow on GitHub:

- Publish the **instructions** as a README or Markdown guide.
- Avoid uploading your personal review data unless you are sure it is safe to share.
- If you do share sample data, redact names, addresses, and any private details.
- Add a short note that Google Takeout export names and JSON structure may change over time.

## Suggested repository layout
```text
google-maps-reviews/
├── README.md
├── scripts/
│   └── export_reviews.py
└── examples/
    └── Reviews.sample.json
```

## Quick checklist
- [ ] Export **Maps (your places)** from Google Takeout
- [ ] Unzip the archive
- [ ] Find `Reviews.json`
- [ ] Save a backup copy on your computer
- [ ] Open it in a text editor or convert it to CSV
- [ ] Keep the workflow in a Markdown file for reuse

