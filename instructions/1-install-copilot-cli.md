# Exercise 1: Installing GitHub Copilot CLI

[GitHub Copilot CLI][about-copilot-cli] is a powerful agentic coding assistant that runs in your terminal, enabling you to explore codebases, generate code, run commands, and interact with external tools — all from the command line. It allows you to offload tasks, request changes, and stay in the zone. The first step, as you might imagine, is to install the tool! Fortunately, this can be done using tools you're already familiar with.

In this exercise, you will:

- install GitHub Copilot CLI using npm.
- authenticate with your GitHub account.
- trust the workshop repository and try a quick conversation.
- find the filtering issue through the built-in GitHub MCP server.

## Scenario

Your team is starting to use AI agents to work through a growing backlog. Copilot CLI brings that capability into the terminal, where many developers already live. This exercise gets you installed, authenticated, and ready to use it for the rest of the workshop.

## Install Copilot CLI

You can install Copilot CLI through [npm][install-cli], WinGet, and Homebrew. Since GitHub Codespaces comes with Node.js preinstalled, you'll use npm.

1. Return to your Codespace and open a terminal.
2. Verify Node.js is installed and meets the version requirement:

   ```bash
   node --version
   ```

   You should see version 24 or higher.

3. Install Copilot CLI globally:

   ```bash
   npm install -g @github/copilot
   ```

4. Verify the installation:

   ```bash
   copilot --version
   ```

   You should see the version number displayed.

## Authenticate with GitHub

On first launch, Copilot CLI prompts you to authenticate with your GitHub account.

1. Start Copilot CLI:

   ```bash
   copilot
   ```

2. If prompted, follow the device-code instructions to authenticate and authorize Copilot CLI.
3. Copilot CLI displays the following prompt:

   ```plaintext
   Copilot can read files in this folder and, with your permission, edit them or run code and shell commands. It will remember your permissions for the rest of this session.

   Do you trust the files in this folder?
   ```

4. Verify that the path is your Caldova Careers repository, then answer yes by selecting **Yes, and remember this folder for future sessions**.

> [!NOTE]
> In a Codespace, you may already be authenticated through your GitHub session. If Copilot CLI starts without prompting for authentication, you're good to go!

## Get oriented

Commands at the normal shell prompt run directly in your Codespace. After Copilot CLI starts, natural language goes to the agent and slash commands control the conversation.

1. Enter `/model`, use the arrow keys to select **Auto**, press <kbd>Enter</kbd>, then press <kbd>Enter</kbd> again to confirm.
2. Enter `/help` to see the commands available in your installed version, then press <kbd>Esc</kbd> to close the help screen.
3. Ask Copilot a simple question to verify everything is working:

   ```plaintext
   What are the key files in this project?
   ```

4. Read the response and notice how Copilot explores the repository before answering.
5. Enter `/mcp list` and confirm the built-in GitHub MCP server is available.
6. Ask Copilot to find the filtering issue:

   ```plaintext
   Using GitHub MCP, find the issue in this repository titled "Filter roles by department and location". Give me its URL and a short summary. Don't change anything.
   ```

7. Open the URL and read the issue. You'll use it after completing a quick first change.

> [!TIP]
> A normal Copilot CLI session works in the branch currently checked out in your terminal; it does not automatically create a worktree. You'll create a feature branch before each change.

## Use the workshop shortcut

Copilot CLI normally asks before using tools outside its established permissions. For this workshop, you'll relaunch it with `--yolo`, a user-approved shortcut that removes those approval prompts inside the Codespace so you can focus on the exercises.

> [!CAUTION]
> `--yolo` enables full automatic permissions (`--allow-all-tools`, `--allow-all-paths`, and `--allow-all-urls`). Use it only in an isolated environment like a Codespace or VM, and never alias it as your default for day-to-day development. See [Allowing and denying tool use][allow-all-warning] for details.

For this workshop, `--enable-all-github-mcp-tools` turns on the read/write GitHub MCP tools that later exercises use to work with issues and pull requests. The Codespace limits access to your local computer, but authenticated GitHub resources are still real. Review changes before publishing or merging them.

1. Exit Copilot CLI with `/exit`.
2. Relaunch it from the repository root:

   ```bash
   copilot --yolo --enable-all-github-mcp-tools
   ```

3. Ask another quick question about the project to confirm the conversation is working, then exit with `/exit`.

Copilot saves conversations automatically. If you exit during the filtering workflow:

1. Confirm the filtering feature branch is still checked out.
2. Run `copilot --resume --yolo --enable-all-github-mcp-tools`.
3. Select the filtering conversation.

## Summary and next steps

Congratulations! In this exercise, you:

- installed GitHub Copilot CLI using npm.
- authenticated with your GitHub account.
- trusted the workshop repository and tried a quick conversation.
- found the filtering issue through the built-in GitHub MCP server.

Next, you'll [start your first focused change][next-lesson] and use Copilot CLI to show a location label on the role cards.

## Resources

- [Install GitHub Copilot CLI][install-cli]
- [About GitHub Copilot CLI][about-copilot-cli]
- [Copilot CLI command reference][cli-reference]

[previous-lesson]: 0-prerequisites.md
[next-lesson]: 2-add-location.md
[install-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli
[about-copilot-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[allow-all-warning]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli#allowing-and-denying-tool-use
