# Challenge 2: Service Level Monitoring

**Data source:** Prometheus · **Facilitator:** Alexa

**Submit your answer:** [Via this form](https://docs.google.com/forms/d/e/1FAIpQLSfoaIbrcuTWsPGgfZOuKOv8wm4wB8gSAtwTKm9WUuq8S8OMqw/viewform?usp=dialog)

---

## Context

You've already set up a dashboard to monitor your Kubernetes infrastructure (pods, CPU, memory). However, your team is now getting reports that:

> "Adding plushes to the cart is slow"

Infrastructure looks healthy, but you don't have visibility into how your services behave at the application level.

---

## Task 1

Your services are instrumented with OpenTelemetry.

> Use **Suggested Dashboards** to find a dashboard that helps you monitor your HTTP services.

---

## Task 2

You found a dashboard. Now make it actually show the latency problem.

In your team, any request that takes **2 seconds or more** is considered a latency problem.

> Make latency issues visible at a glance and reorganize the dashboard for your needs.

---

## Hints

<details>
<summary>Task 1 hints</summary>

1. Go to the **Data sources** page (Connections > Data Sources)
2. Select your Prometheus data source (`grafanacloud-<instance-id>-prom`)
3. Click **Build dashboards** > **From suggestions**
4. In the suggestions modal, search for **"Open Telemetry"**
5. Look for a dashboard related to HTTP services: **"OpenTelemetry for HTTP services"**
6. Click **View dashboard**
7. When prompted, map the data sources:
   - Loki: `grafanacloud-<instance-id>-logs`
   - Tempo: `grafanacloud-<instance-id>-traces`
8. Use the `service_name` variable to select **cartservice**
9. If the dashboard is showing data, **save it** — you'll be modifying this version

</details>

<details>
<summary>Task 2 hints</summary>

- Identify panels that show **P95 latency** and **P99 latency** — these are your key performance indicators
- Edit the main latency panel: update the title (e.g. `P95 Latency (ms)`) and ensure the unit is set to milliseconds
- Set **thresholds** to make problems visible at a glance:
  - Green: < 1s
  - Yellow: 1s – 2s
  - Red: >= 2s
- **Reorganize** the dashboard: move latency panels to the top, group related panels together
- Optionally organize panels into **tabs** (e.g. Overview, Latency, Errors / Logs)

</details>

---

[View solution](./solution.md)
