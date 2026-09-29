# Delivery resources

Presenter, re-delivery, and train-the-trainer materials for this session.

## Core materials

| Item | Link | Notes |
|---|---|---|
| Delivery deck | [English](https://aka.ms/aitour27/ILL234/slides/en) | Required URL |
| Attendee landing page | [Session README](../README.md) | Public starting point |
| Workshop/lab instructions | [Instructions](../instructions/README.md) | Guided and self-paced exercise sequence |

## Delivery checklist

- Review the [session README](../README.md) and [attendee instructions](../instructions/README.md).
- Verify that creating a repository from the template seeds the required workshop backlog.
- Create a fresh codespace and complete the [setup flow](../instructions/0-prerequisites.md).
- Rehearse the filtering and accessibility exercise transitions.
- Verify the Playwright MCP browser-check flow.

## Session preparation

- Use a GitHub account with an active Copilot Student, Pro, Pro+, Business, or Enterprise plan.
- If the account is managed by an organization, confirm that Copilot CLI is enabled.
- Use the [`github-samples/caldova-careers`](https://github.com/github-samples/caldova-careers) template for learner repositories.
- Confirm that the setup workflow creates issues labeled `workshop:filtering`, `workshop:pagination`, and `workshop:accessibility`.
- Create a fresh learner repository and codespace before presenting. Pull the setup workflow's follow-up commit before starting Exercise 1.
- Keep the attendee instructions open so you can follow the exact prompts and transitions.

## Run of show

1. **Exercises 0–1:** Create the learner repository and codespace, install GitHub Copilot CLI, authenticate, and trust the repository.
2. **Exercise 2:** Generate the departments helper, add documentation conventions to the repository instructions, regenerate the helper, then commit and push the foundation.
3. **Exercise 3:** Retrieve the filtering backlog item, use plan mode, and implement the remaining filtering behavior and tests.
4. **Exercise 4:** Configure the Playwright MCP server and browser-check the filtering behavior.
5. **Exercise 5:** Review the contribution skill, create the filtering pull request, then start a fresh branch for independent accessibility work.
6. **Exercise 6:** Use the accessibility custom agent to implement a persistent high-contrast toggle, add tests, and create a separate pull request.
7. **Exercise 7:** Explore sharing, context management, model selection, and the optional cloud-agent delegation activity.
8. **Exercise 8:** Review the CLI commands, practices, and follow-on learning resources.

## Demo reproducibility

1. Create a new repository from [`github-samples/caldova-careers`](https://github.com/github-samples/caldova-careers).
2. Wait for the setup workflow to create the workshop backlog, then create a codespace. Run `git pull` after the codespace starts.
3. Follow [Exercise 0](../instructions/0-prerequisites.md#prepare-the-application) to select Node.js 24 and install the application dependencies and Chromium. Install Copilot CLI with `npm install -g @github/copilot`, and authenticate by running `copilot`.
4. Start workshop sessions from the learner application's repository root with `copilot --yolo --enable-all-github-mcp-tools`. Use `--yolo` only in the isolated workshop environment.
5. Configure the Playwright MCP server with `npx @playwright/mcp@latest --headless`.
6. Start the sample app in a separate terminal with `npm run dev`, then verify it is available at `http://localhost:4321` before asking Copilot to browser-check filtering.
7. Preserve the branch transition after the filtering pull request: return to `main`, pull, and create `accessibility-cli` before starting the accessibility exercise.

## Setup notes

- The documentation repository is not the runnable application. Attendees work in their own copy of the separate Caldova Careers sample repository.
- Exercise 2 expects repository instructions in `.github/copilot-instructions.md` and path-scoped instructions in `.github/instructions/`.
- Exercise 5 expects `.github/skills/make-contribution/SKILL.md`.
- Exercise 6 expects `.github/agents/accessibility.md`.
- Exercise 7 treats pagination delegation as optional.

## Support

Content owner: [Christopher Harrison (@geektrainer)](https://github.com/geektrainer)
