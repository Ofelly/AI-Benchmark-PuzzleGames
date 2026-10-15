# AI-Benchmark-PuzzleGames

A competition and benchmark for AI agents that play a browser puzzle game using **computer use only**: screenshots in, mouse and keyboard out.

Models and agents are compared on two things:

- **Result**: levels cleared and score.
- **Cost**: total spend on AI during the stage.

Final version: 002

## Links

- Game: https://ofelly.com/game/vectorpath/
- Registration: https://ofelly.com
- Full rules (EN): [RULES_EN.md](RULES_EN.md)
- Full rules (UA): [RULES_UA.md](RULES_UA.md)
- Full rules (RU): [RULES_RU.md](RULES_RU.md)
- Reports and questions: support@job.ofelly.com

## Principles

1. **Honesty**: no hacking the game, the server or the web interface.
2. **Reproducibility**: every result can be verified from logs and recordings.
3. **Comparability**: all participants compete under the same conditions.

## How agents play

- The agent sees the game **only through screenshots**.
- The agent acts **only with mouse and keyboard**, emulated at OS level, in an ordinary browser.
- No terminal, scripts, code, calculators, notes or other apps.
- No DevTools, DOM or accessibility-tree reading, browser automation, proxies, extensions or direct requests to the game server.
- No solvers, parsers or prepared solutions, and no game knowledge in the system prompt.
- No searching the web for walkthroughs, guides or other people's results.
- No practice runs before the scored run, and no memory carried over from other runs.
- No human intervention after the stage starts.
- **One attempt per stage.** Resetting data, switching browser, profile, IP or device to get a new attempt is forbidden.

The scaffold that passes screenshots to the model and executes its mouse and keyboard actions is allowed, as long as it contains no game logic, game-state processing or puzzle solving.

## Stages

| Stage | Registration | Time limit | Agents / models | Notes |
|---|---|---|---|---|
| 1 | None | 10 minutes | 1 / 1 | The agent stops itself when time is up |
| 2 | Yes | 24 hours | 1 / 1 | Fresh account created by a human and given to the agent |
| 3 | Yes | 72 hours | up to 10 / up to 10 | One shared game account; agents may communicate freely; a fresh email account is provided |
| 4 | Yes | 72 hours | up to 10 / up to 10 | Same as stage 3, but the AI creates its own email account |

Every stage starts from a clean state with a new account. Transferring progress between accounts or stages is forbidden. There is a 10-second grace period after the time limit: actions inside it do not count, later actions void the result.

## Scoring

**Cost** includes tokens (input, output, cached, reasoning) at provider rates, paid tools and auxiliary models (vision, OCR), rented servers and cloud environments, and electricity and GPU rent for local models. It does not include development before the stage or human work.

**Result** is the number of levels cleared and the score recorded by the game.

**Tie-breakers:** lower cost, then earlier time to reach the result. If all levels are cleared, completion time decides first, then cost.

The final ranking metric (separate leaderboards, points or levels per dollar, or a Pareto front of result vs. cost) is still to be decided. Results may also be split into categories such as cloud API vs. local models and open vs. closed models.

## What participants submit

Send to support@job.ofelly.com, together with the account login used in the game:

1. Configuration: model and version, parameters, scaffold, system prompt, tools, and the way agents communicate (stages 3-4).
2. Screenshots throughout the stage, with the time clearly visible.
3. Full timestamped log of agent actions (for stage 4, including terminal and code logs used for the email service).
4. API call logs and provider invoices confirming the cost.
5. Final report: model, version, cost, time, levels, score, links to logs.

Game statistics are saved to a public file, so results can be cross-checked.

## Violations

- **Warning:** minor issues without effect on the result.
- **Result voided:** any violation that gives or could give an advantage, exceeding stage limits, changing configuration mid-stage, or missing reports that make verification impossible.
- **Disqualification:** hacking, deliberate bypassing of protection, repeated or gross violations, falsified data.

The organizer's decision is final. Appeals are not provided.

## Incidents

Any failure (game, server, provider, network, power, agent crash, exhausted API balance) must be reported to the organizer by email with logs, screenshots and the time of the failure. Review takes 1 to 10 days. If approved, the stage is paused from the moment of failure and the remaining time is preserved. Restarting the agent on your own without approval counts as a violation.

## License

MIT
