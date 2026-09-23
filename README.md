# Vidrow creatives on Bachatt

Static page: https://bachatt-app.github.io/vidrow-creatives/

Same rows as the **User data** tab of Vidrow's "Bachatt Delivery Tracker" sheet, plus an opening frame,
language, live-since date and funnel state. Only Vidrow creatives with Meta spend are listed.

Generated on Sameer's Mac from `Desktop/Meta Game/Creative Planning Fix/Meta Transfer to Campaign Naming/`:

```bash
python vidrow_user_data.py          # pull from Argus prod (tunnel on :5436) → vidrow_user_data_pull.csv; add `go` to refresh the sheet tab
python build_vidrow_frames.py       # thumbnails for new codes → vidrow_site/frames/ (resumable)
python build_vidrow_page.py         # → vidrow_site/index.html
git -C vidrow_site add -A && git -C vidrow_site commit -m "data refresh" && git -C vidrow_site push
```

Definitions: cost per purchase = spend ÷ Meta purchases for that video; SIP users = each matched user's
first funded schedule, split by frequency; average SIP amount = per-frequency average of that first schedule.
