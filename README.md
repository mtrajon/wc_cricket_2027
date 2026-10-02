# 🏏 Cricket World Cup 2027: Schedule, Results & Tables

An unofficial fan website for the **ICC Men's Cricket World Cup 2027**, played in South Africa, Zimbabwe and Namibia from 2 October to 21 November 2027.

It shows all 57 matches with start times in your own time zone, live points tables with net run rate, and a knockout bracket that fills in as the tournament goes on.

**Live site:** `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`
*(replace with your GitHub Pages address)*

---

## Features

- **Full schedule** of all 57 matches: Super Series, group stage, Super 7, semi-finals and final, with venues and grounds.
- **Start times in your time zone.** Times convert automatically, or visitors can pick a country from the "Times in" menu. Venue local time is always shown too.
- **Next match banner** with a countdown. It shows **Live now** while a match is in progress, and the champions after the final.
- **Tournament ribbon** showing every day of the tournament. Tap a day to jump to its matches.
- **Results** with scores, overs and winning margins (for example, "India won by 6 wickets").
- **Points tables** for Group A, Group B, the Super 7 and the Super Series, with played, won, lost, tied, no result, points and **net run rate**.
- **Knockout bracket.** It shows the current top four during the Super 7, then fills in semi-final and final results automatically.
- **Filters** by stage, team, venue, and results or upcoming matches.
- **Follow a team.** Tap the star in a table to highlight that team's matches.
- **Country flags** drawn in code, so there are no image files to manage.
- **Works on phones, tablets and computers**, with light and dark mode.

---

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole website: design, schedule and logic in one file. |
| `results.json` | All results, qualifier names, Super 7 line-up and start times. This is the only file you update during the tournament. |
| `README.md` | This file. |

---

## Setting up GitHub Pages

1. Upload `index.html` and `results.json` to the root of this repository.
2. Go to **Settings → Pages**.
3. Under **Branch**, choose `main` and `/ (root)`, then click **Save**.
4. After a minute or two, your site address appears at the top of the Pages screen.

---

## Updating results during the tournament

Results are stored in `results.json`. The website reads this file every time someone opens the page.

1. Open the live site, scroll to the bottom and click **Enter results (site owner)**.
2. Click **Add result** on a match. Choose the outcome and who batted first, then enter each team's runs, wickets and overs (for example `49.3`).
3. Click **Download results.json**.
4. On GitHub, upload the downloaded file so it replaces the existing `results.json`, then click **Commit changes**.

Visitors see the new results within a few minutes. GitHub keeps every version of `results.json` in its history, so you always have a backup.

> **Tip:** Results you enter are saved only in your browser until you upload `results.json`. Publish after each match day so nothing is lost.

### Other editor tools

| Button | What it does |
| --- | --- |
| **Teams, times and Super 7 line-up** | Name the qualifiers once known (e.g. Qualifier A → Scotland), set the default start time, and confirm which teams fill each Super 7 slot. |
| **Set time** (on each match) | Change one match's local start time, for example for a day-night game. |
| **Open results.json** | Load a results file from your computer, for example to continue on another device. |
| **Show JSON** | Shows the file contents to copy, if downloading doesn't work. |
| **Discard unpublished changes** | Goes back to the results currently published on the site. |

---

## How the tables are calculated

- **Points:** win = 2, tie or no result = 1 each, loss = 0.
- **Order:** points, then wins, then net run rate.
- **Net run rate (NRR):** runs scored per over minus runs conceded per over. If a team is all out, its innings counts as the full overs available (50, or fewer in a reduced match). No-result matches don't count towards NRR.
- **Group stage:** the top three in each group reach the Super 7, plus the better of the two fourth-placed teams.
- **Super 7:** points restart from zero. The top four reach the semi-finals (1st v 4th, 2nd v 3rd).

> For rain-affected matches decided by the DLS method, the official ICC NRR uses adjusted targets, so figures may differ slightly from official ones.

---

## Previewing the site at any date

Add `?now=` and a date and time (UTC) to the address to see how the site will look at that moment:

```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/?now=2027-11-05T09:30Z
```

A yellow note shows when preview mode is on. Remove the `?now=…` part to go back.

---

## `results.json` format

You don't need to edit this by hand. The editor creates it for you. For reference:

```json
{
  "updated": "2027-10-10T19:00:00.000Z",
  "results": {
    "2027-10-10_Johannesburg": {
      "outcome": "t1",
      "bf": "2",
      "i1": { "r": 276, "w": 4, "o": "37.5" },
      "i2": { "r": 273, "w": 10, "o": "45.2" },
      "mo": 50
    }
  },
  "settings": {
    "names": { "QA": "Scotland" },
    "slots": {},
    "s7confirmed": false,
    "defaultTime": "10:00",
    "times": {}
  }
}
```

| Field | Meaning |
| --- | --- |
| Match ID | Date plus venue city, e.g. `2027-10-10_Johannesburg` (spaces become dashes, e.g. `Cape-Town`). |
| `outcome` | `t1` (first-listed team won), `t2` (second-listed team won), `tie`, or `nr` (no result). |
| `bf` | Which team batted first: `"1"` or `"2"`. |
| `i1`, `i2` | Each team's innings: runs `r`, wickets `w`, overs `o`. |
| `mo` | Overs per side (50, or fewer if reduced). |
| `note` | Optional text, e.g. `"DLS method"`. |
| `t1`, `t2` | Teams, only for the semi-finals and final. |
| `names` | Real names for `QA`, `QB`, `QF1`, `QF2`, `QF3`. |
| `slots` | Super 7 slots that differ from the pre-seeded teams. |
| `defaultTime`, `times` | Local start times (24-hour, venue time UTC+2). |

---

## Data and disclaimer

Fixtures are taken from the official schedule announced by the ICC on 1 October 2026. Start times are provisional until confirmed by the ICC. Always check [icc-cricket.com](https://www.icc-cricket.com) for official information.

This is an **unofficial fan project** and is not affiliated with or endorsed by the International Cricket Council.
