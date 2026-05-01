# Contributions 📈

This repository automates GitHub activity to keep the contribution graph active using a scheduled GitHub Actions workflow. 

## Features
- **Automated Commits:** Runs daily via GitHub Actions `cron` scheduling.
- **Organic Activity:** Includes a "dice roll" mechanism (80% chance to run) so it occasionally skips days, making the commit history look natural rather than automated.
- **Randomized Timestamps:** Introduces a random delay of up to 3 hours before committing, ensuring the activity doesn't happen at the exact same minute every day.

## How It Works
The core logic is handled by a GitHub Actions workflow located in `.github/workflows/activity.yml`. 

1. Every day at 06:00 UTC, the workflow is triggered.
2. A bash script generates a random number. If the number is below 80, the workflow proceeds.
3. The runner pauses for a random duration (between 1 second and 3 hours).
4. The script appends the current timestamp to a hidden `.keepalive` file.
5. The changes are committed and pushed back to the repository, utilizing the GitHub-provided noreply email to properly credit the account.

## Setup Instructions
If you are setting this up from scratch or moving it to a new account:
1. Create a repository named `contributions` (can be public or private).
2. Place the workflow code inside `.github/workflows/activity.yml`.
3. If this is a **private** repository, navigate to your main GitHub Profile page, click `Option` (the dropdown in your contribution graph settings), and check **Include private contributions on my profile** so the commits show up publicly.

> **Note on Actions Minutes:** If this repository is private, the randomized delay step consumes GitHub Actions minutes while it "sleeps". If you are close to your 2,000 free monthly minutes, you may want to reduce the maximum delay inside the workflow file.
