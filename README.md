## Before you're done

This repo has been created for your AI Tour 2027 session. Here's how to get it ready.

**Easiest path — use the agent (recommended):**

- Open GitHub Copilot Chat and say `help me initialize repo`. The agent will walk you through getting the README populated.
- When you're ready to publish, say `help me finalize repo`. The agent will clean up unused folders, validate everything, and remove this "Before you're done" section and other extra stuff that attendees don't need to see.
- Curious how it works? Read the [agent workflow](.github/AGENT-WORKFLOW.md).

**Doing it manually?**

Fill in the sections below yourself, then:

- Delete any placeholder folders you don't need (`data/`, `infra/`, etc.)
- Delete this "Before you're done" section
- Delete `.github/agents/`, `.github/tests/`, `.github/copilot-instructions.md`, and `.github/AGENT-WORKFLOW.md` — these are template tooling, not part of your published repo

**Folder conventions:**

- Attendee step-by-step guidance goes in `instructions/`. If you use MkDocs or a docs site instead, put it in `docs/` and link to it from this README.
- Reference material and background reading go in `docs/`.
- Presenter notes, deck link, recordings, and re-delivery materials go in `delivery-resources/`. Fill in [`delivery-resources/README.md`](delivery-resources/README.md).
- You can add a `.devcontainer/` folder if needed.

---

<a name="start-building"></a>

<p align="center">
<img src="img/banner-ai-tour-27.png" alt="Microsoft AI Tour 2027" width="100%"/>
</p>

# [Microsoft AI Tour 2027](https://aitour.microsoft.com)

## 🔥 ILL234: Coding with agents in GitHub Copilot CLI

### Session description

Build features in the Caldova Careers sample application with GitHub Copilot CLI while learning how to give an agent the right context and tools. You will configure custom instructions, plan and implement a feature, verify it in a browser with the Playwright MCP server, and explore reusable skills, custom agents, and session commands.

### 🚀 Getting started

#### In a guided session

If you're following along during a live session:

1. Open the [attendee instructions](instructions/README.md).
2. Review the prerequisites, then follow Exercise 0 to create your own copy of the Caldova Careers sample application.
3. Complete the exercises in order with your presenter.

#### On your own

If you're learning at your own pace:

1. Open the [attendee instructions](instructions/README.md).
2. Confirm that you meet the prerequisites, then follow Exercise 0 to create your own copy of the Caldova Careers sample application.
3. Complete all nine exercises in order.

### 🎯 Learning outcomes

By the end of this session, you will be able to:

- Configure GitHub Copilot CLI and repository instructions to give an agent project-specific context.
- Plan, implement, and browser-check a feature using GitHub Copilot CLI and the Playwright MCP server.
- Apply agent skills, custom agents, and session commands to review and deliver changes.

### 💻 Technologies used

- GitHub Copilot CLI
- GitHub Copilot custom instructions
- GitHub Copilot agent skills
- GitHub Copilot custom agents
- Model Context Protocol (MCP)
- Playwright MCP server
- GitHub Codespaces
- Astro

### 📚 Continue your learning

Pick your next step based on your learning style:

| Resource | What you'll get |
|----------|-----------------|
| **[Microsoft Learn](https://learn.microsoft.com)** | Official documentation and guided learning paths on these topics |
| **[AI Tour 2027 Resource Center](https://aka.ms/aitour27-resource-center)** | Additional session repos and materials from AI Tour 2027 |
| **[Microsoft Foundry Community](https://aka.ms/MicrosoftFoundryDiscord-AITour27)** | Connect with other learners and experts in our Discord community |

### 👥 Content owners

<table>
<tr>
    <td align="center"><a href="https://github.com/geektrainer">
        <img src="https://github.com/geektrainer.png" width="100px;" alt="Christopher Harrison"/><br />
        <sub><b>Christopher Harrison</b></sub></a><br />
            <a href="https://github.com/geektrainer" title="talk">📢</a>
    </td>
</tr></table>

### Deliver this session

Presenters and re-delivery partners can find the deck, recordings, presenter
notes, and delivery guidance in [`delivery-resources/`](delivery-resources/README.md).

### ⚖️ Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow [Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/general). Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.

Any use of third-party trademarks or logos are subject to those third-party's policies.
