# Stretch: Set up an Alert

**Data source:** Prometheus · **Facilitator:** Alexa

---

## Context

You built a Kubernetes health dashboard in Section 2. Now take it one step further: instead of checking the dashboard manually, let Grafana alert you automatically when something goes wrong.

---

## Task

Set up an alert on a panel that fires when an anomaly is detected — for example, when pod restarts exceed a threshold.

---

## Steps

### 1. Create an alert from a panel

1. Open your Kubernetes dashboard (from Section 2 or Challenge 2)
2. Open a panel that tracks a meaningful metric (e.g. pod restarts, error rate)
3. Go to the **Alert** tab
4. Click **New alert rule**

Grafana pre-fills the query from the panel — you don't need to write it again.

### 2. Set the alert condition

Define what an anomaly looks like:

- **Condition:** `IS ABOVE` a threshold (e.g., `0` — any restart is worth knowing about)
- You can preview the condition against historical data before saving

### 3. Set up routing

- **Folder:** Select your personal folder (`@yourname`)
- **Evaluation group:** Create a new group (e.g., `workshop-alerts`)
- **Contact point:** Use the default or any configured one

### 4. Configure alert messaging

- **Summary:** `Pod restarts detected in {{ $labels.namespace }}`
- **Description:** Include a link back to the dashboard for context

---

## Result

When pods restart in the monitored namespace, Grafana fires the alert automatically. No more manual dashboard checks.

---

## Hints

<details>
<summary>Threshold tips</summary>

- Setting the threshold to `0` means any restart triggers the alert
- For a less noisy alert, try `IS ABOVE 2` (more than 2 restarts in the window)
- Use the preview to see how often it would have fired in the last hour

</details>

<details>
<summary>Evaluation interval</summary>

- The evaluation group controls how often the alert checks (e.g., every 1 minute)
- For a post-deploy watchdog, every 1 minute makes sense
- A longer interval (5 min) reduces noise but delays detection

</details>
