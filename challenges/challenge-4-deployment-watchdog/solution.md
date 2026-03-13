# Solution: Challenge 4 — The Deployment Watchdog

---

## Task 1: Scoped pod restart view

### Step 1 — Create a namespace variable

1. New dashboard > **Dashboard settings** > **Variables** > **Add variable**
2. Configure:
   - **Type:** Query
   - **Name:** `namespace`
   - **Data source:** `grafanacloud-prom`
   - **Query:** `label_values(kube_pod_info, namespace)`
3. Apply

### Step 2 — Add a pod restarts time series panel

1. Add visualization, select data source: `grafanacloud-prom`
2. Use saved queries or enter:
   ```
   sum by (pod) (increase(kube_pod_container_status_restarts_total{namespace="$namespace"}[5m]))
   ```
3. Visualization: **Time series**
4. Panel title: `Pod Restarts by Pod`
5. This shows restarts over time per pod — spikes after the deploy time will be immediately visible

### Step 3 — Set time range

Change the time range (top right) to `Last 30 minutes` to focus on the post-deploy window.

**Checkpoint:** Can you see a time series with one line per pod? Any spikes indicate restarts.

---

## Task 2: Add error rate + set default time range

### Step 1 — Add an error rate panel

1. Add a new panel
2. Use saved queries or enter:
   ```
   sum(rate(kube_pod_container_status_restarts_total{namespace="$namespace"}[5m]))
   ```
   Or for HTTP error rate if available:
   ```
   sum(rate(container_last_seen{reason=~"OOMKilled|Error", namespace="$namespace"}[5m]))
   ```
3. Visualization: **Time series**
4. Panel title: `Error Rate`

### Step 2 — Set the default time range

1. Open **Dashboard settings** > **Time options**
2. Set **Default time range:**
   - From: `now-30m`
   - To: `now`
3. Save the dashboard

### Result

Anyone who opens this dashboard lands on the last 30 minutes scoped to their namespace. Post-deploy checks go from a manual investigation to a 10-second glance.
