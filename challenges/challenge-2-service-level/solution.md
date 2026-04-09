# Solution: Challenge 2 — Service Level Monitoring

---

## Task 1: Find a suggested dashboard

### Step 1 — Open the data source

1. Go to **Connections** > **Data Sources**
2. Select your Prometheus data source (format: `grafanacloud-<instance-id>-prom`)

### Step 2 — Browse suggested dashboards

1. Click **Build dashboards** > **From suggestions**
2. In the suggestions modal, search for **"Open Telemetry"**
3. Select **"OpenTelemetry for HTTP services"**
4. Click **View dashboard**

### Step 3 — Map data sources

When prompted, map the data sources:
- **Loki:** `grafanacloud-<instance-id>-logs`
- **Tempo:** `grafanacloud-<instance-id>-traces`

### Step 4 — Select the service

1. Use the `service_name` dashboard variable
2. Select **cartservice**

### Step 5 — Save

If the dashboard is showing data, click **Save dashboard** — you'll modify this version in Task 2.

---

## Task 2: Make latency visible

### Step 1 — Identify latency signals

Locate panels that show:
- **P95 latency**
- **P99 latency**

These are your key indicators of performance issues.

### Step 2 — Make latency visible at a glance

1. Edit the main latency panel
2. Update the title: e.g. `P95 Latency (ms)`
3. Ensure the unit is set to **milliseconds (ms)**

### Step 3 — Apply meaningful thresholds

In your team: latency >= 2 seconds is a problem.

Set thresholds:
- Green: < 1s
- Yellow: 1s – 2s
- Red: >= 2s

### Step 4 — Reorganize the dashboard

1. Move latency panels to the **top** of the dashboard
2. Group related panels together

### Step 5 (optional) — Improve structure

Organize panels into tabs or sections:
- **Overview** — key health signals at the top
- **Latency** — detailed latency breakdown
- **Errors / Logs** — error rates, log panels

### Result

The dashboard now immediately shows whether latency is healthy (green) or problematic (red). No more guessing — a glance tells you if adding plushes to the cart is fast or slow.
