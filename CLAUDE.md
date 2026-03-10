# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

This is Lawrence Chen's GitHub profile repository (`techwithlc/techwithlc`). It contains:
- **`README.md`** — the rendered GitHub profile page
- **`.github/workflows/profile-3d.yml`** — daily GitHub Actions workflow that regenerates 3D contribution SVGs
- **`profile-3d-contrib/`** — auto-generated SVG files (10 style variants); do not hand-edit these

## How the Automation Works

The workflow runs daily at 18:00 UTC (03:00 JST) and on manual dispatch:
1. Checks out the repo
2. Runs `yoshi389111/github-profile-3d-contrib@0.7.1` using `GITHUB_TOKEN` and `USERNAME`
3. Auto-commits and pushes all generated SVGs back to `main`

The README embeds `profile-3d-contrib/profile-night-green.svg` directly via a raw GitHub URL.

## Triggering a Manual Regeneration

Go to Actions → "GitHub-Profile-3D-Contrib" → "Run workflow" in the GitHub UI. There are no local build commands — everything runs in CI.

## Making Changes

- Edit `README.md` to update profile content (bio, expertise, badges, links)
- Edit `.github/workflows/profile-3d.yml` to change the schedule or switch SVG theme displayed
- To change which SVG is displayed in the README, update the `<img src=...>` on the last line of `README.md` to reference a different file from `profile-3d-contrib/`
