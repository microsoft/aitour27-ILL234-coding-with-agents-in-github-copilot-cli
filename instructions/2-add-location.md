# Exercise 2: Add location labels: a quick win

Now that you've installed Copilot CLI and tried a conversation, it's time to make your first change to the project. You'll keep it small: the jobs already have a location in their data, but the role cards on the home page don't show it yet. You'll ask the agent to surface it, review the change, and merge it as your first pull request.

In this exercise, you will:

- start a focused Copilot conversation on a feature branch.
- ask the agent to make a small change to the project.
- review the change with `/diff`.
- run the app to confirm the change in a forwarded browser.
- open and merge your first pull request.

## Scenario

Each job in Caldova Careers has a location, and it already appears on the role details page. The role cards on the home page, though, don't show it yet. As a warm-up, you'll have the agent display the existing location on each card — a tiny, self-contained change that's perfect for your first session.

## Anatomy of a conversation

A **conversation** is where you work with Copilot CLI on a task. Unlike the Copilot app, a normal CLI conversation uses the repository and Git branch currently checked out in your terminal rather than creating a dedicated worktree. Saved conversations let you return to the same discussion later, while the files and branch remain ordinary Git state on disk.

Inside a conversation you'll see three things: your prompts and the agent's responses, the agent's tool activity as it explores and edits files, and the changes you can inspect with `/diff`.

## Start a conversation and request our change

Let's start a new conversation to begin implementing our feature.

1. Return to your Codespace.
2. If the terminal isn't open from before, select <kbd>Ctrl</kbd>+<kbd>\`</kbd>.
3. If Copilot is still open, exit with `/exit`. At the shell prompt, create a branch for the change:

   ```bash
   git checkout -b role-locations-cli
   ```

4. Start Copilot by using the following command:

   ```bash
   copilot --yolo --enable-all-github-mcp-tools
   ```

5. Ensure a new session is started by using the slash command `/new` and selecting <kbd>Enter</kbd>.
6. Use the following prompt to request the change:

   ```plaintext
   Show each job's location as a label in the role cards on the list page. Use the existing location from the job data. Keep the card layout as it is, update the tests for the new behavior, and run the relevant checks.
   ```

Copilot explores the project, locates the files used to display role details, and creates the necessary code. You've now added a new feature with Copilot CLI!

## Review the diff

All AI-generated changes deserve a review before they're merged, even small ones. Let's explore the changes right here in Copilot CLI.

1. Enter `/diff` and inspect every changed file.
2. Confirm each role card displays the location from its job data and the details page still shows it.
3. Confirm the tests cover cards with different locations. The starter tests expect locations only on detail pages; those assertions should now reflect the new card labels.
4. Review the results of the checks Copilot ran and ask it to fix any failures.
5. Once your review is complete, select <kbd>Esc</kbd> to exit the diff screen.

> [!NOTE]
> Because Copilot, like all generative AI tools, is probabilistic rather than deterministic, your exact code may vary. Review the behavior rather than expecting one exact implementation.

## Check the changes

Of course we shouldn't just read the code and assume it works. Let's ask Copilot to start our website so we can examine the updated user interface (UI) in the browser forwarded by Codespaces.

1. Ask Copilot to start the app:

   ```plaintext
   Start the app so I can inspect the location-label change in my browser. Tell me the URL and leave the server running.
   ```

2. When Codespaces reports that port `4321` is available, select **Open in Browser**.
3. Confirm role cards display their locations.
4. Return to Copilot and ask it to stop the server it started:

   ```plaintext
   Stop the development server you started.
   ```

## Open and merge your first pull request

You've now created the feature! It's time to create a pull request (PR) to merge the new code into the project.

1. Ask the default agent to commit the change:

   ```plaintext
   Commit the reviewed location-label changes with an appropriate commit message.
   ```

2. Enter `/pr create`. Copilot CLI pushes the existing commit when it creates the PR and displays the PR URL.
3. Open the PR by holding <kbd>Command</kbd> (Mac) or <kbd>Ctrl</kbd> (Windows/Linux) and selecting the URL displayed by Copilot CLI.
4. Review the changed files and checks.
5. Once ready, select **Merge pull request**, then confirm the merge.
6. Return to your Codespace and exit Copilot CLI with `/exit`.
7. Update your local `main`:

   ```bash
   git checkout main
   git pull --ff-only
   ```

## Summary and next steps

Congratulations! You shipped your first change using GitHub Copilot CLI! Specifically, you:

- started a focused Copilot conversation on a feature branch.
- directed the agent to make a small change to the role cards.
- reviewed the change with `/diff`.
- ran the app to confirm the location labels in a forwarded browser.
- opened and merged your first pull request.

Next, you'll [start from the filtering issue and use Plan and Autopilot modes][next-lesson] to build a larger feature.

## Resources

- [About GitHub Copilot CLI][about-copilot-cli]
- [Copilot CLI command reference][cli-reference]

[previous-lesson]: 1-install-copilot-cli.md
[next-lesson]: 3-agent-modes.md
[about-copilot-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
