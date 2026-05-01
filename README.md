# contributions 📈

> A GitHub Actions workflow that keeps your contribution graph active with randomized daily commits.

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-automated-blue?logo=githubactions)
![License](https://img.shields.io/badge/license-MIT-green)

## Features

- ⏰ **Daily automation** — runs every day at 06:00 UTC via a scheduled cron job
- 🎲 **Randomized activity** — 80% chance of committing on any given day, so the graph has natural gaps
- ⏳ **Varied timestamps** — waits a random delay of up to 3 hours before committing
- 🔒 **Works with private repos** — enable private contributions on your profile to count them publicly

## Getting Started

### 1. Fork or clone this repository

```bash
git clone https://github.com/casper-justus/contributions.git
cd contributions
```

### 2. Push it to your own GitHub account

Create a new repository on your GitHub account (public or private), then:

```bash
git remote set-url origin https://github.com/YOUR_USERNAME/contributions.git
git push -u origin main
```

### 3. Enable Actions

Go to your repository → **Actions** tab → enable workflows if prompted.

### 4. (Optional) Private repo setup

If using a private repository, go to your GitHub **Profile** → scroll to the contribution graph → click **Contribution settings** → check **Include private contributions on my profile**.

## Configuration

All settings are inside `.github/workflows/activity.yml`.

| Setting | Default | Description |
|---|---|---|
| Cron schedule | `0 6 * * *` | Time the workflow triggers daily (06:00 UTC) |
| Commit chance | `80` | Percentage chance a commit is made on any given day |
| Max delay | `10800` seconds | Maximum random wait before committing (3 hours) |

## How It Works

1. The workflow triggers daily at 06:00 UTC.
2. A bash script rolls a random number — if below 80, the workflow proceeds.
3. The runner sleeps for a random duration (1s to 3hrs).
4. The current timestamp is appended to a `.keepalive` file.
5. The change is committed and pushed using your GitHub noreply email so it counts toward your graph.

## License

MIT
