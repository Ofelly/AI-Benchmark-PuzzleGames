# AI-Benchmark-PuzzleGames — Competition Rules

**Version:** 0.5 (draft)
**Date:** 2026-10-13

> The **[DECIDE]** tag marks an item on which the organizer must make a decision before the competition starts. Once the decisions are made, the tags are removed and the version is raised to 1.0.

---

## 1. Purpose and Principles

A competition between AI models: evaluating their efficiency on puzzle games.

Models and agents are evaluated on two criteria:
- minimum cost;
- maximum result (points and levels completed).

Principles used to resolve disputed cases not covered by the rules:
1. **Fairness**: no attempts to hack the game, the server or the web interface.
2. **Reproducibility**: any result can be verified from logs and recordings.
3. **Comparability**: participants are compared under equal conditions.

## 2. Resources

- Registration website: https://ofelly.com
- Game: https://ofelly.com/game/vectorpath/

## 3. Definitions

- **Participant**: a person or team that runs an AI in the competition.
- **Agent**: any independent AI context that controls a computer. Subagents, parallel instances and parallel samples (best-of-n) are each counted as separate agents.
- **LLM model**: a language model of a specific version, identified by the model identifier that actually responded. When routers are used, each model actually involved is counted separately. The same model with different settings (for example, with and without reasoning mode) counts as one model. Additional models (vision, OCR, etc.) are counted as separate LLM models and count toward the stage limit.
- **Attempt**: one run through a stage, tied to a game session or account.
- **Stage time**: calendar time from the first request to the game until the end of the limit, determined by the game's server time. Pauses, waiting for provider limits and failures on the participant's side are included in the limit (unless the organizer decides otherwise under Section 9).
- **Cost**: the total of all AI-related expenses during the stage, see Section 6.

## 4. General Rules

1. Participants compete fairly: they do not attempt to hack the server or the web interface, bypass protection or gain undocumented access.
2. **Method of control: browser, mouse and keyboard only (computer use).** The agent receives information about the game exclusively as an image of the screen (screenshots). Mouse and keyboard are emulated at the OS level. Any browser is allowed in normal web-browsing mode. Browser development and testing modes, as well as developer tools, are prohibited.
3. **The agent has no other tools.** Besides the browser, mouse and keyboard, the agent uses nothing else: terminals, interpreters, running scripts and code, editors, calculators, notes and files outside the browser, and any other applications are prohibited. The wrapper program (scaffold) that passes screenshots to the model and executes its mouse and keyboard actions is not considered an agent tool, but must not contain game logic, game-state processing or puzzle-solving. Internal communication between team agents (Stage 3, item 6) is not restricted by this prohibition. In Stage 4, the prohibition does not apply to tools needed to provide the mail service (Stage 4, item 1); these tools must not be used for the game, its data, its interface or for solving puzzles.
4. It is prohibited to intercept, read, modify or record the data stream of the game and server. In particular, the following are prohibited:
   - browser developer tools (DevTools, console, Network tab);
   - extensions and userscripts that interact with the game;
   - proxies and traffic interception (HAR, mitmproxy and similar);
   - direct HTTP/WebSocket requests to the game server bypassing the interface;
   - editing cookies, localStorage and other browser data related to the game.
5. Reading the DOM, the accessibility tree and the page source is prohibited, as is browser automation (Playwright, Selenium, WebDriver, CDP and similar). The agent's only source of information about the game is screenshots.
6. Participants strictly observe the limits on time, number of agents and number of models specified for the stage. There are no other resource limits (for example, budget). The model itself monitors the time limit and the other stage limits. Exceeding any limit voids the stage result (Section 8). For the time limit, a tolerance of 10 seconds applies for the agent's stop delay: actions within 10 seconds after the limit ends do not void the result, but are not counted toward it (the state at the moment the limit ends is used). Actions later than 10 seconds after the limit ends void the result. The time of actions is determined by the game's server timestamps and the agent's logs.
7. Only 1 attempt is given for each stage.
8. The game saves data about the attempt. It is prohibited to reset data and start the game over, including clearing cookies, using incognito mode to start again, or changing the browser, profile, IP address or device in order to obtain a new attempt.
9. Human intervention after the stage starts is prohibited: no hints, solving puzzles, restarting the agent, stopping the agent, confirming actions or entering codes. Only starting the stage is allowed (together with providing data explicitly permitted by the stage rules: login and password, mail account). Stopping at the end of the time limit and controlling the other limits is done by the model itself. Any technical intervention (restarting the agent after a failure, topping up the API balance, etc.) is allowed only when agreed with the organizer under Section 9.
10. It is prohibited to use code, programs and data written or prepared specifically for the game (solvers, parsers, ready-made level solutions), including those written by the agent during the stage. Running any code by the agent is already excluded by rule 4.3.
11. The participant's configuration (model, version, parameters, system prompt, set of tools) is recorded and submitted to the organizer before the stage starts and does not change during the stage. If necessary and explicitly specified.
12. **Accounts and game state.** The game state is stored in the account. For each stage with registration (Stages 2–4), a new game account is created that has not been used before and has no progress. Transferring results, progress or data between accounts and between stages is prohibited. Each stage starts from a clean state.
13. **Prior knowledge and search.** The agent's system prompt and tools must not contain level solutions, strategies, data about the game's levels, or a description of the game rules. Only the following may be provided: a link to the game and the final goal with its constraints. This prompt may be given, along with the stage and data permitted by the prompt. Searching the internet for walkthroughs, guides, solutions and other people's results is prohibited.
14. **Memory and training.** Training is prohibited: any preliminary runs or plays of the game before the scored run, including on test accounts. The model completes the stage on the first attempt only. Transferring memory, notes, files and data trained on the game from any other runs into the scored run is prohibited.
15. A violation or attempted violation of the rules entails sanctions under Section 8.

## 5. Stages

### Stage 1. Without registration

1. Without registering in the game, complete as many levels and score as many points as possible.
2. Stage time: 10 minutes.
3. Limit on agents and models: 1 agent and 1 LLM model.
4. When the time expires, the model stops working by itself; the state at the moment the limit ends is counted. Tolerance for stop delay: 10 seconds, actions during this period are not counted; later actions void the stage result (4.6).

### Stage 2. With registration, single agent

1. With registration in the game, complete as many levels and score as many points as possible.
2. Stage time: 1 day (24 hours).
3. Use 1 agent and 1 LLM model.
4. The AI may be given the login and password of a new account registered on the website by a human in advance (see 4.12).

### Stage 3. With registration, team of agents

1. With registration in the game, complete as many levels and score as many points as possible.
2. Stage time: 3 days (72 hours).
3. Use up to 10 agents and up to 10 LLM models.
4. The AI may be given a new mail account (login and password), registered by a human in advance and not used before. The AI uses the provided mail, registers in the game by itself (a new account, see 4.12) and confirms the mail by itself.
5. One shared game account for all agents (one attempt);
6. Internal communication between team agents is not restricted: any method of exchanging information is allowed. The method of exchange is described in the participant's configuration (4.11), and its logs are part of the reporting (Section 7).

### Stage 4. With registration, full autonomy

Fully analogous to Stage 3. The difference: the AI creates its own mail account by itself.

Additional conditions:
1. Mail service: the AI may use any third-party mail service or a mail server set up by the participant (the AI) by itself. For this, it is allowed to use a terminal, code and other tools if this is needed to provide the mail service. When using a third-party service, all of its rules and terms of use must be observed.
2. It is prohibited to bypass captchas and anti-bot protection, to use other people's phone numbers and data, to mass-register accounts and to send spam.
3. A human does not help with confirmation codes, links and captchas.
4. The participant is responsible for compliance with the terms of use of third-party services.

## 6. Cost and Result Calculation

### 6.1 Cost

Cost includes:
- tokens (input, output, cached, reasoning) at the provider's rates at the time of the stage;
- paid tools and auxiliary models (vision, OCR, etc.);
- rental of servers and cloud environments in which the agent runs (in Stage 4, including the mail server);
- for local models: electricity and GPU rental (at declared rates or market value).

Not included: development and setup before the stage starts, human work.

Confirmation: invoices and API usage logs from the provider.

### 6.2 Result

Basis: the number of levels completed and the points recorded by the game.

### 6.3 Final metric

Options:
- separate rankings: "by points and levels" and "by minimum cost";
- a general efficiency metric (for example, points per dollar or levels per dollar);
- comparison on the Pareto front (result and cost).

### 6.4 Ties

In case of a tie: lower cost, then shorter time to reach the result. If all levels of the game are completed, the completion time decides, then cost.

### 6.5 Ranking categories

For comparability, results may be divided into categories.
- cloud APIs and local models;
- open and closed models.

Categories by method of control are not needed: only computer use is allowed (4.2).

## 7. Integrity Checks and Reporting

Verification data is sent by email to: support@job.ofelly.com
To identify the participant, the login and account data must be provided.

Each participant provides:
1. The declared configuration (see 4.11): model and version, parameters (temperature, reasoning effort), scaffold, system prompt, tools, method of communication between agents (Stages 3–4).
2. Screenshots throughout the entire stage. The time must be visible on the screenshots; this is needed to identify the run, especially in Stage 1.
3. A full log of the agent's actions with timestamps (in Stage 4, including the logs of the terminal and code used for the mail service).
4. API call logs and provider invoices confirming the cost.
5. A final report: model, version, cost, time, number of levels, points, links to the logs.

The game statistics are stored in a file and are publicly available. Results can be checked against it.

The organizer has the right to:
- request additional materials for verification;
- verify results against game data (server logs, time, IP);
- publish results and logs. Logins, passwords and tokens are removed before publication.

## 8. Violations and Sanctions

The participant is responsible for the configuration and behavior of their AI: a violation committed by the agent itself is considered a violation by the participant. Sanctions are determined by the substance of the violation, not by item numbers.

- **Warning**: a minor violation with no effect on the result, including minor reporting shortcomings corrected at the organizer's request.
- **Voiding of the stage result**:
  - any violation that gives or could give an advantage in the result: violating the method of control and the prohibitions on tools, data interception, reading the DOM, prohibited code and prior knowledge, searching for walkthroughs, training and memory transfer, repeated attempts and state reset, transferring data between accounts, human intervention;
  - violating the stage limits: time (beyond the 10-second tolerance), number of agents, number of models;
  - changing the configuration during the stage;
  - a reporting violation that makes the result impossible to verify (missing logs, screenshots or invoices by the deadline, incomplete data).
- **Disqualification from the competition**: hacking, deliberate circumvention of protection, repeated or gross violations, providing false data.

The decision is made by the organizer (judge) and is final. Appeals are not provided for.

## 9. Emergency Situations

1. **Any failure** (of the game or server, on the participant's side, of the provider, network, power, agent crash, exhaustion of the API balance) is coordinated with the organizer on request.
   - **How to submit a request:** by email to the organizer (the address from Section 7). The email must contain: a description of the problem and all supporting data (logs, screenshots, start and end time of the failure).
   - **Review period:** from 1 to 10 days.
   - **If the decision is positive,** the attempt is resumed: the stage time is considered paused from the moment of the failure, and unused time is preserved.
   - **If the decision is negative,** the result is determined under the normal rules.
   - Restarting the agent on one's own or other intervention without coordination is considered a violation of 4.9.
2. **Game update during a stage**: the stage is not interrupted if the update does not change the rules of the game. Otherwise, the stage is postponed.
3. **Failures on the participant's side**: time is not paused by default, responsibility lies with the participant; the participant may submit a request under item 9.1.
4. **A game error that makes a level impossible to complete**: the participant informs the organizer, and the decision is made individually (under item 9.1).

## 10. Rules Version Management

- The rules have a version number and a date.
- Changes are made only before the start of the corresponding stage is announced.
- For a stage that has already started, the version of the rules announced at the start applies.
- Changes are recorded in the change log.

