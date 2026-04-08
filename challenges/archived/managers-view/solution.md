# Solution: Challenge 1 — The Manager's View

---

## Task 1: Platform health at a glance

### Step 1 — Create a new dashboard

1. Go to **Dashboards** > **New** > **New dashboard**
2. Click **Add visualization**

### Step 2 — Add a "Running Pods" stat panel

1. Select data source: `grafanacloud-prom`
2. Open the **Saved queries** tab in the query editor and search for pod status, or use:
   ```
   sum(kube_pod_status_phase{phase="Running"})
   ```
3. Set visualization to **Stat**
4. Panel title: `Running Pods`
5. Set thresholds:
   - Green: base (any value above 0 is healthy)
   - Red: 0 (no running pods is critical)

### Step 3 — Add a "Pod Restarts" stat panel

1. Add a new panel
2. Query (or find via Saved queries):
   ```
   sum(increase(kube_pod_container_status_restarts_total[1h]))
   ```
3. Visualization: **Stat**
4. Panel title: `Pod Restarts (last 1h)`
5. Thresholds:
   - Green: 0
   - Yellow: 5
   - Red: 10

### Step 4 — Add an "Error Rate" stat panel

1. Add a new panel
2. Query (or find via Saved queries):
   ```
   sum(rate(container_last_seen{reason="OOMKilled"}[5m]))
   ```
3. Visualization: **Stat**
4. Panel title: `OOMKilled Containers`
5. Thresholds:
   - Green: 0
   - Red: 1

### Step 5 — Save

1. Click Save
2. Name: `ops / platform-health-executive`
3. Description: `Platform health overview for leadership. Shows running pods, restart count, and critical errors at a glance.`

---

## Task 2: Add a namespace variable

### Step 1 — Create the variable

1. Open **Dashboard settings** (gear icon)
2. Go to **Variables** > **Add variable**
3. Configure:
   - **Type:** Query
   - **Name:** `namespace`
   - **Label:** `Namespace`
   - **Data source:** `grafanacloud-prom`
   - **Query:** `label_values(kube_pod_info, namespace)`
   - **Include All option:** enable this so the manager can see all namespaces at once
4. Click **Apply**

### Step 2 — Use the variable in your queries

Update your panel queries to filter by namespace. For example:

```
sum(kube_pod_status_phase{phase="Running", namespace="$namespace"})
```

Grafana automatically replaces `$namespace` with the selected value from the dropdown.

### Result

The dashboard now has a namespace dropdown at the top. The CTO can select `payments` and see only that team's health.
