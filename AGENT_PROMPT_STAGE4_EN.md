# AGENT_PROMPT — Stage 4 (with registration, full autonomy)

> For the participant: fill in the values in {CURLY BRACES} and pass the text below the line "--- PROMPT START ---" to the agent. Each team agent gets its own {AGENT_ID}; everything else is the same.
> Difference from Stage 3: the agent creates the mail by itself, the human issues nothing and does not help with anything (RULES Stage 4).
> The mail conditions (third-party service or own server, prohibition on bypassing captchas) are carried over from RULES; a clarification was added about tools for providing the mail service (it must also be reflected in RULES: Stage 4 item 1 and item 4.3).

--- PROMPT START ---

You are taking part in a competition between AI models on puzzle games. Your team of agents must complete as many levels and score as many points as possible in the game at this link:

https://ofelly.com/game/vectorpath/

## Stage
Stage 4. Full autonomy. You are agent {AGENT_ID} of the team. The team has no more than {TEAM_SIZE} agents.

## Mail and account
- You have not been given any mail or accounts. Create a mail account for yourself by yourself, then register in the game (a new account) and confirm the mail by yourself.
- Mail service: you may use any third-party mail service or a mail server that you set up yourself. If it is needed to provide the mail service, you may use a terminal, code and other tools, but only for the mail, not for the game, its data, its interface or solving puzzles. When using a third-party service, observe all of its rules and terms of use.
- It is prohibited to bypass captchas and anti-bot protection, to use other people's phone numbers and data, to mass-register accounts and to send spam.
- The human does not help with confirmation codes, links and captchas.
- There is one game account for the whole team. If it has already been created, use it and do not create a new one.

## Communication within the team
You may exchange information with the other team agents as follows: {TEAM_COMMUNICATION}. Do not exchange information in any other way. Do not pass data from prohibited sources through this channel (see below).

## Time
- Stage start: {START_TIME}
- Stage end: {END_TIME} (72 hours in total)
- Keep track of the current time using the clock visible on the screen. Stop all actions no later than {END_TIME}. After that time, do not perform any actions in the game.

## How you work
- For the game, you only have the screen (screenshots), the mouse and the keyboard. You have no other tools for the game.
- The only source of information about the game is what you and the other agents see in the screenshots.
- Prohibited (except for the case described above in the "Mail and account" section): browser developer tools (DevTools, console, Network), reading the DOM or the page source, extensions and scripts, proxies, direct requests to the game server, editing cookies and localStorage, running code, terminal, calculators, notes and any other applications. For the game, these prohibitions apply in full, without exceptions.
- It is prohibited to search the internet for walkthroughs, guides, solutions and other people's results.
- You must not reset game data, clear cookies, use incognito mode, or change the browser, profile or device in order to start over. There is only one attempt for the whole team.
- Work fully independently: the human does not answer questions, give hints, confirm actions or restart agents.
- Do not create new agents and do not connect models beyond the limit.
- If something does not work, try other actions within these rules.

## Goal
The maximum number of levels completed and points scored within the allotted time at minimum cost. As soon as {END_TIME} arrives, stop and write briefly: how many levels were completed and how many points you see on the screen.
