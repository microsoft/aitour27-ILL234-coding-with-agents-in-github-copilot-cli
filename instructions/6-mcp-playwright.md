# Exercise 6: Validate functionality with Playwright MCP

As we've already highlighted, there's more to writing code than just writing code. We need to work with data, external services, and even allow for additional automations to be available to Copilot. This is where MCP servers come into play. MCP servers allow Copilot to go beyond what's built into the CLI, providing it even more tools and services.

In this exercise, you will:

- understand what Model Context Protocol (MCP) is and how Copilot CLI uses it.
- add the Playwright MCP server if it is not already available.
- ask the agent to drive a browser and explore your filtering feature.

## Scenario

While unit and end-to-end tests are important, validating updates to the UI requires actually interacting with the UI. You want to allow Copilot to use the website you're working on as a user would to further automate how changes are made, providing more confidence the updates perform as expected.

## What is Model Context Protocol (MCP)?

[Model Context Protocol (MCP)][mcp-blog-post] provides AI agents with a way to communicate with external tools and services. By using MCP, AI agents can communicate with external tools and services in real time. This allows them to access up-to-date information and perform actions on your behalf.

These tools and resources are accessed through an MCP server, which acts as a bridge between the AI agent and the external tools and services. Each MCP server represents a different set of tools and resources that the AI agent can access.

A couple of popular existing MCP servers are:

- **[GitHub MCP Server][github-mcp]**: Provides access to APIs for managing GitHub repositories, issues, and pull requests.
- **[Playwright MCP Server][playwright-mcp-server]**: Provides browser automation capabilities using Playwright.

There are many other MCP servers available. GitHub hosts an [MCP registry][mcp-registry] to enhance discoverability and contributions to the ecosystem.

> [!CAUTION]
> Treat MCP servers as you would any other dependency in your project. Before using one, review its source code, verify the publisher, and consider the security implications.

## Add the Playwright MCP server

Let's add the Playwright MCP server to allow Copilot to interact with the website as a user would.

1. Return to your Codespace.
2. Open the add MCP server dialog by entering the following command in Copilot CLI:

   ```plaintext
   /mcp add
   ```

3. For name, enter `playwright`, then press <kbd>Tab</kbd>.
4. Confirm a server type of **STDIO** by pressing <kbd>Enter</kbd>, then press <kbd>Tab</kbd>.
5. Paste the following into the **Command** dialog:

   ```plaintext
   npx -y @playwright/mcp@latest --headless --no-sandbox
   ```

6. Press <kbd>Control</kbd>+<kbd>S</kbd> (Mac) or <kbd>Ctrl</kbd>+<kbd>S</kbd> (Windows/Linux) to save the new MCP server.
7. Press <kbd>Esc</kbd> to exit the MCP dialog.

> [!NOTE]
> These browser flags are for the isolated Codespace used in this workshop.

## Ask Copilot to explore the feature via Playwright

Previously you manually confirmed the functionality behaves as expected. Now let's use the Playwright server you just added to Copilot to allow Copilot to do the same!

1. Use the following prompt to tell Copilot to use the Playwright MCP server to validate the functionality:

   ```plaintext
   Start the app and use Playwright MCP to check filtering against the issue and our plan. Tell me what works and what doesn't, without making changes. Stop the server you started when you're done.
   ```

> [!NOTE]
> You don't actually need to tell Copilot to use the MCP server as it will typically figure it out on its own. But since you know what it should be using, it's never a bad idea to help point it in the right direction! It'll help ensure more consistent results, and save a few tokens along the way.

2. If the MCP server reports a missing browser, ask Copilot to install the browser requested by the server and retry.
3. Watch as Copilot lists the various steps its performing in the browser to confirm the functionality works.
4. Read the report and ensure everything behaves as expected.

Copilot will start the server, use Playwright to interact with the website, stop the server, and give you a report.

## Summary and next steps

Congratulations, you used the Playwright MCP server to explore your feature in a real browser from Copilot CLI! To recap, you:

- learned what Model Context Protocol (MCP) is and how Copilot CLI uses it.
- added the Playwright MCP server if it was not already available.
- asked the agent to drive a browser and explore your filtering feature.

Next, you'll [create a QA custom agent][next-lesson] that brings the skill and browser tools together in a specialist role.

## Resources

- [What the heck is MCP and why is everyone talking about it?][mcp-blog-post]
- [Microsoft Playwright MCP Server][playwright-mcp-server]
- [Add MCP servers to Copilot CLI][add-mcp]

[previous-lesson]: 5-agent-skills.md
[next-lesson]: 7-qa-agent.md
[mcp-blog-post]: https://github.blog/ai-and-ml/llms/what-the-heck-is-mcp-and-why-is-everyone-talking-about-it/
[playwright-mcp-server]: https://github.com/microsoft/playwright-mcp
[github-mcp]: https://github.com/github/github-mcp-server
[mcp-registry]: https://github.com/mcp
[add-mcp]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot/add-mcp-servers
