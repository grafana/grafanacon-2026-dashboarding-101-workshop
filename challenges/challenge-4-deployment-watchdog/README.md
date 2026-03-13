# Challenge 4: The Deployment Watchdog

**Data source:** Prometheus · **Facilitator:** Alexa

---

## Context

We deploy multiple times a day. When something breaks after a deploy, we need to know fast.

---

## Task 1

You just got paged. A teammate says:

> "We deployed to the payments namespace 20 minutes ago and something feels off. Can you check if pods are restarting?"

Build a dashboard scoped to that namespace showing pod restarts. Use saved queries.

---

## Task 2

Incident resolved. Your team lead asks for a standing post-deploy view:

> "After every deploy I want to see error rate and request rate for the last 30 minutes, for any namespace."

Add a second panel for error rate and set the default time range to last 30 minutes.

---

## Hints

<details>
<summary>Task 1 hints</summary>

- Add a **template variable** for namespace (same as Challenge 1 Task 2)
- Use a **Time series** visualization to see restarts over time, not just the current count
- Look for a saved query related to `container_status_restarts`
- Narrow the time range to the last 30 minutes to focus on post-deploy behaviour

</details>

<details>
<summary>Task 2 hints</summary>

- Add a second panel using a saved query for error rate
- To set the default time range: **Dashboard settings** > **Time options** > set **Default time range** to `now-30m` to `now`
- The namespace variable from Task 1 already makes this work for any namespace

</details>

---

[View solution](./solution.md)
