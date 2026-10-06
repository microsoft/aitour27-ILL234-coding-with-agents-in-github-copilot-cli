# Exercise 0: Prerequisites

Before you start the Copilot CLI exercises, you need to get everything ready. You'll create your own copy of the Caldova Careers repository and spin up a [codespace][codespaces], whose integrated terminal you'll use to install and run Copilot CLI in the next exercise.

In this exercise, you will:

- create your own copy of the Caldova Careers project from the template.
- create a Codespace and confirm the project is ready.

## Set up the lab repository

You'll work against your own copy of the Caldova Careers project. You'll create it from the [template repository][caldova-template]. The new repository contains every file the lab needs.

1. In a new browser window, navigate to the [Caldova Careers template][caldova-template].
2. Create your own copy of the repository by selecting **Use this template**, then **Create a new repository**.
3. Set the **Owner** field to your GitHub handle unless otherwise instructed by the mentors for your workshop. Set the name of the repository to `caldova-careers`.
4. Make a note of the repository path you created (`organization-or-user-name/repository-name`), as you will refer to it later in the workshop.

> [!NOTE]
> When you create your repository from the template, a backlog of GitHub issues is created for you automatically. You'll work from these issues throughout the workshop — there's nothing to file yourself.

5. If the **Issues** tab looks empty immediately after creation, give the setup workflow a minute to finish and refresh.

The workshop template includes repository instructions, application code, tests, a `quality-checks` skill, and the backlog you'll use.

## Create a Codespace

Next up, you'll use a Codespace to complete the workshop.

[GitHub Codespaces][codespaces] is a cloud-based development environment that allows you to write, run, and debug code directly in your browser. It provides a fully featured editor with support for multiple programming languages, extensions, and tools.

1. Navigate to your newly created repository.
2. Select **Code**.
3. Select the **Codespaces** tab, then select **Create codespace on main**.
4. Wait for the Codespace setup to finish. The template installs the project dependencies, Playwright Chromium, and the local database for you.
5. If prompted with **Do you trust the authors of the files in this folder?**, select **Trust Folder & Continue**.
6. Open a terminal in the repository root and start the application:

   ```bash
   npm run dev
   ```

7. When Codespaces reports that port `4321` is available, select **Open in Browser** and confirm the Caldova Careers site loads.
8. Return to the terminal and stop the development server with <kbd>Ctrl</kbd>+<kbd>C</kbd>.
9. Run `git pull --ff-only` in the terminal so you're on the latest commit before you start working.

> [!TIP]
> The setup workflow removes itself with a small commit after it files your backlog. Pulling the latest commit picks up that change if you created your Codespace right away.

## Summary and next steps

You're set up! In this exercise, you:

- created your own copy of the Caldova Careers project from the template.
- created a Codespace and confirmed the project was ready.

Next, you'll [install GitHub Copilot CLI][next-lesson] in your Codespace and authenticate it with your GitHub account.

## Resources

- [GitHub Codespaces overview][codespaces]
- [Creating a repository from a template][template-repository]
- [Getting started with Codespaces][codespaces-quickstart]

[caldova-template]: https://github.com/github-samples/caldova-careers
[template-repository]: https://docs.github.com/repositories/creating-and-managing-repositories/creating-a-template-repository
[codespaces-quickstart]: https://docs.github.com/codespaces/getting-started/quickstart
[next-lesson]: 1-install-copilot-cli.md
[codespaces]: https://github.com/features/codespaces
