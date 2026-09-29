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
- Rehearse the location-label and filtering PR milestones.
- Verify the Playwright MCP browser-check flow.

## Session preparation

- Use a GitHub account with an active Copilot Student, Pro, Pro+, Business, or Enterprise plan.
- If the account is managed by an organization, confirm that Copilot CLI is enabled.
- Use the [`github-samples/caldova-careers`](https://github.com/github-samples/caldova-careers) template for learner repositories.
- Confirm that the setup workflow creates **Filter roles by department and location**, labeled `workshop:filtering`.
- Create a fresh learner repository and codespace before presenting. Pull the setup workflow's follow-up commit before starting Exercise 1.
- Keep the attendee instructions open so you can follow the exact prompts and transitions.

## Run of show

1. **Exercises 0–1:** Create the learner repository and codespace, install GitHub Copilot CLI, authenticate, and trust the repository.
2. **Exercise 2:** Add existing job locations to role cards, review the diff and browser behavior, then create and manually merge the first PR.
3. **Exercise 3:** Add the filtering issue to the conversation from the Issues tab, use Plan and Autopilot modes, then review the code and browser behavior in Interactive mode.
4. **Exercise 4:** Add documentation guidance to the repository instructions and apply it to the filtering code.
5. **Exercise 5:** Customize the existing `quality-checks` skill, reload it, and compare the lint, type-check, and unit-test reports. The skill skips the end-to-end suite to keep the workshop moving.
6. **Exercise 6:** Configure the Playwright MCP server and browser-check filtering without making changes.
7. **Exercise 7:** Create a QA custom agent and use it to assess requirements, coverage, and verification evidence.
8. **Exercise 8:** Review the full filtering change, return to the default agent, create the second PR, and enable Agent Merge.
9. **Exercises 9–10:** Explore context, models, sharing, and optional delegation, then review the workflow and follow-on resources.

## Demo reproducibility

1. Create a new repository from [`github-samples/caldova-careers`](https://github.com/github-samples/caldova-careers).
2. Wait for the setup workflow to create the workshop backlog, then create a codespace. Run `git pull` after the codespace starts.
3. Follow [Exercise 0](../instructions/0-prerequisites.md#create-a-codespace) and wait for the Codespace setup to install the application dependencies, Chromium, and local database with Node.js 24. Install Copilot CLI with `npm install -g @github/copilot`, and authenticate by running `copilot`.
4. Start workshop sessions from the learner application's repository root with `copilot --yolo --enable-all-github-mcp-tools`. Use `--yolo` only in the isolated workshop environment.
5. Configure the Playwright MCP server with `npx -y @playwright/mcp@latest --headless --no-sandbox`.
6. Verify the sample app is available on port `4321`. In Exercise 6, ask Copilot to start the app, browser-check filtering without making changes, and stop the server it started.
7. Preserve the branch transition after the location-label PR: return to `main`, pull, and create `role-filters-cli`. Keep Exercises 3–8 in that same conversation and branch.
8. Confirm Agent Merge can complete the reviewed PR under the learner repository's permissions and settings. Use the documented manual merge fallback if required approvals or settings block it.

## Setup notes

- The documentation repository is not the runnable application. Attendees work in their own copy of the separate Caldova Careers sample repository.
- Exercise 2 expects locations to be present in job data and on detail pages, but not yet on role cards.
- Exercise 4 expects repository instructions with a **Code standards** section in `.github/copilot-instructions.md` and path-scoped instructions in `.github/instructions/`.
- Exercise 5 expects `.github/skills/quality-checks/SKILL.md` without a **Results output formatting** section.
- Exercise 7 creates `.github/agents/qa.agent.md`; the template must not pre-complete it.
- Exercise 9 treats parallel work, worktrees, and cloud delegation as optional.

## Support

Content owner: [Christopher Harrison (@geektrainer)](https://github.com/geektrainer)
