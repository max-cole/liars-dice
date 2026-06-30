# Liar's Dice League

A Python engine for running Liar's Dice games between algorithmic players. Players compete in a tiered league — submit a PR to join, and a weekly scheduled run plays the games and updates standings (extra runs trigger automatically when a player file changes).

_This project is based on the foundational work and initial implementation by [Zach Austin](https://github.com/zachaustin01)._

Interested in competing? **[Visit the Wiki](https://github.com/after2400/liars-dice/wiki)** — rules, player API, and how to submit a bot. For local dev setup see [CONTRIBUTING.md](CONTRIBUTING.md).

## Current Standings

<!-- prettier-ignore-start -->
<!-- leaderboard-start -->
### Premier
| Player | Season W% | Wins in PRM | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| EvilStewie | 23.8 | 1841 | 18.0 | 2162 | 12000 |
| Deep Thought | 15.0 | 1605 | 16.1 | 1605 | 10000 |
| Sloane | 12.0 | 3840 | 18.3 | 7521 | 41000 |
| Peter Beter | 11.7 | 1968 | 17.4 | 2259 | 13000 |
| Stewie | 11.5 | 4076 | 18.9 | 4729 | 25000 |
| Peter Griffin | 10.0 | 2008 | 15.4 | 2008 | 13000 |
| Nuke LaLoosh | 8.7 | 2935 | 17.4 | 4008 | 23000 |

### Championship
| Player | Season W% | Wins in CH | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| Columbo | Relegated | 432 | 17.6 | 879 | 5000 |
| Cal Culatid | 14.1 | 2234 | 18.1 | 3798 | 21000 |
| Diego | 13.6 | 2290 | 17.9 | 5972 | 33350 |
| Eva | 13.2 | 5093 | 19.6 | 6471 | 33000 |
| Zara | 12.3 | 3659 | 19.0 | 6074 | 32000 |
| Honest Abe | 11.6 | 2299 | 14.6 | 2772 | 19000 |
| Finn | 7.3 | 2179 | 17.6 | 6364 | 36250 |

### Level 1
| Player | Season W% | Wins in L1 | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| Remy | Relegated | 4058 | 17.3 | 7804 | 45000 |
| Rick Sanchez | 17.3 | 3108 | 17.3 | 3108 | 18000 |
| Alice | 15.8 | 3899 | 15.9 | 4992 | 31450 |
| Bruno | 15.0 | 2895 | 12.6 | 3850 | 30450 |
| Meg Griffin | 14.5 | 216 | 10.8 | 216 | 2000 |
| Topper | 6.6 | 2268 | 8.4 | 2268 | 27000 |
| Liar², Pants on Fire | 4.2 | 905 | 4.1 | 905 | 22000 |
| Cleo | 2.1 | 1650 | 5.3 | 1667 | 31450 |

### Quarter Leaderboard

| Player | Tier | PRM W% | CH W% | L1 W% | Total W% | Games |
|--------|------|--------|-------|-------|----------|-------|
| Zara | Championship | 20.1 | 18.3 | — | 19.0 | 32000 |
| Diego | Championship | 18.1 | 17.6 | — | 17.9 | 33350 |
| Stewie | Premier | 17.7 | 36.5 | 28.8 | 18.9 | 25000 |
| Eva | Championship | 17.2 | 20.4 | — | 19.6 | 33000 |
| EvilStewie | Premier | 16.7 | 32.1 | — | 18.0 | 12000 |
| Peter Beter | Premier | 16.4 | 29.1 | — | 17.4 | 13000 |
| Deep Thought | Premier | 16.1 | — | — | 16.1 | 10000 |
| Sloane | Premier | 15.4 | 23.0 | — | 18.3 | 41000 |
| Peter Griffin | Premier | 15.4 | — | — | 15.4 | 13000 |
| Alice | Level 1 | 14.8 | 12.6 | 17.0 | 15.9 | 31450 |
| Nuke LaLoosh | Premier | 14.7 | 27.6 | 52.1 | 17.4 | 23000 |
| Finn | Championship | 14.0 | 13.6 | 21.9 | 17.6 | 36250 |
| Cal Culatid | Championship | 12.8 | 18.6 | 26.5 | 18.1 | 21000 |
| Bruno | Level 1 | 10.9 | 13.8 | 12.6 | 12.6 | 30450 |
| Remy | Level 1 | 10.6 | 14.1 | 22.5 | 17.3 | 45000 |
| Columbo | Championship | 7.7 | 21.6 | 29.3 | 17.6 | 5000 |
| Cleo | Level 1 | 1.1 | 0.3 | 6.1 | 5.3 | 31450 |
| Honest Abe | Championship | — | 13.5 | 23.6 | 14.6 | 19000 |
| Rick Sanchez | Level 1 | — | — | 17.3 | 17.3 | 18000 |
| Meg Griffin | Level 1 | — | — | 10.8 | 10.8 | 2000 |
| Topper | Level 1 | — | — | 8.4 | 8.4 | 27000 |
| Liar², Pants on Fire | Level 1 | — | — | 4.1 | 4.1 | 22000 |

<!-- leaderboard-end -->
<!-- prettier-ignore-end -->

_Updated weekly (Mondays at 9am UTC) or whenever a player file is added/modified. Full history in the [season tracking issue](https://github.com/after2400/liars-dice/issues/4)._

---

## How It Works

Two workflows replace the old per-PR game model:

**`register-player.yml`** — triggered when a PR touches `players/`

- Validates the player file (class name matches filename, display name ≤ 25 chars)
- Registers the player in `leaderboard.yaml` at the appropriate entry tier
- Commits the leaderboard update and auto-merges the PR
- No games run immediately

**`run-season.yml`** — cron fires daily at 9am UTC; a guard job decides whether to actually run

- Runs on Mondays (weekly cadence) or when any `players/*.py` file was added/modified in the last 24h; `workflow_dispatch` always runs
- Plays `N_GAMES` (default 1000) games in each active tier, bottom-up: `inactive → L1 → CH → PRM`
- Promotions and relegations are applied between tiers (so a player promoted from L1 can compete in CH the same day)
- Commits the updated leaderboard and posts a summary to the season tracking issue

A tier is skipped if it has fewer than 2 players.

---

## Tier Structure

Capacities scale with `TOP_N` (repo variable, default 4, max 8):

| Tier     | Capacity    | Notes                                 |
| -------- | ----------- | ------------------------------------- |
| PRM      | `TOP_N`     | Premier Division — top of the table   |
| CH       | `TOP_N`     | Championship                          |
| L1       | `2 × TOP_N` | League One                            |
| inactive | unlimited   | Plays separately; top player promotes |

**Entry tier:** new players enter the lowest active tier that has capacity (L1 if possible, else CH, else PRM). A player registered mid-day plays in the next scheduled run.

**Promotion / relegation (per season run):**

- Top player in each tier promotes to the tier above
- Bottom player(s) relegate to the tier below
- `times_inactive` increments each time a player is relegated to inactive

---

## Project Structure

```
game/
  __main__.py          # entry point, logging, player selection, --tier filter
  validate.py          # player file validator (python -m game.validate <file>)
  components/
    script.py          # game loop and round orchestration
    bets.py            # Bet class, bet_validator, bet_grader
    series.py          # series runner and results formatter
    leaderboard.py     # leaderboard read/write, apply_season_results
    stats.py           # GameStats incremental stats (optional algo arg, opt-in by name)
    utils.py           # player loader
  season/
    utils.py           # shared helpers: _load_lb, _save_lb, date/quarter utilities
  simulation/
    quarter.py         # simulate a full quarter locally (uv run python -m game.simulation.quarter)

players/               # one .py file per player — see full list on GitHub
  ...                  # https://github.com/after2400/liars-dice/tree/main/players

.github/
  workflows/
    register-player.yml      # PR validation, registration, auto-merge
    run-monday.yml           # weekly/conditional season runner (guard + run jobs)
    update-leaderboard.yml   # updates README standings on player file changes
    guard-non-player-prs.yml # blocks non-admin non-player PRs from auto-merge
    release.yml              # PSR — bumps version, regenerates CHANGELOG, creates GitHub Release
    lint.yml                 # ruff + commitlint on push/PR
  scripts/
    register_player.py   # validates player file, writes leaderboard entry
    run_season.py        # bottom-up tier runner, writes season summary
    reset_season.py      # quarterly tournament reset and pool runner
    lb_owner.py          # looks up github_username by class name
    lb_has_player.py     # checks whether a class name is registered
    lb_delete.py         # removes players from leaderboard by file path
    lb_update_name.py    # validates and updates display_name on modification

.Justfile                # local dev recipes (just develop / pytest / lint / simulate-*)
leaderboard.yaml         # source of truth — tier, stats, github_username per player
```
