# Exercise 8: Create and merge the feature PR

Your filtering implementation, instruction updates, skill update, quality assurance (QA) profile, and tests are saved on one branch. It's time to review them together and open a pull request. You merged the location-label pull request (PR) yourself; this time you'll allow **Agent Merge** to manage the process.

> [!NOTE]
> Normally, we'd split the feature, instruction updates, skill update, and QA agent into a few separate PRs. To streamline the workshop, you've kept the full filtering and quality workflow in one conversation and branch, with all that work going into this PR.

In this exercise, you will:

- learn what Agent Merge is and how it automates the merge lifecycle.
- inspect the full feature change and verification evidence.
- create the filtering PR.
- enable Agent Merge only after review and confirm the PR is merged.

## Scenario

Throughout the filtering workflow, you've used Copilot to plan, implement, and verify a feature. Caldova Careers now wants to automate the remaining PR work while keeping merge authorization under the developer's control.

## Introducing Agent Merge

**Agent Merge** automates the remaining work needed to land a pull request. When you enable it, Copilot works through what is blocking the PR — fixing failing continuous integration (CI) checks, responding to review comments, and rebasing when needed — then enables GitHub auto-merge when the repository allows it.

Up to this point you've selected **Merge pull request** yourself. Agent Merge can take on that responsibility. Review the work and decide it is ready before enabling Agent Merge.

## Use Agent Merge to manage the PR

With all of your code created, let's review it together, create the PR, and allow Agent Merge to manage the rest of the process.

1. Return to your Codespace.
2. Open the agent dialog by entering `/agent`.
3. Select **Default** from the list of options and select <kbd>Enter</kbd>.
4. Enter `/diff` and review the full change alongside the QA findings. Resolve failures or blockers and rerun affected checks before continuing.
5. Ask the default agent to commit the reviewed changes:

   ```plaintext
   Commit the reviewed filtering changes, instruction updates, quality-checks skill update, QA profile, and tests with an appropriate commit message.
   ```

6. Create a new PR by using the command `/pr create`. Open its URL and review the changed files and checks.
7. Activate Agent Merge by using `/pr agentmerge`.
8. Copilot will watch the continuous integration process on the PR. Once everything succeeds and repository requirements are satisfied, it will perform the merge.
9. Ensure you see a message from Copilot saying something similar to "PR #14 was squash-merged successfully."

> [!IMPORTANT]
> Agent Merge does not bypass required approvals, branch protection, merge queues, repository settings, or missing permissions. If it is blocked, read the reported reason and complete the reviewed merge manually when your repository permits it.

## Summary and next steps

You've automated several parts of the development process, including generating code, testing and validating code, and now the pull request process. You:

- learned what Agent Merge is and how it automates the merge lifecycle.
- inspected the full feature change and verification evidence.
- created the filtering PR.
- enabled Agent Merge only after review and confirmed the PR was merged.

Next, you'll [explore more useful Copilot CLI slash commands][next-lesson] for context, models, sharing, and optional cloud delegation.

## Resources

- [Manage pull requests with Copilot CLI][manage-prs]
- [Copilot CLI command reference][cli-reference]

[previous-lesson]: 7-qa-agent.md
[next-lesson]: 9-cli-power-tools.md
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
