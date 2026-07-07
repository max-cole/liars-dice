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
| <img src="https://www.gravatar.com/avatar/39c6087277499978d0500bb0205419d1?d=identicon&f=y&s=64" width="64" height="64"> Ripley | 17.2 | 172 | 17.2 | 172 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/The_Oracle.gif" width="64" height="64"> The Oracle | 15.6 | 156 | 15.6 | 156 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/The_Merovingian.png" width="64" height="64"> The Merovingian | 14.2 | 142 | 14.2 | 142 | 1000 |
| <img src="https://www.gravatar.com/avatar/f68b87e0e12c96cc8ec181aa48e4e9b5?d=identicon&f=y&s=64" width="64" height="64"> EvilStewie | 12.9 | 129 | 12.9 | 129 | 1000 |
| <img src="https://res.cloudinary.com/rzifhdkf/image/upload/w_64,h_64,c_fill/HAL_9000.png" width="64" height="64"> HAL 9000 | 12.5 | 125 | 12.5 | 125 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Deep_Thought.jpg" width="64" height="64"> Deep Thought | 11.6 | 116 | 14.3 | 286 | 2000 |
| <img src="https://www.gravatar.com/avatar/4d0a927fbe8ecbf7e9d05deea69a694f?d=identicon&f=y&s=64" width="64" height="64"> Shwimp | 9.0 | 90 | 9.0 | 90 | 1000 |
| <img src="https://www.gravatar.com/avatar/8eb6692d51ca57e7464df1cb61624c89?d=identicon&f=y&s=64" width="64" height="64"> Columbo | 3.5 | 35 | 3.5 | 35 | 1000 |

### Championship
| Player | Season W% | Wins in CH | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| <img src="https://www.gravatar.com/avatar/28c4ac8b8ecc3772ff3d22f9bf6c737a?d=identicon&f=y&s=64" width="64" height="64"> Peter Beter | Relegated | 0 | 3.5 | 35 | 1000 |
| <img src="https://www.gravatar.com/avatar/b4eed5a89f11670e6c411cab8aa2b5a7?d=identicon&f=y&s=64" width="64" height="64"> Stewie | 12.2 | 122 | 12.2 | 122 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Sloane_Avery.png" width="64" height="64"> Sloane | 11.9 | 119 | 11.9 | 119 | 1000 |
| <img src="https://www.gravatar.com/avatar/d51be008f389672257bcaa7b722a3df8?d=identicon&f=y&s=64" width="64" height="64"> Peter Griffin | 11.9 | 119 | 11.9 | 119 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Cal_Culatid.jpg" width="64" height="64"> Cal Culatid | 11.0 | 110 | 24.9 | 499 | 2000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Eva_Longoria.png" width="64" height="64"> Eva | 10.0 | 100 | 10.0 | 100 | 1000 |
| <img src="https://www.gravatar.com/avatar/4fb845c67d91bcb3178498fc6fe1fedc?d=identicon&f=y&s=64" width="64" height="64"> Diego | 9.5 | 95 | 9.5 | 95 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Zara.png" width="64" height="64"> Zara | 9.2 | 92 | 9.2 | 92 | 1000 |

### Level 1
| Player | Season W% | Wins in L1 | Win % Total | Total Wins | Games |
|--------|-----------|----------------|-------------|------------|-------|
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Honest_Abe.jpg" width="64" height="64"> Honest Abe | Relegated | 0 | 7.3 | 73 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Nuke_LaLoosh.png" width="64" height="64"> Nuke LaLoosh | 35.0 | 350 | 35.0 | 350 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Meg_Griffin.png" width="64" height="64"> Meg Griffin | 25.9 | 259 | 25.9 | 259 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Finn_Carter.png" width="64" height="64"> Finn | 21.7 | 217 | 21.7 | 217 | 1000 |
| <img src="https://www.gravatar.com/avatar/9b2b78033ecf0401a2feab5b4ba7462e?d=identicon&f=y&s=64" width="64" height="64"> Bruno | 19.2 | 192 | 19.2 | 192 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Remy_Beasley.png" width="64" height="64"> Remy | 18.6 | 186 | 18.6 | 186 | 1000 |
| <img src="https://www.gravatar.com/avatar/17ad55a9b8384777496330d23e59d520?d=identicon&f=y&s=64" width="64" height="64"> Rick Sanchez | 14.8 | 148 | 14.8 | 148 | 1000 |
| <img src="https://www.gravatar.com/avatar/64489c85dc2fe0787b85cd87214b3810?d=identicon&f=y&s=64" width="64" height="64"> Alice | 9.9 | 99 | 9.9 | 99 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Topper.png" width="64" height="64"> Topper | 9.0 | 90 | 9.0 | 90 | 1000 |
| <img src="https://www.gravatar.com/avatar/6e1def9bfa26327930ba900d46f8c9b3?d=identicon&f=y&s=64" width="64" height="64"> Cleo | 3.6 | 36 | 3.6 | 36 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Liar_Liar.png" width="64" height="64"> Liar², Pants on Fire | 3.4 | 34 | 3.4 | 34 | 1000 |

### Quarter Leaderboard

| Player | Tier | PRM W% | CH W% | L1 W% | Total W% | Games |
|--------|------|--------|-------|-------|----------|-------|
| <img src="https://www.gravatar.com/avatar/39c6087277499978d0500bb0205419d1?d=identicon&f=y&s=64" width="64" height="64"> Ripley | Premier | 17.2 | — | — | 17.2 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/The_Oracle.gif" width="64" height="64"> The Oracle | Premier | 15.6 | — | — | 15.6 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/The_Merovingian.png" width="64" height="64"> The Merovingian | Premier | 14.2 | — | — | 14.2 | 1000 |
| <img src="https://www.gravatar.com/avatar/f68b87e0e12c96cc8ec181aa48e4e9b5?d=identicon&f=y&s=64" width="64" height="64"> EvilStewie | Premier | 12.9 | — | — | 12.9 | 1000 |
| <img src="https://res.cloudinary.com/rzifhdkf/image/upload/w_64,h_64,c_fill/HAL_9000.png" width="64" height="64"> HAL 9000 | Premier | 12.5 | — | — | 12.5 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Deep_Thought.jpg" width="64" height="64"> Deep Thought | Premier | 11.6 | 17.0 | — | 14.3 | 2000 |
| <img src="https://www.gravatar.com/avatar/4d0a927fbe8ecbf7e9d05deea69a694f?d=identicon&f=y&s=64" width="64" height="64"> Shwimp | Premier | 9.0 | — | — | 9.0 | 1000 |
| <img src="https://www.gravatar.com/avatar/28c4ac8b8ecc3772ff3d22f9bf6c737a?d=identicon&f=y&s=64" width="64" height="64"> Peter Beter | Championship | 3.5 | — | — | 3.5 | 1000 |
| <img src="https://www.gravatar.com/avatar/8eb6692d51ca57e7464df1cb61624c89?d=identicon&f=y&s=64" width="64" height="64"> Columbo | Premier | 3.5 | — | — | 3.5 | 1000 |
| <img src="https://www.gravatar.com/avatar/b4eed5a89f11670e6c411cab8aa2b5a7?d=identicon&f=y&s=64" width="64" height="64"> Stewie | Championship | — | 12.2 | — | 12.2 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Sloane_Avery.png" width="64" height="64"> Sloane | Championship | — | 11.9 | — | 11.9 | 1000 |
| <img src="https://www.gravatar.com/avatar/d51be008f389672257bcaa7b722a3df8?d=identicon&f=y&s=64" width="64" height="64"> Peter Griffin | Championship | — | 11.9 | — | 11.9 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Cal_Culatid.jpg" width="64" height="64"> Cal Culatid | Championship | — | 11.0 | 38.9 | 24.9 | 2000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Eva_Longoria.png" width="64" height="64"> Eva | Championship | — | 10.0 | — | 10.0 | 1000 |
| <img src="https://www.gravatar.com/avatar/4fb845c67d91bcb3178498fc6fe1fedc?d=identicon&f=y&s=64" width="64" height="64"> Diego | Championship | — | 9.5 | — | 9.5 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Zara.png" width="64" height="64"> Zara | Championship | — | 9.2 | — | 9.2 | 1000 |
| <img src="https://res.cloudinary.com/dfcgw5cr6/image/upload/w_64,h_64,c_fill/Honest_Abe.jpg" width="64" height="64"> Honest Abe | Level 1 | — | 7.3 | — | 7.3 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Nuke_LaLoosh.png" width="64" height="64"> Nuke LaLoosh | Level 1 | — | — | 35.0 | 35.0 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Meg_Griffin.png" width="64" height="64"> Meg Griffin | Level 1 | — | — | 25.9 | 25.9 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Finn_Carter.png" width="64" height="64"> Finn | Level 1 | — | — | 21.7 | 21.7 | 1000 |
| <img src="https://www.gravatar.com/avatar/9b2b78033ecf0401a2feab5b4ba7462e?d=identicon&f=y&s=64" width="64" height="64"> Bruno | Level 1 | — | — | 19.2 | 19.2 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Remy_Beasley.png" width="64" height="64"> Remy | Level 1 | — | — | 18.6 | 18.6 | 1000 |
| <img src="https://www.gravatar.com/avatar/17ad55a9b8384777496330d23e59d520?d=identicon&f=y&s=64" width="64" height="64"> Rick Sanchez | Level 1 | — | — | 14.8 | 14.8 | 1000 |
| <img src="https://www.gravatar.com/avatar/64489c85dc2fe0787b85cd87214b3810?d=identicon&f=y&s=64" width="64" height="64"> Alice | Level 1 | — | — | 9.9 | 9.9 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Topper.png" width="64" height="64"> Topper | Level 1 | — | — | 9.0 | 9.0 | 1000 |
| <img src="https://www.gravatar.com/avatar/6e1def9bfa26327930ba900d46f8c9b3?d=identicon&f=y&s=64" width="64" height="64"> Cleo | Level 1 | — | — | 3.6 | 3.6 | 1000 |
| <img src="https://res.cloudinary.com/hdyiihba/image/upload/w_64,h_64,c_fill/Liar_Liar.png" width="64" height="64"> Liar², Pants on Fire | Level 1 | — | — | 3.4 | 3.4 | 1000 |

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
    lb_update_player.py  # validates and updates display_name/avatar on modification

.Justfile                # local dev recipes (just develop / pytest / lint / simulate-*)
leaderboard.yaml         # source of truth — tier, stats, github_username per player
```
