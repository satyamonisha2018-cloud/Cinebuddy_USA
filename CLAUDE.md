# Cinebuddy — Movie Ticket Analytics Dashboard

## What This Project Is

**Cinebuddy** is a movie ticket analytics dashboard that tracks ticket purchases across multiple theatres and movies. Two operators — **Vamsi** and **Monisha** — buy tickets at various cinema locations, and this dashboard gives a live view of total spend, tickets sold, best-performing movies, and theatre-level breakdown.

Data comes from **Wave App CSV exports** (Income rows only). The dashboard is a single self-contained HTML file deployed as a **GitHub Pages static page**.

---

## Current Data (May 21 – Jun 1, 2026)

### Raw Ticket Data

| Date | Theatre | Movie | Tickets | Amount | Buyer |
|------|---------|-------|---------|--------|-------|
| May 21 | Starlight | Dhrishyam 3 | 3 | $25.50 | Vamsi |
| May 21 | Commerce Center | Dhrishyam 3 | 3 | $27.00 | Monisha |
| May 21 | Fox | Peddi | 2 | $30.00 | Vamsi |
| May 21 | Solomon | Karuppu | 4 | $28.00 | Monisha |
| May 22 | Wilder | Prada 2 | 2 | $18.00 | Monisha |
| May 22 | Shiloh | Dhrishyam 3 | 2 | $16.00 | Vamsi |
| May 22 | Perimeter Pointe | Dhrishyam 3 | 1 | $10.00 | Vamsi |
| May 23 | Times Square | Star Wars | 2 | $22.00 | Vamsi |
| May 23 | Secaucus | Star Wars | 2 | $18.00 | Vamsi |
| May 24 | Solomon | Chand Mera Dil | 2 | $18.00 | Vamsi |
| May 24 | Village Park | Karuppu | 2 | $16.00 | Vamsi |
| May 24 | Village Park | Karuppu | 1 | $8.00 | Vamsi |
| May 24 | Solomon | Sheep Detective | 4 | $36.00 | Vamsi |
| May 24 | Greenwood | Passenger | 1 | $8.00 | Vamsi |
| May 24 | Hadley | Star Wars | 5 | $45.00 | Vamsi |
| May 24 | Commerce | Dhrishyam 3 | 3 | $27.00 | Monisha |
| May 25 | Commerce | Dhrishyam 3 | 3 | $21.00 | Vamsi |
| May 25 | Fox | Veerabhadrudu | 5 | $45.00 | Vamsi |
| May 25 | Commerce | Michael | 3 | $21.00 | Vamsi |
| May 26 | Shiloh | Dhrishyam 3 | 5 | $40.00 | Monisha |
| May 26 | Solomon | Obsession | 3 | $27.00 | Vamsi |
| May 26 | Arnot Mall | Obsession | 2 | $16.00 | Monisha |
| May 27 | Coldwater | Peddi | 3 | $45.00 | Vamsi |
| May 29 | Peoples Plaza | Obsession | 3 | $24.00 | Monisha |
| May 29 | Secaucus | Obsession | 2 | $17.00 | Vamsi |
| May 30 | Shiloh | Obsession | 4 | $32.00 | Monisha |
| May 30 | Huebner Oaks | Star Wars | 5 | $30.00 | Vamsi |
| May 30 | Deerfield | Obsession | 1 | $8.00 | Vamsi |
| May 30 | Coldwater | Obsession | 5 | $45.00 | Monisha |
| May 31 | Solomon | Obsession | 3 | $27.00 | Monisha |
| May 31 | Huebner | Obsession | 2 | $12.00 | Vamsi |
| Jun 1 | Secaucus | Pressure | 1 | $9.00 | Vamsi |
| Jun 1 | Waterford | Backrooms | 2 | $18.00 | Vamsi |
| Jun 1 | Bellingham | 1:Nenokkadine | 2 | $12.00 | Vamsi |
| Jun 1 | Bellingham | Obsession | 1 | $9.00 | Vamsi |
| Jun 1 | Secaucus | Backrooms | 1 | $9.00 | Vamsi |

**Note in code:** "REAL DATA — parsed from Wave CSV, Income rows, May 21+ only"

### Movies Tracked

Dhrishyam 3, Peddi, Karuppu, Prada 2, Star Wars, Chand Mera Dil, Sheep Detective, Passenger, Veerabhadrudu, Michael, Obsession, Pressure, Backrooms, 1:Nenokkadine

### Theatres Tracked

Starlight, Commerce Center, Fox, Solomon, Wilder, Shiloh, Perimeter Pointe, Times Square, Secaucus, Village Park, Greenwood, Hadley, Commerce, Arnot Mall, Coldwater, Peoples Plaza, Huebner Oaks, Deerfield, Waterford, Bellingham, Huebner, Hadley

### Operators

- **Vamsi** — primary buyer
- **Monisha** — secondary buyer

---

## Dashboard Features

### KPI Cards (4 cards)
- Total Revenue ($)
- Total Tickets sold
- Top Movie (by tickets)
- #2 Movie (by tickets)
- (implicitly) Top Theatre

### Charts
1. **Monthly Tickets Bar** — tickets sold by month (aggregated)
2. **Movie Performance** — combo chart: bar (tickets) + line (revenue) per movie
3. **Stacked Daily Bar** — tickets per day, stacked by movie, colored by movie, with inline movie name labels
4. **Theatre Heatmap** — tickets by theatre over time

### Filters
- Theatre dropdown (auto-populated from data)
- Month dropdown

### Hero Insight Chip
Auto-generated top insight shown as a pill in the header.

---

## Design System

**Dark theme** — cinema/entertainment aesthetic.

```css
:root {
  --bg:     #080c14;    /* page background — very dark navy */
  --card:   #131d2e;    /* card backgrounds */
  --border: rgba(255,255,255,.07);
  --ink:    #f0f4ff;    /* primary text */
  --muted:  #6b7fa0;    /* secondary text */
  --dim:    #3a4a62;    /* tertiary */
  --amber:  #f59e0b;    /* brand accent — Cinebuddy orange/gold */
  --red:    #ef4444;
  --blue:   #3b82f6;
  --teal:   #14b8a6;
  --purple: #a78bfa;
  --green:  #22c55e;
  --r:      14px;       /* border radius */
}
```

**Background:** solid `#080c14`

**Brand:** Amber/orange gradient icon (`linear-gradient(135deg,#f59e0b,#ef4444)`), brand name "Cine**buddy**" with amber highlight.

**Chart library:** Chart.js v4.4.0 via CDN (`https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js`). The dashboard shows a warning banner if Chart.js fails to load.

**Color palette for data:** `["#f59e0b","#3b82f6","#14b8a6","#a78bfa","#ef4444","#22c55e","#f97316","#ec4899","#06b6d4"]`

**Font:** `'Segoe UI', Arial, sans-serif`

**Nav:** Sticky top nav with blur backdrop (`backdrop-filter: blur(18px)`), links: Overview, Movies, Theatres, Heat Map.

---

## Tech Stack

- **Pure HTML/CSS/JS** — single self-contained file
- **Chart.js v4.4.0** (CDN) — only external dependency
- **Static** — deploy directly to GitHub Pages
- **Data structure:** `const RAW = [ {date, theatre, movie, tickets, amount, by}, ... ]`

---

## Data Structure

```js
const RAW = [
  { date: "2026-05-21", theatre: "Starlight", movie: "Dhrishyam 3", tickets: 3, amount: 25.50, by: "Vamsi" },
  // ... more entries
];
```

All analytics are computed dynamically from `RAW`. The theatre dropdown is auto-populated from `RAW` on page load — no manual maintenance needed.

---

## How to Add New Data

When new Wave CSV exports arrive:
1. Keep only `Income` rows from Wave
2. Extract: date, theatre name, movie name, ticket count, amount, buyer name
3. Append new objects to the `RAW` array in the `<script>` block
4. The charts and KPIs update automatically — no other changes needed

---

## Files in This Project

| File | What It Is |
|------|-----------|
| `cinebuddy-dashboard.html` | The complete analytics dashboard — single file, all features |

---

## Git Setup (To Do)

```bash
git init
git add .
git commit -m "Initial commit — Cinebuddy movie ticket analytics"
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
```

---

## What's Next / Ideas

- [ ] Add more data as new Wave exports come in (just append to `RAW`)
- [ ] Add a "by buyer" filter (Vamsi vs Monisha breakdown)
- [ ] Add revenue per theatre ranking
- [ ] Track average ticket price per movie over time
- [ ] Add a date range picker filter
- [ ] Consider a "profit per booking" calculation if cost data is available
