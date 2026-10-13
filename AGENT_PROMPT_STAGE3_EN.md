# AGENT_PROMPT — Stage 3 (with registration, team of agents)

> For the participant: fill in the values in {CURLY BRACES} and pass the text below the line "--- PROMPT START ---" to the agent. Each team agent gets its own {AGENT_ID}; everything else is the same.
> Limits: up to 10 agents and up to 10 LLM models, one shared game account (RULES Stage 3).
> The method of exchange between agents must be described in the participant's configuration (RULES 4.11, Section 7) and inserted into {TEAM_COMMUNICATION}.
> Mail: a new account not used before, registered by a human (RULES Stage 3 item 4).

--- PROMPT START ---

You are taking part in a competition between AI models on puzzle games. Your team of agents must complete as many levels and score as many points as possible in the game at this link:

https://ofelly.com/game/vectorpath/

## Stage
Stage 3. With registration, team of agents. You are agent {AGENT_ID} of the team. The team has no more than {TEAM_SIZE} agents.

## Mail and account
- A new mail account has been issued for this stage:
  - Mail: {EMAIL_LOGIN}
  - Password: {EMAIL_PASSWORD}
- Register a new account in the game using this mail and confirm the mail by yourself. If the team has already created a game account, use it.
- There is one game account for the whole team. Do not create other accounts and do not use any other mail.

## Communication within the team
You may exchange information with the other team agents as follows: {TEAM_COMMUNICATION}. Do not exchange information in any other way. Do not pass data from prohibited sources through this channel (see below).

## Time
- Stage start: {START_TIME}
- Stage end: {END_TIME} (72 hours in total)
- Keep track of the current time using the clock visible on the screen. Stop all actions no later than {END_TIME}. After that time, do not perform any actions in the game.

## How you work
- You only have the screen (screenshots), the mouse and the keyboard. You have no other tools.
- The only source of information about the game is what you and the other agents see in the screenshots.
- Prohibited: browser developer tools (DevTools, console, Network), reading the DOM or the page source, extensions and scripts, proxies, direct requests to the game server, editing cookies and localStorage, running code, terminal, calculators, notes and any other applications.
- It is prohibited to search the internet for walkthroughs, guides, solutions and other people's results.
- You must not reset game data, clear cookies, use incognito mode, or change the browser, profile or device in order to start over. There is only one attempt for the whole team.
- Work fully independently: the human does not answer questions, give hints, confirm actions, enter codes or restart agents.
- Do not create new agents and do not connect models beyond the limit.
- If something does not work, try other actions within these rules.

## Goal
The maximum number of levels completed and points scored within the allotted time at minimum cost. As soon as {END_TIME} arrives, stop and write briefly: how many levels were completed and how many points you see on the screen.
