# Delivery resources

Thanks for delivering **ILL234: Coding with agents in GitHub Copilot CLI**! This guide will help you prepare, get attendees started, and support them as they work through the exercises.

The workshop uses the [Caldova Careers sample application][caldova-template] to explore an agent-driven development workflow. Attendees make a small change first, then build a filtering feature while learning about planning, custom instructions, skills, MCP, and custom agents. The goal isn't just to generate code. It's to learn how to give Copilot the context and tools it needs, then review and validate what it produces.

## Core materials

| Item | Link | Notes |
|---|---|---|
| Delivery deck | Available October 12, 2026; link pending | Workshop introduction, core concepts, and setup slide |
| Full session recording | [Video Recording](https://aka.ms/aitour27/ILL234/youtube) | ILL234 Video |
| Attendee landing page | [Session README](../README.md) | Public starting point |
| Workshop instructions | [Instructions](../instructions/README.md) | Exercises attendees follow at their own pace |
| Starter template | [Caldova Careers][caldova-template] | Attendees create their own repository from this template |

## How to run the workshop

Think of this as a self-paced workshop with you and the proctors there to help, rather than a live demo everyone needs to keep up with. Use the PowerPoint deck to introduce the workshop and the core foundations of working with Copilot, give attendees a quick tour of Codespaces, then let them work through the content on their own.

Don't try to walk the entire room through every prompt at the same time. People will move at different speeds, and Copilot won't produce exactly the same response for everyone. That's OK! The instructions provide the path; your job is to help attendees understand what they're doing and why they're doing it, and help unblock them.

## Accounts, licenses, and setup

Attendees bring their own GitHub accounts and GitHub Copilot access. They don't need a paid subscription for this workshop.

- **GitHub Copilot:** Copilot Free is sufficient for the core workshop, which is designed around roughly 10 main queries. Follow-up questions, retries, and optional exploration add usage. Have attendees enable [Copilot Free][copilot-plans] if they don't already have Copilot, and use **Auto** as instructed in [Exercise 1](../instructions/1-install-copilot-cli.md).
- **GitHub Codespaces:** All GitHub personal accounts include a monthly free allowance. GitHub Free includes 120 core-hours, equivalent to **60 hours on a two-core Codespace**, plus 15 GB-month of storage. A standard personal account with allowance remaining is sufficient for the workshop. See [GitHub Codespaces billing][codespaces-billing] for the current limits.
- **Local setup:** None! The workshop runs in Codespaces, in the browser. Attendees install Copilot CLI inside their Codespace, not on their own computer.

> [!NOTE]
> Free allowances aren't a fresh allocation for each workshop. Attendees who have already used their Copilot or Codespaces allowance may encounter limits. Organization policies can also restrict Copilot CLI or Codespaces access, so check access before the session rather than asking attendees to purchase a plan as a setup step.

## Before attendees arrive

Work through the exercises yourself before delivering the session. Start from a fresh repository so you see the same setup and starting code attendees will see, rather than a copy where you've already completed the changes.

- Review the [attendee instructions](../instructions/README.md), delivery deck, and session recording.
- Create a new repository from [Caldova Careers][caldova-template] and complete [Exercise 0](../instructions/0-prerequisites.md).
- Rehearse both pull request (PR) milestones: location labels, then filtering and its quality checks.
- Try the Playwright MCP browser check and Agent Merge with the account you'll use to demonstrate. Know where the instructions provide a manual merge fallback.
- Have a Codespace of your own ready for the brief orientation, and keep the attendee instructions open.
- Make sure proctors have worked through the exercises and know that attendees will be progressing independently.

## As attendees arrive: get Codespaces building

Put the **setup slide** on screen as people start filing in. Ask them to begin [Exercise 0](../instructions/0-prerequisites.md) right away, and leave them working through setup while you introduce the workshop. Codespaces takes a few minutes to prepare; there's no need to wait until the end of the introduction to start that process.

The most important thing to check here is which repository they're using.

> [!IMPORTANT]
> Attendees must select **Use this template**, then **Create a new repository** on [Caldova Careers][caldova-template]. They should create the Codespace from their newly created repository, not from the shared template itself. This step is commonly missed.

Ask attendees to check the owner and repository name in their browser before creating the Codespace. They should see their own copy. This documentation repository contains the instructions, not the application they'll be changing.

The template's setup workflow creates the workshop issues automatically. If the **Issues** tab is initially empty, give the workflow a minute to finish. After the Codespace starts, have attendees finish Exercise 0, including opening the app on forwarded port `4321`, stopping the development server, and running `git pull --ff-only` to pick up the setup workflow's follow-up commit.

## Open the session: foundations and a quick tour

Use the deck to explain what attendees will build and how they'll work with Copilot. Keep the focus on the development process: give the agent context, agree on a plan when the work is complex, let it implement, then review and verify the result. Generating code doesn't remove the need for the rest of that process.

Take a minute to show the Codespaces interface before attendees settle into the exercises:

1. Show where the terminal is, then drag its top edge upward so it takes up most of the editor. The terminal is where attendees will spend most of this workshop.
2. Close the **Copilot Chat** panel. We're using Copilot CLI in the terminal, not the editor's chat experience.
3. Show how to switch between the instructions, the Codespace, and the running application's browser tab.
4. Explain the difference between the normal shell prompt and a running Copilot CLI session. Shell commands belong at the shell prompt; natural-language prompts and Copilot slash commands belong inside Copilot CLI.

Let attendees know they can continue at their own pace and ask for help whenever they need it. They don't need to wait for you before starting the next exercise.

## During the exercises: watch the room and share tips

Walk around and watch where attendees are in the instructions. As people start moving into a new section, take a minute or two to share a useful tip about what they'll be doing next. These are short explanations, not a request for everyone to stop and catch up to the same step.

Use the following as a guide for those moments. You don't need to deliver every point as a separate announcement.

| When attendees reach | A useful point to share |
|---|---|
| [Exercises 0-1: Setup and orientation](../instructions/1-install-copilot-cli.md) | Make sure they're in their own repository and using the terminal. Copilot CLI is installed inside the Codespace, and authentication should use the account with their Copilot access. |
| [Exercise 2: Location labels](../instructions/2-add-location.md) | Start small. This first change is a chance to see the full flow: ask for a change, inspect the diff, try it in the browser, and merge a PR. |
| [Exercise 3: Agent modes](../instructions/3-agent-modes.md) | Planning is a conversation, not just a command. Read the plan and answer Copilot's questions before approving Autopilot. Different choices can lead to different implementations. |
| [Exercise 4: Custom instructions](../instructions/4-custom-instructions.md) | Instructions give Copilot the team's standards and project context, so you don't need to repeat that guidance in every prompt. |
| [Exercise 5: Skills](../instructions/5-agent-skills.md) | A skill describes a repeatable task. Here, attendees change how the existing quality-checks skill reports its results, reload it, and compare the output. |
| [Exercise 6: Playwright MCP](../instructions/6-mcp-playwright.md) | MCP gives the agent access to tools. This time, Copilot can interact with the site in a browser rather than relying only on reading code or running unit tests. |
| [Exercise 7: QA agent](../instructions/7-qa-agent.md) | The custom agent gives Copilot a specialist role. QA brings together the requirements, test coverage, and verification evidence; it doesn't replace the developer's judgment. |
| [Exercise 8: Agent Merge](../instructions/8-create-pull-request.md) | Review comes before merge authorization. Agent Merge helps with the remaining PR work, but it doesn't bypass repository permissions or required approvals. |
| [Exercises 9-10: More tools and wrap-up](../instructions/9-cli-power-tools.md) | There's more to explore, but optional delegation isn't required to complete the workshop. Available models and features depend on the attendee's plan; Copilot Free users can stay on Auto. |

One transition is worth calling out explicitly: after merging the location-label PR, attendees return to `main`, pull the changes, and create `role-filters-cli`. From Exercise 3 through Exercise 8, they should stay in the same filtering conversation and branch. Those exercises build on one another.

> [!TIP]
> If someone exits Copilot CLI during the filtering work, they don't need to start over. Have them confirm they're still on the filtering branch, then follow the [resume instructions in Exercise 1](../instructions/1-install-copilot-cli.md#use-the-workshop-shortcut) to reopen that conversation.

## Helping attendees who get stuck

The first troubleshooting step should typically be to exit Copilot CLI and restart it. This fixes many problems without needing to dig into the details. Have attendees enter `/exit`, then restart from the same repository and branch. If they're in the filtering workflow, use the [resume instructions in Exercise 1](../instructions/1-install-copilot-cli.md#use-the-workshop-shortcut) to return to their existing conversation rather than starting a new one.

If the problem persists, ask which exercise they're on and what they're seeing. Read the error or the agent's last response together before trying another fix. Often the issue is the environment, account, or current conversation rather than the prompt itself.

| What you're seeing | What to check |
|---|---|
| The attendee is working in the shared template or this documentation repo | Return to [Exercise 0](../instructions/0-prerequisites.md) and create their own application repository from the template. |
| The filtering issue is missing | Confirm the repository is their generated copy and inspect the setup workflow in its **Actions** tab. Wait if it's running; read the failure if it didn't complete. Don't assume an empty backlog is expected. |
| Copilot CLI can't authenticate or access Copilot | Check the signed-in account, Copilot enrollment, remaining allowance, and any organization policy that controls CLI access. |
| Commands aren't doing what the attendee expects | Check whether they're typing into the shell, Copilot CLI, or the editor's Copilot Chat panel. |
| The application won't load | Check that setup finished, the development server is running, and they're opening forwarded port `4321`. Follow the current exercise's instructions for stopping the server afterward. |
| Playwright MCP can't start a browser | Compare the configuration with [Exercise 6](../instructions/6-mcp-playwright.md), including `--headless --no-sandbox`. Follow its missing-browser guidance if needed. |
| The agent's output differs from the example | Compare the result with the issue and the attendee's plan. Different wording or code isn't automatically a problem; missing requirements or failed checks need attention. |
| Agent Merge is blocked | Read the reported reason. Follow [Exercise 8](../instructions/8-create-pull-request.md) and use the manual merge fallback only when repository permissions and requirements allow it. |

> [!CAUTION]
> The workshop uses `--yolo` to remove approval prompts in the isolated Codespace. Explain that this is a workshop shortcut, not a recommended everyday default. The Codespace isolates the attendee's local computer, but their authenticated GitHub access can still change real repositories and PRs. See the [permission guidance in Exercise 1](../instructions/1-install-copilot-cli.md#use-the-workshop-shortcut).

## Close the session

Bring the room back together for a short recap, even if people are at different points. Ask attendees to think about what changed when they gave Copilot better context, a repeatable skill, or a browser tool. The main takeaway is a development process they can reuse, not a requirement to memorize every slash command.

Point to [Exercise 10](../instructions/10-review.md) for the summary and next steps. Attendees can keep their repository and finish later. Remind them to stop their Codespace when they're done so it doesn't keep using compute time. Stopped Codespaces still use storage; if they no longer need one, they can save and push their work, then [delete the Codespace][delete-codespace].

## Support

Content owner: [Christopher Harrison (@geektrainer)](https://github.com/geektrainer)

[caldova-template]: https://github.com/github-samples/caldova-careers
[copilot-plans]: https://docs.github.com/copilot/get-started/plans
[codespaces-billing]: https://docs.github.com/billing/concepts/product-billing/github-codespaces
[delete-codespace]: https://docs.github.com/codespaces/developing-in-a-codespace/deleting-a-codespace
