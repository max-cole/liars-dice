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
| The Merovingian | 25.9 | 259 | 35.4 | 1061 | 3000 |
| EvilStewie | 17.3 | 2014 | 18.0 | 2335 | 13000 |
| Deep Thought | 13.1 | 1736 | 15.8 | 1736 | 11000 |
| Peter Beter | 10.7 | 2075 | 16.9 | 2366 | 14000 |
| Stewie | 10.2 | 4178 | 18.6 | 4831 | 26000 |
| Peter Griffin | 8.9 | 2097 | 15.0 | 2097 | 14000 |
| Nuke LaLoosh | 7.4 | 3009 | 17.0 | 4082 | 24000 |
| Sloane | 6.5 | 3905 | 18.1 | 7586 | 42000 |

### Championship
| Player | Season W% | Wins in CH | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| Columbo | 12.4 | 556 | 16.7 | 1003 | 6000 |
| Diego | 11.4 | 2404 | 17.7 | 6086 | 34350 |
| Zara | 11.3 | 3772 | 18.7 | 6187 | 33000 |
| Eva | 9.3 | 5186 | 19.3 | 6564 | 34000 |
| Cal Culatid | 8.9 | 2323 | 17.7 | 3887 | 22000 |
| Honest Abe | 8.7 | 2386 | 14.3 | 2859 | 20000 |
| Finn | 4.6 | 2225 | 17.2 | 6410 | 37250 |

### Level 1
| Player | Season W% | Wins in L1 | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| Remy | 13.7 | 4195 | 17.3 | 7941 | 46000 |
| Rick Sanchez | 10.5 | 3213 | 16.9 | 3213 | 19000 |
| Bruno | 8.9 | 2984 | 12.5 | 3939 | 31450 |
| Alice | 8.7 | 3986 | 15.7 | 5079 | 32450 |
| Meg Griffin | 6.9 | 285 | 9.5 | 285 | 3000 |
| Liar², Pants on Fire | 2.0 | 925 | 4.0 | 925 | 23000 |
| Topper | 1.5 | 2283 | 8.2 | 2283 | 28000 |
| Cleo | 1.0 | 1660 | 5.2 | 1677 | 32450 |

### Quarter Leaderboard

| Player | Tier | PRM W% | CH W% | L1 W% | Total W% | Games |
|--------|------|--------|-------|-------|----------|-------|
| The Merovingian | Premier | 25.9 | 33.4 | 46.8 | 35.4 | 3000 |
| Zara | Championship | 20.1 | 18.0 | — | 18.7 | 33000 |
| Diego | Championship | 18.1 | 17.2 | — | 17.7 | 34350 |
| Stewie | Premier | 17.4 | 36.5 | 28.8 | 18.6 | 26000 |
| Eva | Championship | 17.2 | 19.9 | — | 19.3 | 34000 |
| EvilStewie | Premier | 16.8 | 32.1 | — | 18.0 | 13000 |
| Peter Beter | Premier | 16.0 | 29.1 | — | 16.9 | 14000 |
| Deep Thought | Premier | 15.8 | — | — | 15.8 | 11000 |
| Sloane | Premier | 15.0 | 23.0 | — | 18.1 | 42000 |
| Peter Griffin | Premier | 15.0 | — | — | 15.0 | 14000 |
| Alice | Level 1 | 14.8 | 12.6 | 16.6 | 15.7 | 32450 |
| Nuke LaLoosh | Premier | 14.3 | 27.6 | 52.1 | 17.0 | 24000 |
| Finn | Championship | 14.0 | 13.1 | 21.9 | 17.2 | 37250 |
| Cal Culatid | Championship | 12.8 | 17.9 | 26.5 | 17.7 | 22000 |
| Bruno | Level 1 | 10.9 | 13.8 | 12.4 | 12.5 | 31450 |
| Remy | Level 1 | 10.6 | 14.1 | 22.1 | 17.3 | 46000 |
| Columbo | Championship | 7.7 | 18.5 | 29.3 | 16.7 | 6000 |
| Cleo | Level 1 | 1.1 | 0.3 | 5.9 | 5.2 | 32450 |
| Honest Abe | Championship | — | 13.3 | 23.6 | 14.3 | 20000 |
| Rick Sanchez | Level 1 | — | — | 16.9 | 16.9 | 19000 |
| Meg Griffin | Level 1 | — | — | 9.5 | 9.5 | 3000 |
| Topper | Level 1 | — | — | 8.2 | 8.2 | 28000 |
| Liar², Pants on Fire | Level 1 | — | — | 4.0 | 4.0 | 23000 |

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
