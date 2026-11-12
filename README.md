# ie_build

## Driver Route Mapper (`route-mapper.html`)

A single-page tool for mapping your drivers' GPS history. You don't install anything,
and your data stays on your computer: files are read in the browser and never uploaded.

### How to use

1. Download `route-mapper.html` and double-click it to open it in Chrome, Edge or Firefox.
   You need an internet connection for the map tiles.
2. Export the GPS history from your tracking system, for example yesterday's data.
3. Drag the file onto the page, or click **Add GPS files**. You can add several files at once.

Each driver gets their own colored route with a green start dot, a red end square and
numbered stop markers. Click a driver in the **Routes** list to see:

- distance, start/end time, total, moving and stopped time, and max and average speed
- every stop with arrival and departure times and a Google Maps link
- a playback bar that replays the route on the map (60× to 3600× speed)

Click anywhere on a route line to see the time and speed at that point.
**Export stops CSV** saves every stop for the visible routes as a spreadsheet.

### Supported files

| Format | Notes |
| --- | --- |
| CSV / TSV / TXT | The tool finds the latitude, longitude, time, driver/vehicle and speed columns on its own. Date and time can be in separate columns. |
| Excel (.xlsx, .xls) | Every sheet is read. |
| GPX | Tracks, routes and waypoints. |
| KML | Google Earth tracks (`gx:Track`), lines and timestamped points. |
| GeoJSON / JSON | Point features, LineStrings, or a plain list of records. |

You can also paste coordinates (`lat, lon` per line, or CSV with a header row).

If a file's columns aren't picked up correctly, open **Files → Columns used** and choose
the right ones. The map updates right away.

### Settings

- **Stop = parked at least N minutes**: minimum dwell time to count as a stop (default 5).
- **Stop radius**: how far the vehicle can drift and still count as parked (default 250 ft).
- **Split each driver's route by day**: useful when a file covers several days.
- **Ignore GPS jumps**: drops points that would need an impossible speed (over about 155 mph).

`samples/sample-gps-export.csv` is a made-up two-driver file you can use to try the tool.
