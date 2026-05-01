# contributions 📈

A GitHub Actions workflow that keeps my contribution graph active with randomized daily commits.

## How it works
- Runs every day at **06:00 UTC** via a scheduled cron job
- Has an **80% chance** of committing on any given day — so the graph has natural gaps
- Waits a **random delay of up to 3 hours** before committing to vary the timestamp
- Appends the current date to a `.keepalive` file and pushes the commit
