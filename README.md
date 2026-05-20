# NBA Ticket Scraper Demo 🏀

A beginner-friendly Python web scraping demo that uses **Beautiful Soup** and **Requests** to find cheap NBA tickets from SeatGeek. Built as part of a Python learning series.

---

## What it does

- Sends an HTTP request to a ticket listing page using `requests`
- Parses the returned HTML using `BeautifulSoup`
- Extracts ticket prices, game info, venue, and availability
- Filters results by price and team

---

## Tech stack

| Tool | Purpose |
|------|---------|
| `requests` | Fetches the raw HTML of a webpage |
| `beautifulsoup4` | Parses and extracts data from HTML |
| `Python 3.x` | Core language |

---

## Getting started

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/nba-ticket-scraper.git
cd nba-ticket-scraper
```

### 2. Install dependencies

```bash
pip install requests beautifulsoup4
```

### 3. Run the scraper

```bash
python scraper.py
```

---

## Example output

```
76ers vs Celtics - May 24, 2026 · 7:30 PM
Wells Fargo Center, Philadelphia
Price: $89 | Status: Available

Knicks vs Pacers - May 25, 2026 · 6:00 PM
Madison Square Garden, New York
Price: $142 | Status: Available
```

---

## How it works

```python
from bs4 import BeautifulSoup
import requests

page = requests.get("https://www.seatgeek.com/nba-tickets")
soup = BeautifulSoup(page.content, "html.parser")
tickets = soup.find_all("div", class_="ticket-price")
print(tickets)
```

1. `requests.get()` fetches the full HTML of the page
2. `BeautifulSoup` parses that HTML into a readable structure
3. `find_all()` searches for every element matching the target class
4. Results are printed and can be filtered by price or team

---

## Notes

> Most major ticket sites use bot protection (Cloudflare, CAPTCHA) that blocks basic scrapers. This project is intended as a learning demo. For production use, consider the [SeatGeek API](https://platform.seatgeek.com/) instead.

---

## Part of a Python learning series

This project is part of an ongoing Python blog series covering:
- `Beautiful Soup` — web scraping
- `Pandas` — data organization
- `Matplotlib` — data visualization
- `Requests` — HTTP handling

Follow along on [Bluesky](https://bsky.app) for new posts.

---

## License

MIT
