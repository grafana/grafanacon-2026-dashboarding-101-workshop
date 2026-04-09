# Challenge 2: Service Level Monitoring

**Data source:** Prometheus · **Facilitator:** Alexa

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

1. Use the same approach as in Section 2 to find suggested dashboards
2. Search for **`OpenTelemetry for HTTP Services`** — the search is case sensitive
3. When loading the dashboard, you will be asked to map more than one data source — check what is available in your instance

</details>

<details>
<summary>Task 2 hints</summary>

1. Which latency percentile is most useful for catching slow outliers? — [Not sure what percentiles mean?](https://igor.io/latency/#percentiles)
2. How can you make the 2-second threshold immediately visible without having to read the numbers?
3. What should be the first thing someone sees when they open this dashboard?

</details>

---

[View solution](./solution.md)
