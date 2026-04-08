# Challenge 1: The Manager's View

**Data source:** Prometheus · **Facilitator:** Alexa

---

## Context

We run services on Kubernetes and leadership wants visibility into platform health.

---

## Task 1

Your Sr. Manager walks over and says:

> "I need to present platform health to the CTO on Friday. Can you give me something visual? Just green or red, is it healthy or not?"

Build a dashboard she can read in 10 seconds. Use stat panels with color-coded thresholds. Use saved queries — no PromQL needed.

---

## Task 2

The CTO saw the dashboard and loved it, but asks:

> "Can I filter this by namespace? I only care about the payments team."

Add a template variable so the dashboard adapts to whoever is viewing it.

---

## Hints

<details>
<summary>Task 1 hints</summary>

- Use the **Stat** visualization — it shows a single value with a color
- Set thresholds: green below a safe value, red above a critical value
- Use **Saved queries** in the query editor to find pre-built metrics
- Keep it to 3 or 4 panels max — one question per panel
- Suggested metrics to look for: pod restart count, error rate, number of running pods

</details>

<details>
<summary>Task 2 hints</summary>

- Go to **Dashboard settings** > **Variables** > **Add variable**
- Use type: **Query**, data source: `grafanacloud-prom`
- Query: `label_values(kube_pod_info, namespace)` to list all namespaces
- Once created, Grafana automatically applies the variable to matching panels

</details>

---

[View solution](./solution.md)
