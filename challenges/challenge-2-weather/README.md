# Challenge 2: Team Weather Dashboard

**Data source:** Infinity · **Facilitator:** Yaëlle

**Starting dashboard:** [Open in Grafana](https://afcb45.grafana.net/goto/affwx0cxe6ebka?orgId=stacks-1523323)
_(Make a copy before editing — Save > Save as Copy > select your folder)_

---

## Context

My team is distributed in 5 different places in the world.
For fun we have a weather dashboard so we always know how warm it is where everybody is.

---

## Task 1

A new team member joins from Barcelona, Spain:

> "I want to add that location's information to the dashboard."

---

## Task 2

We have temperature and that's been a good conversation starter, but now we noticed we talk about rain (and snow) a lot:

> "I would like to see data about precipitation too."

---

## Useful information

- Weather API: `https://api.open-meteo.com/`
- Documentation: `https://open-meteo.com/en/docs`
- The API is free and requires no authentication

### Example API call

```
https://api.open-meteo.com/v1/forecast?latitude=48.8566&longitude=2.3522&current_weather=true
```

Returns current temperature, wind speed and weather code for Paris.

### Adding precipitation

```
https://api.open-meteo.com/v1/forecast?latitude=48.8566&longitude=2.3522&current_weather=true&daily=precipitation_sum&timezone=auto
```

---

## Hints

<details>
<summary>Task 1 hints</summary>

- Barcelona coordinates: `latitude=41.3851`, `longitude=2.1734`
- The dashboard uses a **custom variable** with city names and coordinates as values
- Adding Barcelona means adding a new value to that variable
- Once added, the panel **repeats automatically** — one panel per city

</details>

<details>
<summary>Task 2 hints</summary>

- Add `&daily=precipitation_sum&timezone=auto` to the existing API URL
- The response will include a `daily` object with `precipitation_sum` array
- Use **Infinity** to parse the nested JSON and extract the value
- A **Stat** panel showing today's precipitation (index 0 of the array) works well
- You can also use a **Bar chart** to show precipitation over the next 7 days

</details>

---

[View solution](./solution.md)
