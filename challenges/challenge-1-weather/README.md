# Challenge 1: Team Weather Dashboard

**Data source:** Infinity · **Facilitator:** Yaëlle

**Starting dashboard:** _TBD_
_(Make a copy before editing — Save > Save as Copy > select your folder)_

---

## Context

My team is distributed in 5 different places in the world.
For fun we have a weather dashboard so we always know how warm it is where everybody is.

---

## Task 1

A new team member joins from Barcelona, Spain:

> "I want to add that location's information to the dashboard."

Barcelona coordinates: **41.3874° N, 2.1686° E**

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
https://api.open-meteo.com/v1/forecast?latitude=48.8566&longitude=2.3522&current=temperature_2m&timezone=auto
```

Returns current temperature for Paris.

---

## Hints

<details>
<summary>Task 1 hints</summary>

- **Duplicate** any existing temperature panel
- Change the `latitude` and `longitude` in the URL to Barcelona's: `latitude=41.3874&longitude=2.1686`
- Update the panel title to include Barcelona
- Change the row settings to allow **6 panels per row** max
- **Alternative:** Use the saved query "Paris Temperature" and update the coordinates

</details>

<details>
<summary>Task 2 hints</summary>

- **Duplicate the temperature row** to create a precipitation section
- Use the saved query "Barcelona Precipitation" as a starting point
- Change the `latitude` and `longitude` to match each city
- Change the unit of the Stat panel to **mm**
- The API parameter for precipitation is `&daily=precipitation_sum&timezone=auto`

</details>

---

[View solution](./solution.md)
