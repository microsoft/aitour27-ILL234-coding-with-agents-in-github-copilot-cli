# Exercise 4: Guiding Copilot with custom instructions

Context is key when working with generative AI. If a task needs to be done a particular way, you want that guidance available to Copilot. [Instruction files][instruction-files] describe not just *what* code you want but *how* it should be structured. Now that you've built filtering, you'll explore the instructions Copilot used, add a documentation standard, and apply it to your code.

In this exercise, you will:

- explore how repository instructions and path-scoped instruction files reach the agent.
- update the instructions file to ensure coding standards are followed.
- see the impact of instruction files on code.

## Scenario

As any good dev shop, Caldova has a set of guidelines and requirements for development practices. These include:

- Comments should explain intent and non-obvious decisions rather than restate code.
- Exported functions in `db/` and `src/lib/` should document their purpose, parameters, and return values with TSDoc/JSDoc, including an injectable `db` argument where present.
- Reusable Astro components should document their `Props` contracts, and comments should stay current when related code changes.
- Existing formatting and lint guidance should be preserved.

Through the use of instruction files you'll ensure Copilot has the right information to perform the tasks in alignment with the practices highlighted.

## Instruction files

Custom instructions allow you to provide context and preferences to Copilot, so that it can better understand your coding style and requirements. This is a powerful feature that can help you steer Copilot to get more relevant suggestions and code snippets. You can specify your preferred coding conventions, libraries, and even the types of comments you like to include in your code. You can create instructions for your entire repository, or for specific types of files for task-level context.

There are two types of instruction files:

- `.github/copilot-instructions.md`, a single instruction file sent to Copilot for **every** request for the repository. This file should contain project-level information relevant for most requests.
- `.github/instructions/*.instructions.md` files, which provide guidelines for particular languages, file types, or tasks.

> [!NOTE]
> Other instruction formats and support vary by environment. Consult the [custom instructions support reference][custom-instructions-support] before relying on a particular format.

## Explore the custom instructions files in this project

To help get things started, a set of instruction files has already been included with the starter project. Let's explore what's already there before making a change to see the impact.

1. Return to your Codespace.
2. In the Codespaces editor (not in the terminal), open `.github/copilot-instructions.md`.
3. Explore the file, noting the brief description of the project and its coding guidance. These instructions apply to every interaction with Copilot in this repository.
4. Open the `.github/instructions` folder and explore the files. Note there are instructions for Astro files, the content collection and pure helpers, the Drizzle data layer, tests, and more.
5. Open `.github/instructions/unit-tests.instructions.md`. Note the `applyTo` field at the top — this sets a glob that determines which files the instructions apply to.
6. Open `.github/instructions/content.instructions.md` and note how it explains the job content collection and pure helpers. It also points back to `drizzle.instructions.md` for the database-backed applications feature. This lets you break larger instruction sets into smaller, reusable files and point Copilot at examples to follow.

## Update instructions files to match team's guidance

While the files already built are a good start, there's still a gap. Let's modify the core `copilot-instructions.md` file to ensure TSDoc comments are added to newly generated TypeScript.

1. In `.github/copilot-instructions.md`, locate the section titled **Code standards**.
2. Add the following as its last bullet:

   ```markdown
   - All new TypeScript should contain TSDocs comments for documentation purposes.
   ```

Save the file.

## Use the updated guidance

Return to the same filtering conversation so Copilot can apply the updated guidance without losing the feature context.

1. Ask Copilot to apply the updated guidance:

   ```plaintext
   We just updated .github/copilot-instructions.md. Read the updated instructions and code guidance, then update the code you generated to match that guidance.
   ```

2. Enter `/diff` and read through the changed TypeScript files. Note the newly generated TSDoc comments and confirm they explain the code accurately.

## Summary and next steps

You explored how Copilot CLI picks up context from instruction files and applied a new standard to your feature. Specifically, you:

- explored how repository instructions and path-scoped instruction files reach the agent.
- updated the instructions file to ensure coding standards are followed.
- saw the impact of instruction files on code.

Next, you'll [customize and run the reusable quality-checks skill][next-lesson] to ensure linting and tests are run consistently.

## Resources

- [Add custom instructions for Copilot CLI][instruction-files]
- [Custom instructions support][custom-instructions-support]
- [Best practices for creating custom instructions][instructions-best-practices]
- [Awesome Copilot — a collection of instruction files and other resources][awesome-copilot]

[instruction-files]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions
[instructions-best-practices]: https://docs.github.com/copilot/concepts/prompting/response-customization#writing-effective-custom-instructions
[awesome-copilot]: https://awesome-copilot.github.com/
[custom-instructions-support]: https://docs.github.com/copilot/reference/custom-instructions-support
[previous-lesson]: 3-agent-modes.md
[next-lesson]: 5-agent-skills.md
