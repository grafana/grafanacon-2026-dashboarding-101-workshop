# Solution: Challenge 2 — Team Weather Dashboard

---

## How the dashboard works

> **TODO:** Confirm with Yaëlle — does the starting dashboard already have the custom variable and repeat panel set up, or do attendees build it from scratch?

The dashboard uses a **custom variable** to store city names and their coordinates. A single panel template uses this variable and is set to **repeat** — Grafana automatically generates one panel per city value. Adding a new city is as simple as adding a new value to the variable.

---

## Task 1: Add Barcelona

### Step 1 — Open the variable

1. Open the weather dashboard
2. Go to **Dashboard settings** > **Variables**
3. Find the `city` variable and click to edit it

### Step 2 — Understand the variable format

The variable uses **Custom** type with values in this format:

```
London : latitude=51.5074&longitude=-0.1278
Paris : latitude=48.8566&longitude=2.3522
Berlin : latitude=52.5200&longitude=13.4050
New York : latitude=40.7128&longitude=-74.0060
Tokyo : latitude=35.6762&longitude=139.6503
```

The label (before `:`) is what the viewer sees. The value (after `:`) is what gets injected into the API URL.

### Step 3 — Add Barcelona

Add a new line to the custom values:

```
Barcelona : latitude=41.3851&longitude=2.1734
```

### Step 4 — Apply

Click **Apply** and go back to the dashboard.

Grafana repeats the panel for every value in the variable — Barcelona now appears automatically. No new panel needed.

---

## Task 2: Add precipitation data

### Step 1 — Update the Infinity query URL

The existing temperature panel uses a URL like:

```
https://api.open-meteo.com/v1/forecast?${city}&current_weather=true
```

To add precipitation, update it to:

```
https://api.open-meteo.com/v1/forecast?${city}&current_weather=true&daily=precipitation_sum&timezone=auto
```

### Step 2 — Add a precipitation panel

1. Add a new visualization panel
2. Data source: **Infinity**
3. Type: **JSON**
4. URL:
   ```
   https://api.open-meteo.com/v1/forecast?${city}&daily=precipitation_sum&timezone=auto
   ```
5. In the **Rows/Root** field, navigate to: `daily`
6. Add columns:
   - `time` (string)
   - `precipitation_sum` (number)

### Step 3 — Choose the visualization

**Option A — Today's precipitation as a Stat:**
- Use a transformation to filter to index 0 (today)
- Visualization: **Stat**
- Unit: `mm`
- Panel title: `Precipitation Today (mm)`

**Option B — 7-day forecast as a Bar chart:**
- Keep all 7 days from the API response
- Visualization: **Bar chart**
- X axis: `time`, Y axis: `precipitation_sum`
- Panel title: `Precipitation Forecast (7 days)`

### Step 4 — Enable repeat on the new panel

1. Open the panel edit
2. Go to **Panel options** > **Repeat options**
3. Set **Repeat by variable** to `city`
4. Set **Max per row** to match the temperature panels

Now precipitation panels repeat per city just like the temperature ones.
