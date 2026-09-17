EPL DEADHEAD FINDER — JOB 166 PROTOTYPE

Purpose
- Standalone research prototype only.
- Does NOT modify Engineer Pay Log production or Supabase.
- Uses Job 166 report/final-arrival/release times from the current GO 202 Crew Book.
- Uses public LIRR GTFS only. E Stops, equipment/Q stops and WSY intercepts are intentionally not included yet.

Quick test
1. Upload index.html to a new GitHub repository (or upload both files).
2. Enable GitHub Pages.
3. Open the page.
4. The page immediately has a Babylon demo dataset.
5. It also tries to load the current public LIRR GTFS from:
   https://rrgtfsfeeds.s3.amazonaws.com/gtfslirr.zip
6. Once GTFS loads, the Preferred deadhead station dropdown expands to all GTFS stops.

Connection rules in this prototype
- 5+ minutes = legal transfer.
- 4 minutes = short / possible, but not legally protected.
- 1–3 minutes = tight / possible.
- Going home starts the transfer clock at the scheduled arrival of Job 166's final working train, not the printed release time.

Job 166 seed
Weekday pattern:
- Report GCM 3:44 PM
- Final train 275 arrives GCM 12:32 AM
- Release 12:37 AM
Weekend pattern:
- Report GCM 3:51 PM
- Final train 6275 arrives GCM 12:35 AM
- Release 12:40 AM
Relief days: Wednesday–Thursday

Babylon fallback demo routes
Weekday:
- 163 Babylon 2:16 PM -> Jamaica 2:59 PM
- 1299 Jamaica 3:13 PM -> GCM 3:35 PM
- 2702 GCM 12:37 AM -> Jamaica 12:58 AM
- 2 Jamaica 1:05 AM -> Babylon 1:42 AM
Weekend:
- 6159 Babylon 2:11 PM -> Jamaica 2:55 PM
- 6255 Jamaica 3:07 PM -> GCM 3:27 PM
- 8702 GCM 12:37 AM -> Jamaica 12:57 AM
- 6102 Jamaica 1:02 AM -> Babylon 1:54 AM

If browser CORS blocks the MTA zip, the page exposes a local GTFS zip picker. Babylon demo mode still remains usable.
