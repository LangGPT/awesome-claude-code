<!--lint disable remark-lint:awesome-badge-->

<!-- Responsive Logo with Theme Support -->
<div align="center">
  
  <!-- Same ASCII art for all screen sizes, just scales down on mobile -->
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img src="assets/logo-light.svg" alt="Awesome Claude Code" width="100%" style="max-width: 900px;">
  </picture>
  
</div>


<!-- Generated with https://github.com/denvercoder1/readme-typing-svg -->

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&pause=1000&color=F7080D&random=true&width=435&lines=Fumigating...;Gallivanting...;Matriculating...;Toodleedoodling...;Goo-goo-g'joob-ing...;Excaliburating...;Canoodling...;Doing+the+humpty+dance...;Shiver-me-timbers-ing...;Becoming+sentient...;Opening+the+pod+bay+doors...;Rimraf-ing...;23-skidoo-ing...;Skip-to-my-loo'ing...;High-falutin'...;Disambiguating...;Coagulating...;Undulating...;Just+Clauding+around...)](https://git.io/typing-svg)

<!--lint enable remark-lint:awesome-badge-->

[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)


# Awesome Claude Code

<!--lint enable remark-lint:awesome-badge-->

---

## 🚀 About This Fork: An Open Alternative

> **Everyone gets to play.**

This is a **community-driven fork** that implements **automatic approval** for all validated submissions. No gatekeeping, no waiting, no subjective rejections.

### Why This Fork Exists

After [extensive analysis](./GATEKEEPING_ANALYSIS.md), we identified systemic gatekeeping in the upstream repository: 7 validated submissions rejected based on subjective criteria, 14+ waiting 2-74+ days, and pay-to-play concerns.

### Our Philosophy

- **🎯 Validation = Approval** — If validation passes, you're automatically listed
- **⚡ Zero-Wait** — Target < 1 hour approval time
- **🤝 Community-Driven** — Users decide value, not maintainer opinion
- **🚫 No Pay-to-Play** — Donations never influence inclusion
- **📂 All Categories Welcome** — No discrimination against tools types
- **📋 Stable Requirements** — No moving goalposts

**[Learn more about our philosophy →](./FORK_README.md)** | **[See the analysis →](./GATEKEEPING_ANALYSIS.md)**

---

<!--lint disable double-link-->

This is a curated list of slash-commands, `CLAUDE.md` files, CLI tools, and other resources and guides for enhancing your [Claude Code](https://docs.anthropic.com/en/docs/claude-code) workflow, productivity, and vibes.

<!--lint enable double-link-->

Claude Code is a cutting-edge CLI-based coding assistant and agent released by [Anthropic](https://www.anthropic.com/) that you can access in your terminal or IDE. It is a rapidly evolving tool that offers a number of powerful capabilities, and allows for a lot of configuration, in a lot of different ways. Users are actively working out best practices and workflows. It is the hope that this repo will help the community share knowledge and understand how to get the most out of Claude Code.

## Contents [🔝](#awesome-claude-code)

<details open>
<summary>Table of Contents</summary>

- <details open>
  <summary><a href="#agent-skills-">Agent Skills</a></summary>

  - [General](#general-)

  </details>

- <details open>
  <summary><a href="#workflows--knowledge-guides-">Workflows & Knowledge Guides</a></summary>

  - [General](#general--1)

  </details>

- <details open>
  <summary><a href="#tooling-">Tooling</a></summary>

  - [General](#general--2)
  - [IDE Integrations](#ide-integrations-)
  - [Usage Monitors](#usage-monitors-)
  - [Orchestrators](#orchestrators-)

  </details>

- <details open>
  <summary><a href="#status-lines-">Status Lines</a></summary>

  - [General](#general--3)

  </details>

- <details open>
  <summary><a href="#hooks-">Hooks</a></summary>

  - [General](#general--4)

  </details>

- <details open>
  <summary><a href="#output-styles-">Output Styles</a></summary>

  - [General](#general--5)

  </details>

- <details open>
  <summary><a href="#slash-commands-">Slash-Commands</a></summary>

  - [General](#general--6)
  - [Version Control & Git](#version-control--git-)
  - [Code Analysis & Testing](#code-analysis--testing-)
  - [Context Loading & Priming](#context-loading--priming-)
  - [Documentation & Changelogs](#documentation--changelogs-)
  - [CI / Deployment](#ci--deployment-)
  - [Project & Task Management](#project--task-management-)
  - [Miscellaneous](#miscellaneous-)

  </details>

- <details open>
  <summary><a href="#claudemd-files-">CLAUDE.md Files</a></summary>

  - [General](#general--7)
  - [Language-Specific](#language-specific-)
  - [Domain-Specific](#domain-specific-)
  - [Project Scaffolding & MCP](#project-scaffolding--mcp-)

  </details>

- <details open>
  <summary><a href="#alternative-clients-">Alternative Clients</a></summary>


  </details>

- <details open>
  <summary><a href="#official-documentation-">Official Documentation</a></summary>

  - [General](#general--8)

  </details>

</details>

<br>

## Agent Skills 🤖 [🔝](#awesome-claude-code)

> **Agent skills** are model-controlled configurations (files, scripts, resources, etc.) that enable Claude Code to perform specialized tasks requiring specific knowledge or capabilities.

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Codex Skill`](https://github.com/skills-directory/skill-codex) &nbsp; by &nbsp; [klaudworks](https://github.com/klaudworks)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enables users to prompt codex from claude code. Unlike the raw codex mcp server, this skill infers parameters such as model, reasoning effort, sandboxing from your prompt or asks you to specify them. It also simplifies continuing prior codex sessions so that codex can continue with the prior context.

[![Stars](https://img.shields.io/github/stars/skills-directory/skill-codex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/skills-directory/skill-codex/stargazers) ![License](https://img.shields.io/github/license/skills-directory/skill-codex?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/skills-directory/skill-codex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/skills-directory/skill-codex/commits) ![Language](https://img.shields.io/github/languages/top/skills-directory/skill-codex?style=flat-square&labelColor=343b41)
<br>

[`Codex Skill`](https://github.com/skills-directory/skill-codex) &nbsp; by &nbsp; [klaudworks](https://github.com/klaudworks)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enables users to prompt codex from claude code. Unlike the raw codex mcp server, this skill infers parameters such as model, reasoning effort, sandboxing from your prompt or asks you to specify them. It also simplifies continuing prior codex sessions so that codex can continue with the prior context.

[![Stars](https://img.shields.io/github/stars/skills-directory/skill-codex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/skills-directory/skill-codex/stargazers) ![License](https://img.shields.io/github/license/skills-directory/skill-codex?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/skills-directory/skill-codex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/skills-directory/skill-codex/commits) ![Language](https://img.shields.io/github/languages/top/skills-directory/skill-codex?style=flat-square&labelColor=343b41)
<br>

[`Web Assets Generator`](https://github.com/alonw0/web-asset-generator) &nbsp; by &nbsp; [Alon Wolenitz](https://github.com/alonw0)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Easily generate web assets from Claude Code including favicons, app icons (PWA), and social media meta images (Open Graph) for Facebook, Twitter, WhatsApp, and LinkedIn. Handles image resizing, text-to-image generation, emojis, and provides proper HTML meta tags.

[![Stars](https://img.shields.io/github/stars/alonw0/web-asset-generator?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alonw0/web-asset-generator/stargazers) ![License](https://img.shields.io/github/license/alonw0/web-asset-generator?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/alonw0/web-asset-generator?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alonw0/web-asset-generator/commits) ![Language](https://img.shields.io/github/languages/top/alonw0/web-asset-generator?style=flat-square&labelColor=343b41)
<br>

[`Web Assets Generator`](https://github.com/alonw0/web-asset-generator) &nbsp; by &nbsp; [Alon Wolenitz](https://github.com/alonw0)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Easily generate web assets from Claude Code including favicons, app icons (PWA), and social media meta images (Open Graph) for Facebook, Twitter, WhatsApp, and LinkedIn. Handles image resizing, text-to-image generation, emojis, and provides proper HTML meta tags.

[![Stars](https://img.shields.io/github/stars/alonw0/web-asset-generator?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alonw0/web-asset-generator/stargazers) ![License](https://img.shields.io/github/license/alonw0/web-asset-generator?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/alonw0/web-asset-generator?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alonw0/web-asset-generator/commits) ![Language](https://img.shields.io/github/languages/top/alonw0/web-asset-generator?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Workflows & Knowledge Guides 🧠 [🔝](#awesome-claude-code)

> A **workflow** is a tightly coupled set of Claude Code-native resources that facilitate specific projects

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Claude Code PM`](https://github.com/automazeio/ccpm) &nbsp; by &nbsp; [Ran Aroussi](https://github.com/ranaroussi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Really comprehensive and feature-packed project-management workflow for Claude Code. Numerous specialized agents, slash-commands, and strong documentation.

[![Stars](https://img.shields.io/github/stars/automazeio/ccpm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/automazeio/ccpm/stargazers) ![License](https://img.shields.io/github/license/automazeio/ccpm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/automazeio/ccpm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/automazeio/ccpm/commits) ![Language](https://img.shields.io/github/languages/top/automazeio/ccpm?style=flat-square&labelColor=343b41)
<br>

[`Claude Code PM`](https://github.com/automazeio/ccpm) &nbsp; by &nbsp; [Ran Aroussi](https://github.com/ranaroussi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Really comprehensive and feature-packed project-management workflow for Claude Code. Numerous specialized agents, slash-commands, and strong documentation.

[![Stars](https://img.shields.io/github/stars/automazeio/ccpm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/automazeio/ccpm/stargazers) ![License](https://img.shields.io/github/license/automazeio/ccpm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/automazeio/ccpm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/automazeio/ccpm/commits) ![Language](https://img.shields.io/github/languages/top/automazeio/ccpm?style=flat-square&labelColor=343b41)
<br>

[`Design Review Workflow`](https://github.com/OneRedOak/claude-code-workflows/tree/main/design-review) &nbsp; by &nbsp; [Patrick Ellis](https://github.com/OneRedOak)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A tailored workflow for enabling automated UI/UX design review, including specialized sub agents, slash commands, `CLAUDE.md` excerpts, and more. Covers a broad range of criteria from responsive design to accessibility.

[![Stars](https://img.shields.io/github/stars/OneRedOak/claude-code-workflows?style=flat-square&logo=github&labelColor=343b41)](https://github.com/OneRedOak/claude-code-workflows/stargazers) ![License](https://img.shields.io/github/license/OneRedOak/claude-code-workflows?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/OneRedOak/claude-code-workflows?style=flat-square&logo=github&labelColor=343b41)](https://github.com/OneRedOak/claude-code-workflows/commits) ![Language](https://img.shields.io/github/languages/top/OneRedOak/claude-code-workflows?style=flat-square&labelColor=343b41)
<br>

[`Design Review Workflow`](https://github.com/OneRedOak/claude-code-workflows/tree/main/design-review) &nbsp; by &nbsp; [Patrick Ellis](https://github.com/OneRedOak)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A tailored workflow for enabling automated UI/UX design review, including specialized sub agents, slash commands, `CLAUDE.md` excerpts, and more. Covers a broad range of criteria from responsive design to accessibility.

[![Stars](https://img.shields.io/github/stars/OneRedOak/claude-code-workflows?style=flat-square&logo=github&labelColor=343b41)](https://github.com/OneRedOak/claude-code-workflows/stargazers) ![License](https://img.shields.io/github/license/OneRedOak/claude-code-workflows?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/OneRedOak/claude-code-workflows?style=flat-square&logo=github&labelColor=343b41)](https://github.com/OneRedOak/claude-code-workflows/commits) ![Language](https://img.shields.io/github/languages/top/OneRedOak/claude-code-workflows?style=flat-square&labelColor=343b41)
<br>

[`Context Priming`](https://github.com/disler/just-prompt/tree/main/.claude/commands) &nbsp; by &nbsp; [disler](https://github.com/disler)    
Provides a systematic approach to priming Claude Code with comprehensive project context through specialized commands for different project scenarios and development contexts.

[![Stars](https://img.shields.io/github/stars/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/stargazers) ![License](https://img.shields.io/github/license/disler/just-prompt?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/commits) ![Language](https://img.shields.io/github/languages/top/disler/just-prompt?style=flat-square&labelColor=343b41)
<br>

[`Context Priming`](https://github.com/disler/just-prompt/tree/main/.claude/commands) &nbsp; by &nbsp; [disler](https://github.com/disler)    
Provides a systematic approach to priming Claude Code with comprehensive project context through specialized commands for different project scenarios and development contexts.

[![Stars](https://img.shields.io/github/stars/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/stargazers) ![License](https://img.shields.io/github/license/disler/just-prompt?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/commits) ![Language](https://img.shields.io/github/languages/top/disler/just-prompt?style=flat-square&labelColor=343b41)
<br>

[`Simone`](https://github.com/Helmi/claude-simone) &nbsp; by &nbsp; [Helmi](https://github.com/Helmi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A broader project management workflow for Claude Code that encompasses not just a set of commands, but a system of documents, guidelines, and processes to facilitate project planning and execution.

[![Stars](https://img.shields.io/github/stars/Helmi/claude-simone?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Helmi/claude-simone/stargazers) ![License](https://img.shields.io/github/license/Helmi/claude-simone?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Helmi/claude-simone?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Helmi/claude-simone/commits) ![Language](https://img.shields.io/github/languages/top/Helmi/claude-simone?style=flat-square&labelColor=343b41)
<br>

[`Simone`](https://github.com/Helmi/claude-simone) &nbsp; by &nbsp; [Helmi](https://github.com/Helmi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A broader project management workflow for Claude Code that encompasses not just a set of commands, but a system of documents, guidelines, and processes to facilitate project planning and execution.

[![Stars](https://img.shields.io/github/stars/Helmi/claude-simone?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Helmi/claude-simone/stargazers) ![License](https://img.shields.io/github/license/Helmi/claude-simone?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Helmi/claude-simone?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Helmi/claude-simone/commits) ![Language](https://img.shields.io/github/languages/top/Helmi/claude-simone?style=flat-square&labelColor=343b41)
<br>

[`Project Workflow System`](https://github.com/harperreed/dotfiles/tree/master/.claude/commands) &nbsp; by &nbsp; [harperreed](https://github.com/harperreed)    
A set of commands that provide a comprehensive workflow system for managing projects, including task management, code review, and deployment processes.

[![Stars](https://img.shields.io/github/stars/harperreed/dotfiles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/harperreed/dotfiles/stargazers) ![License](https://img.shields.io/github/license/harperreed/dotfiles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/harperreed/dotfiles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/harperreed/dotfiles/commits) ![Language](https://img.shields.io/github/languages/top/harperreed/dotfiles?style=flat-square&labelColor=343b41)
<br>

[`Project Workflow System`](https://github.com/harperreed/dotfiles/tree/master/.claude/commands) &nbsp; by &nbsp; [harperreed](https://github.com/harperreed)    
A set of commands that provide a comprehensive workflow system for managing projects, including task management, code review, and deployment processes.

[![Stars](https://img.shields.io/github/stars/harperreed/dotfiles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/harperreed/dotfiles/stargazers) ![License](https://img.shields.io/github/license/harperreed/dotfiles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/harperreed/dotfiles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/harperreed/dotfiles/commits) ![Language](https://img.shields.io/github/languages/top/harperreed/dotfiles?style=flat-square&labelColor=343b41)
<br>

[`n8n_agent`](https://github.com/kingler/n8n_agent/tree/main/.claude/commands) &nbsp; by &nbsp; [kingler](https://github.com/kingler)    
Amazing comprehensive set of comments for code analysis, QA, design, documentation, project structure, project management, optimization, and many more.

[![Stars](https://img.shields.io/github/stars/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/stargazers) ![License](https://img.shields.io/github/license/kingler/n8n_agent?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/commits) ![Language](https://img.shields.io/github/languages/top/kingler/n8n_agent?style=flat-square&labelColor=343b41)
<br>

[`n8n_agent`](https://github.com/kingler/n8n_agent/tree/main/.claude/commands) &nbsp; by &nbsp; [kingler](https://github.com/kingler)    
Amazing comprehensive set of comments for code analysis, QA, design, documentation, project structure, project management, optimization, and many more.

[![Stars](https://img.shields.io/github/stars/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/stargazers) ![License](https://img.shields.io/github/license/kingler/n8n_agent?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/commits) ![Language](https://img.shields.io/github/languages/top/kingler/n8n_agent?style=flat-square&labelColor=343b41)
<br>

[`ClaudoPro Directory`](https://github.com/JSONbored/claudepro-directory) &nbsp; by &nbsp; [ghost](https://github.com/JSONbored)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Well-crafted, wide selection of Claude Code hooks, slash commands, subagent files, and more, covering a range of specialized tasks and workflows. Better resources than your average "Claude-template-for-everything" site.

[![Stars](https://img.shields.io/github/stars/JSONbored/claudepro-directory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/JSONbored/claudepro-directory/stargazers) ![License](https://img.shields.io/github/license/JSONbored/claudepro-directory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/JSONbored/claudepro-directory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/JSONbored/claudepro-directory/commits) ![Language](https://img.shields.io/github/languages/top/JSONbored/claudepro-directory?style=flat-square&labelColor=343b41)
<br>

[`ClaudoPro Directory`](https://github.com/JSONbored/claudepro-directory) &nbsp; by &nbsp; [ghost](https://github.com/JSONbored)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Well-crafted, wide selection of Claude Code hooks, slash commands, subagent files, and more, covering a range of specialized tasks and workflows. Better resources than your average "Claude-template-for-everything" site.

[![Stars](https://img.shields.io/github/stars/JSONbored/claudepro-directory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/JSONbored/claudepro-directory/stargazers) ![License](https://img.shields.io/github/license/JSONbored/claudepro-directory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/JSONbored/claudepro-directory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/JSONbored/claudepro-directory/commits) ![Language](https://img.shields.io/github/languages/top/JSONbored/claudepro-directory?style=flat-square&labelColor=343b41)
<br>

[`Project Management, Implementation, Planning, and Release`](https://github.com/scopecraft/command/tree/main/.claude/commands) &nbsp; by &nbsp; [scopecraft](https://github.com/scopecraft)    
Really comprehensive set of commands for all aspects of SDLC.

[![Stars](https://img.shields.io/github/stars/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/stargazers) ![License](https://img.shields.io/github/license/scopecraft/command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/commits) ![Language](https://img.shields.io/github/languages/top/scopecraft/command?style=flat-square&labelColor=343b41)
<br>

[`Project Management, Implementation, Planning, and Release`](https://github.com/scopecraft/command/tree/main/.claude/commands) &nbsp; by &nbsp; [scopecraft](https://github.com/scopecraft)    
Really comprehensive set of commands for all aspects of SDLC.

[![Stars](https://img.shields.io/github/stars/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/stargazers) ![License](https://img.shields.io/github/license/scopecraft/command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/commits) ![Language](https://img.shields.io/github/languages/top/scopecraft/command?style=flat-square&labelColor=343b41)
<br>

[`AB Method`](https://github.com/ayoubben18/ab-method) &nbsp; by &nbsp; [Ayoub Bensalah](https://github.com/ayoubben18)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A principled, spec-driven workflow that transforms large problems into focused, incremental missions using Claude Code's specialized sub agents. Includes slash-commands, sub agents, and specialized workflows designed for specific parts of the SDLC.

[![Stars](https://img.shields.io/github/stars/ayoubben18/ab-method?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ayoubben18/ab-method/stargazers) ![License](https://img.shields.io/github/license/ayoubben18/ab-method?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ayoubben18/ab-method?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ayoubben18/ab-method/commits) ![Language](https://img.shields.io/github/languages/top/ayoubben18/ab-method?style=flat-square&labelColor=343b41)
<br>

[`AB Method`](https://github.com/ayoubben18/ab-method) &nbsp; by &nbsp; [Ayoub Bensalah](https://github.com/ayoubben18)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A principled, spec-driven workflow that transforms large problems into focused, incremental missions using Claude Code's specialized sub agents. Includes slash-commands, sub agents, and specialized workflows designed for specific parts of the SDLC.

[![Stars](https://img.shields.io/github/stars/ayoubben18/ab-method?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ayoubben18/ab-method/stargazers) ![License](https://img.shields.io/github/license/ayoubben18/ab-method?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ayoubben18/ab-method?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ayoubben18/ab-method/commits) ![Language](https://img.shields.io/github/languages/top/ayoubben18/ab-method?style=flat-square&labelColor=343b41)
<br>

[`RIPER Workflow`](https://github.com/tony/claude-code-riper-5) &nbsp; by &nbsp; [Tony Narlock](https://tony.sh)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Structured development workflow enforcing separation between Research, Innovate, Plan, Execute, and Review phases. Features consolidated subagents for context-efficiency, branch-aware memory bank, and strict mode enforcement for guided development.

[![Stars](https://img.shields.io/github/stars/tony/claude-code-riper-5?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tony/claude-code-riper-5/stargazers) ![License](https://img.shields.io/github/license/tony/claude-code-riper-5?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tony/claude-code-riper-5?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tony/claude-code-riper-5/commits) ![Language](https://img.shields.io/github/languages/top/tony/claude-code-riper-5?style=flat-square&labelColor=343b41)
<br>

[`RIPER Workflow`](https://github.com/tony/claude-code-riper-5) &nbsp; by &nbsp; [Tony Narlock](https://tony.sh)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Structured development workflow enforcing separation between Research, Innovate, Plan, Execute, and Review phases. Features consolidated subagents for context-efficiency, branch-aware memory bank, and strict mode enforcement for guided development.

[![Stars](https://img.shields.io/github/stars/tony/claude-code-riper-5?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tony/claude-code-riper-5/stargazers) ![License](https://img.shields.io/github/license/tony/claude-code-riper-5?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tony/claude-code-riper-5?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tony/claude-code-riper-5/commits) ![Language](https://img.shields.io/github/languages/top/tony/claude-code-riper-5?style=flat-square&labelColor=343b41)
<br>

[`Project Bootstrapping and Task Management`](https://github.com/steadycursor/steadystart/tree/main/.claude/commands) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Provides a structured set of commands for bootstrapping and managing a new project, including meta-commands for creating and editing custom slash-commands.

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`Project Bootstrapping and Task Management`](https://github.com/steadycursor/steadystart/tree/main/.claude/commands) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Provides a structured set of commands for bootstrapping and managing a new project, including meta-commands for creating and editing custom slash-commands.

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`Laravel TALL Stack AI Development Starter Kit`](https://github.com/tott/laravel-tall-claude-ai-configs) &nbsp; by &nbsp; [tott](https://github.com/tott)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Transform your Laravel TALL (Tailwind, AlpineJS, Laravel, Livewire) stack development with comprehensive Claude Code configurations that provide intelligent assistance, systematic workflows, and domain expert consultation.

[![Stars](https://img.shields.io/github/stars/tott/laravel-tall-claude-ai-configs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tott/laravel-tall-claude-ai-configs/stargazers) ![License](https://img.shields.io/github/license/tott/laravel-tall-claude-ai-configs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tott/laravel-tall-claude-ai-configs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tott/laravel-tall-claude-ai-configs/commits) ![Language](https://img.shields.io/github/languages/top/tott/laravel-tall-claude-ai-configs?style=flat-square&labelColor=343b41)
<br>

[`Laravel TALL Stack AI Development Starter Kit`](https://github.com/tott/laravel-tall-claude-ai-configs) &nbsp; by &nbsp; [tott](https://github.com/tott)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Transform your Laravel TALL (Tailwind, AlpineJS, Laravel, Livewire) stack development with comprehensive Claude Code configurations that provide intelligent assistance, systematic workflows, and domain expert consultation.

[![Stars](https://img.shields.io/github/stars/tott/laravel-tall-claude-ai-configs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tott/laravel-tall-claude-ai-configs/stargazers) ![License](https://img.shields.io/github/license/tott/laravel-tall-claude-ai-configs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tott/laravel-tall-claude-ai-configs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tott/laravel-tall-claude-ai-configs/commits) ![Language](https://img.shields.io/github/languages/top/tott/laravel-tall-claude-ai-configs?style=flat-square&labelColor=343b41)
<br>

[`Blogging Platform Instructions`](https://github.com/cloudartisan/cloudartisan.github.io/tree/main/.claude/commands) &nbsp; by &nbsp; [cloudartisan](https://github.com/cloudartisan)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;CC-BY-SA-4.0  
Provides a well-structured set of commands for publishing and maintaining a blogging platform, including commands for creating posts, managing categories, and handling media files.

[![Stars](https://img.shields.io/github/stars/cloudartisan/cloudartisan.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cloudartisan/cloudartisan.github.io/stargazers) ![License](https://img.shields.io/github/license/cloudartisan/cloudartisan.github.io?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/cloudartisan/cloudartisan.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cloudartisan/cloudartisan.github.io/commits) ![Language](https://img.shields.io/github/languages/top/cloudartisan/cloudartisan.github.io?style=flat-square&labelColor=343b41)
<br>

[`Blogging Platform Instructions`](https://github.com/cloudartisan/cloudartisan.github.io/tree/main/.claude/commands) &nbsp; by &nbsp; [cloudartisan](https://github.com/cloudartisan)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;CC-BY-SA-4.0  
Provides a well-structured set of commands for publishing and maintaining a blogging platform, including commands for creating posts, managing categories, and handling media files.

[![Stars](https://img.shields.io/github/stars/cloudartisan/cloudartisan.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cloudartisan/cloudartisan.github.io/stargazers) ![License](https://img.shields.io/github/license/cloudartisan/cloudartisan.github.io?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/cloudartisan/cloudartisan.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cloudartisan/cloudartisan.github.io/commits) ![Language](https://img.shields.io/github/languages/top/cloudartisan/cloudartisan.github.io?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Cheat Sheet`](https://github.com/aeulker/Claude-Code-Cheat-Sheet) &nbsp; by &nbsp; [aeulker](https://github.com/aeulker)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claude Code Cheat Sheet - A comprehensive reference guide for Claude Code workflows and best practices.

[![Stars](https://img.shields.io/github/stars/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aeulker/Claude-Code-Cheat-Sheet/stargazers) ![License](https://img.shields.io/github/license/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aeulker/Claude-Code-Cheat-Sheet/commits) ![Language](https://img.shields.io/github/languages/top/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Cheat Sheet`](https://github.com/aeulker/Claude-Code-Cheat-Sheet) &nbsp; by &nbsp; [aeulker](https://github.com/aeulker)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claude Code Cheat Sheet - A comprehensive reference guide for Claude Code workflows and best practices.

[![Stars](https://img.shields.io/github/stars/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aeulker/Claude-Code-Cheat-Sheet/stargazers) ![License](https://img.shields.io/github/license/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aeulker/Claude-Code-Cheat-Sheet/commits) ![Language](https://img.shields.io/github/languages/top/aeulker/Claude-Code-Cheat-Sheet?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Handbook`](https://nikiforovall.blog/claude-code-rules/) &nbsp; by &nbsp; [nikiforovall](https://github.com/NikiforovAll)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Collection of best practices, tips, and techniques for Claude Code development workflows, enhanced with distributable plugins. Covers practical technique guides for beginners and advanced users.

[`Claude Code Handbook`](https://nikiforovall.blog/claude-code-rules/) &nbsp; by &nbsp; [nikiforovall](https://github.com/NikiforovAll)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Collection of best practices, tips, and techniques for Claude Code development workflows, enhanced with distributable plugins. Covers practical technique guides for beginners and advanced users.

[`ClaudeLog`](https://claudelog.com) &nbsp; by &nbsp; [InventorBlack](https://www.reddit.com/user/inventor_black/)    
A comprehensive knowledge base with detailed breakdowns of advanced [mechanics](https://claudelog.com/mechanics/you-are-the-main-thread/) including [CLAUDE.md best practices](https://claudelog.com/mechanics/claude-md-supremacy), practical technique guides like [plan mode](https://claudelog.com/mechanics/plan-mode), [ultrathink](https://claudelog.com/faqs/what-is-ultrathink/), [sub-agents](https://claudelog.com/mechanics/task-agent-tools/), [agent-first design](https://claudelog.com/mechanics/agent-first-design/) and [configuration guides](https://claudelog.com/configuration).

[`ClaudeLog`](https://claudelog.com) &nbsp; by &nbsp; [InventorBlack](https://www.reddit.com/user/inventor_black/)    
A comprehensive knowledge base with detailed breakdowns of advanced [mechanics](https://claudelog.com/mechanics/you-are-the-main-thread/) including [CLAUDE.md best practices](https://claudelog.com/mechanics/claude-md-supremacy), practical technique guides like [plan mode](https://claudelog.com/mechanics/plan-mode), [ultrathink](https://claudelog.com/faqs/what-is-ultrathink/), [sub-agents](https://claudelog.com/mechanics/task-agent-tools/), [agent-first design](https://claudelog.com/mechanics/agent-first-design/) and [configuration guides](https://claudelog.com/configuration).

[`Shipping Real Code w/ Claude`](https://diwank.space/field-notes-from-shipping-real-code-with-claude) &nbsp; by &nbsp; [Diwank](https://github.com/creatorrr)    
A detailed blog post explaining the author's process for shipping a product with Claude Code, including CLAUDE.md files and other interesting resources.

[`Shipping Real Code w/ Claude`](https://diwank.space/field-notes-from-shipping-real-code-with-claude) &nbsp; by &nbsp; [Diwank](https://github.com/creatorrr)    
A detailed blog post explaining the author's process for shipping a product with Claude Code, including CLAUDE.md files and other interesting resources.

</details>

<br>

## Tooling 🧰 [🔝](#awesome-claude-code)

> **Tooling** denotes applications that are built on top of Claude Code and consist of more components than slash-commands and `CLAUDE.md` files

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Claude Code Templates`](https://github.com/davila7/claude-code-templates) &nbsp; by &nbsp; [Daniel Avila](https://github.com/davila7)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Incredibly awesome collection of resources from every category in this list, presented with a neatly polished UI, great features like usage dashboard, analytics, and everything from slash commands to hooks to agents. An awesome companion for this awesome list.

[![Stars](https://img.shields.io/github/stars/davila7/claude-code-templates?style=flat-square&logo=github&labelColor=343b41)](https://github.com/davila7/claude-code-templates/stargazers) ![License](https://img.shields.io/github/license/davila7/claude-code-templates?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/davila7/claude-code-templates?style=flat-square&logo=github&labelColor=343b41)](https://github.com/davila7/claude-code-templates/commits) ![Language](https://img.shields.io/github/languages/top/davila7/claude-code-templates?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Templates`](https://github.com/davila7/claude-code-templates) &nbsp; by &nbsp; [Daniel Avila](https://github.com/davila7)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Incredibly awesome collection of resources from every category in this list, presented with a neatly polished UI, great features like usage dashboard, analytics, and everything from slash commands to hooks to agents. An awesome companion for this awesome list.

[![Stars](https://img.shields.io/github/stars/davila7/claude-code-templates?style=flat-square&logo=github&labelColor=343b41)](https://github.com/davila7/claude-code-templates/stargazers) ![License](https://img.shields.io/github/license/davila7/claude-code-templates?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/davila7/claude-code-templates?style=flat-square&logo=github&labelColor=343b41)](https://github.com/davila7/claude-code-templates/commits) ![Language](https://img.shields.io/github/languages/top/davila7/claude-code-templates?style=flat-square&labelColor=343b41)
<br>

[`SuperClaude`](https://github.com/SuperClaude-Org/SuperClaude_Framework) &nbsp; by &nbsp; [SuperClaude-Org](https://github.com/SuperClaude-Org)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A versatile configuration framework that enhances Claude Code with specialized commands, cognitive personas, and development methodologies, such as "Introspection" and "Orchestration".

[![Stars](https://img.shields.io/github/stars/SuperClaude-Org/SuperClaude_Framework?style=flat-square&logo=github&labelColor=343b41)](https://github.com/SuperClaude-Org/SuperClaude_Framework/stargazers) ![License](https://img.shields.io/github/license/SuperClaude-Org/SuperClaude_Framework?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/SuperClaude-Org/SuperClaude_Framework?style=flat-square&logo=github&labelColor=343b41)](https://github.com/SuperClaude-Org/SuperClaude_Framework/commits) ![Language](https://img.shields.io/github/languages/top/SuperClaude-Org/SuperClaude_Framework?style=flat-square&labelColor=343b41)
<br>

[`SuperClaude`](https://github.com/SuperClaude-Org/SuperClaude_Framework) &nbsp; by &nbsp; [SuperClaude-Org](https://github.com/SuperClaude-Org)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A versatile configuration framework that enhances Claude Code with specialized commands, cognitive personas, and development methodologies, such as "Introspection" and "Orchestration".

[![Stars](https://img.shields.io/github/stars/SuperClaude-Org/SuperClaude_Framework?style=flat-square&logo=github&labelColor=343b41)](https://github.com/SuperClaude-Org/SuperClaude_Framework/stargazers) ![License](https://img.shields.io/github/license/SuperClaude-Org/SuperClaude_Framework?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/SuperClaude-Org/SuperClaude_Framework?style=flat-square&logo=github&labelColor=343b41)](https://github.com/SuperClaude-Org/SuperClaude_Framework/commits) ![Language](https://img.shields.io/github/languages/top/SuperClaude-Org/SuperClaude_Framework?style=flat-square&labelColor=343b41)
<br>

[`Claudable`](https://github.com/opactorai/Claudable) &nbsp; by &nbsp; [Ethan Park](https://github.com/Atipico1)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claudable is an open-source web builder that leverages local CLI agents, such as Claude Code and Cursor Agent, to build and deploy products effortlessly. OpenSource Lovable that runs locally.

[![Stars](https://img.shields.io/github/stars/opactorai/Claudable?style=flat-square&logo=github&labelColor=343b41)](https://github.com/opactorai/Claudable/stargazers) ![License](https://img.shields.io/github/license/opactorai/Claudable?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/opactorai/Claudable?style=flat-square&logo=github&labelColor=343b41)](https://github.com/opactorai/Claudable/commits) ![Language](https://img.shields.io/github/languages/top/opactorai/Claudable?style=flat-square&labelColor=343b41)
<br>

[`Claudable`](https://github.com/opactorai/Claudable) &nbsp; by &nbsp; [Ethan Park](https://github.com/Atipico1)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claudable is an open-source web builder that leverages local CLI agents, such as Claude Code and Cursor Agent, to build and deploy products effortlessly. OpenSource Lovable that runs locally.

[![Stars](https://img.shields.io/github/stars/opactorai/Claudable?style=flat-square&logo=github&labelColor=343b41)](https://github.com/opactorai/Claudable/stargazers) ![License](https://img.shields.io/github/license/opactorai/Claudable?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/opactorai/Claudable?style=flat-square&logo=github&labelColor=343b41)](https://github.com/opactorai/Claudable/commits) ![Language](https://img.shields.io/github/languages/top/opactorai/Claudable?style=flat-square&labelColor=343b41)
<br>

[`Container Use`](https://github.com/dagger/container-use) &nbsp; by &nbsp; [dagger](https://github.com/dagger)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Development environments for coding agents. Enable multiple agents to work safely and independently with your preferred stack.

[![Stars](https://img.shields.io/github/stars/dagger/container-use?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dagger/container-use/stargazers) ![License](https://img.shields.io/github/license/dagger/container-use?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dagger/container-use?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dagger/container-use/commits) ![Language](https://img.shields.io/github/languages/top/dagger/container-use?style=flat-square&labelColor=343b41)
<br>

[`Container Use`](https://github.com/dagger/container-use) &nbsp; by &nbsp; [dagger](https://github.com/dagger)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Development environments for coding agents. Enable multiple agents to work safely and independently with your preferred stack.

[![Stars](https://img.shields.io/github/stars/dagger/container-use?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dagger/container-use/stargazers) ![License](https://img.shields.io/github/license/dagger/container-use?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dagger/container-use?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dagger/container-use/commits) ![Language](https://img.shields.io/github/languages/top/dagger/container-use?style=flat-square&labelColor=343b41)
<br>

[`Omnara`](https://github.com/omnara-ai/omnara) &nbsp; by &nbsp; [Ishaan Sehgal](https://github.com/ishaansehgal99)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
A command center for AI agents that syncs Claude Code sessions across terminal, web, and mobile. Allows for remote monitoring, human-in-the-loop interaction, and team collaboration. Recently open-sourced web and mobile applications.

[![Stars](https://img.shields.io/github/stars/omnara-ai/omnara?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omnara-ai/omnara/stargazers) ![License](https://img.shields.io/github/license/omnara-ai/omnara?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/omnara-ai/omnara?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omnara-ai/omnara/commits) ![Language](https://img.shields.io/github/languages/top/omnara-ai/omnara?style=flat-square&labelColor=343b41)
<br>

[`Omnara`](https://github.com/omnara-ai/omnara) &nbsp; by &nbsp; [Ishaan Sehgal](https://github.com/ishaansehgal99)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
A command center for AI agents that syncs Claude Code sessions across terminal, web, and mobile. Allows for remote monitoring, human-in-the-loop interaction, and team collaboration. Recently open-sourced web and mobile applications.

[![Stars](https://img.shields.io/github/stars/omnara-ai/omnara?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omnara-ai/omnara/stargazers) ![License](https://img.shields.io/github/license/omnara-ai/omnara?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/omnara-ai/omnara?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omnara-ai/omnara/commits) ![Language](https://img.shields.io/github/languages/top/omnara-ai/omnara?style=flat-square&labelColor=343b41)
<br>

[`claude-code-tools`](https://github.com/pchalasani/claude-code-tools) &nbsp; by &nbsp; [Prasad Chalasani](https://github.com/pchalasani)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A collection of awesome tools, including tmux integrations, better session management, hooks that enhance security - a really well-done set of Claude Code enhancers, especially for tmux users.

[![Stars](https://img.shields.io/github/stars/pchalasani/claude-code-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/pchalasani/claude-code-tools/stargazers) ![License](https://img.shields.io/github/license/pchalasani/claude-code-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/pchalasani/claude-code-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/pchalasani/claude-code-tools/commits) ![Language](https://img.shields.io/github/languages/top/pchalasani/claude-code-tools?style=flat-square&labelColor=343b41)
<br>

[`claude-code-tools`](https://github.com/pchalasani/claude-code-tools) &nbsp; by &nbsp; [Prasad Chalasani](https://github.com/pchalasani)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A collection of awesome tools, including tmux integrations, better session management, hooks that enhance security - a really well-done set of Claude Code enhancers, especially for tmux users.

[![Stars](https://img.shields.io/github/stars/pchalasani/claude-code-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/pchalasani/claude-code-tools/stargazers) ![License](https://img.shields.io/github/license/pchalasani/claude-code-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/pchalasani/claude-code-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/pchalasani/claude-code-tools/commits) ![Language](https://img.shields.io/github/languages/top/pchalasani/claude-code-tools?style=flat-square&labelColor=343b41)
<br>

[`tweakcc`](https://github.com/Piebald-AI/tweakcc) &nbsp; by &nbsp; [Piebald-AI](https://github.com/Piebald-AI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Command-line tool to customize your Claude Code styling.

[![Stars](https://img.shields.io/github/stars/Piebald-AI/tweakcc?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Piebald-AI/tweakcc/stargazers) ![License](https://img.shields.io/github/license/Piebald-AI/tweakcc?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Piebald-AI/tweakcc?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Piebald-AI/tweakcc/commits) ![Language](https://img.shields.io/github/languages/top/Piebald-AI/tweakcc?style=flat-square&labelColor=343b41)
<br>

[`tweakcc`](https://github.com/Piebald-AI/tweakcc) &nbsp; by &nbsp; [Piebald-AI](https://github.com/Piebald-AI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Command-line tool to customize your Claude Code styling.

[![Stars](https://img.shields.io/github/stars/Piebald-AI/tweakcc?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Piebald-AI/tweakcc/stargazers) ![License](https://img.shields.io/github/license/Piebald-AI/tweakcc?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Piebald-AI/tweakcc?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Piebald-AI/tweakcc/commits) ![Language](https://img.shields.io/github/languages/top/Piebald-AI/tweakcc?style=flat-square&labelColor=343b41)
<br>

[`cc-sessions`](https://github.com/GWUDCAP/cc-sessions) &nbsp; by &nbsp; [toastdev](https://github.com/satoastshi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
An opinionated approach to produce development with Claude Code

[![Stars](https://img.shields.io/github/stars/GWUDCAP/cc-sessions?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GWUDCAP/cc-sessions/stargazers) ![License](https://img.shields.io/github/license/GWUDCAP/cc-sessions?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GWUDCAP/cc-sessions?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GWUDCAP/cc-sessions/commits) ![Language](https://img.shields.io/github/languages/top/GWUDCAP/cc-sessions?style=flat-square&labelColor=343b41)
<br>

[`cc-sessions`](https://github.com/GWUDCAP/cc-sessions) &nbsp; by &nbsp; [toastdev](https://github.com/satoastshi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
An opinionated approach to produce development with Claude Code

[![Stars](https://img.shields.io/github/stars/GWUDCAP/cc-sessions?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GWUDCAP/cc-sessions/stargazers) ![License](https://img.shields.io/github/license/GWUDCAP/cc-sessions?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GWUDCAP/cc-sessions?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GWUDCAP/cc-sessions/commits) ![Language](https://img.shields.io/github/languages/top/GWUDCAP/cc-sessions?style=flat-square&labelColor=343b41)
<br>

[`VoiceMode MCP`](https://github.com/mbailey/voicemode) &nbsp; by &nbsp; [Mike Bailey](https://github.com/mbailey)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
VoiceMode MCP brings natural conversations to Claude Code. It supports any OpenAI API compatible voice services and installs free and open source voice services (Whisper.cpp and Kokoro-FastAPI).

[![Stars](https://img.shields.io/github/stars/mbailey/voicemode?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mbailey/voicemode/stargazers) ![License](https://img.shields.io/github/license/mbailey/voicemode?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/mbailey/voicemode?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mbailey/voicemode/commits) ![Language](https://img.shields.io/github/languages/top/mbailey/voicemode?style=flat-square&labelColor=343b41)
<br>

[`VoiceMode MCP`](https://github.com/mbailey/voicemode) &nbsp; by &nbsp; [Mike Bailey](https://github.com/mbailey)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
VoiceMode MCP brings natural conversations to Claude Code. It supports any OpenAI API compatible voice services and installs free and open source voice services (Whisper.cpp and Kokoro-FastAPI).

[![Stars](https://img.shields.io/github/stars/mbailey/voicemode?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mbailey/voicemode/stargazers) ![License](https://img.shields.io/github/license/mbailey/voicemode?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/mbailey/voicemode?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mbailey/voicemode/commits) ![Language](https://img.shields.io/github/languages/top/mbailey/voicemode?style=flat-square&labelColor=343b41)
<br>

[`Rulesync`](https://github.com/dyoshikawa/rulesync) &nbsp; by &nbsp; [dyoshikawa](https://github.com/dyoshikawa)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Node.js CLI tool that automatically generates configs (rules, ignore files, MCP servers, commands, and subagents) for various AI coding agents. Rulesync can convert configs between Claude Code and other AI agents in both directions.

[![Stars](https://img.shields.io/github/stars/dyoshikawa/rulesync?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dyoshikawa/rulesync/stargazers) ![License](https://img.shields.io/github/license/dyoshikawa/rulesync?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dyoshikawa/rulesync?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dyoshikawa/rulesync/commits) ![Language](https://img.shields.io/github/languages/top/dyoshikawa/rulesync?style=flat-square&labelColor=343b41)
<br>

[`Rulesync`](https://github.com/dyoshikawa/rulesync) &nbsp; by &nbsp; [dyoshikawa](https://github.com/dyoshikawa)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Node.js CLI tool that automatically generates configs (rules, ignore files, MCP servers, commands, and subagents) for various AI coding agents. Rulesync can convert configs between Claude Code and other AI agents in both directions.

[![Stars](https://img.shields.io/github/stars/dyoshikawa/rulesync?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dyoshikawa/rulesync/stargazers) ![License](https://img.shields.io/github/license/dyoshikawa/rulesync?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dyoshikawa/rulesync?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dyoshikawa/rulesync/commits) ![Language](https://img.shields.io/github/languages/top/dyoshikawa/rulesync?style=flat-square&labelColor=343b41)
<br>

[`Claude Composer`](https://github.com/possibilities/claude-composer) &nbsp; by &nbsp; [Mike Bannister](https://github.com/possibilities)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Unlicense  
A tool that adds small enhancements to Claude Code.

[![Stars](https://img.shields.io/github/stars/possibilities/claude-composer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/possibilities/claude-composer/stargazers) ![License](https://img.shields.io/github/license/possibilities/claude-composer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/possibilities/claude-composer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/possibilities/claude-composer/commits) ![Language](https://img.shields.io/github/languages/top/possibilities/claude-composer?style=flat-square&labelColor=343b41)
<br>

[`Claude Composer`](https://github.com/possibilities/claude-composer) &nbsp; by &nbsp; [Mike Bannister](https://github.com/possibilities)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Unlicense  
A tool that adds small enhancements to Claude Code.

[![Stars](https://img.shields.io/github/stars/possibilities/claude-composer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/possibilities/claude-composer/stargazers) ![License](https://img.shields.io/github/license/possibilities/claude-composer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/possibilities/claude-composer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/possibilities/claude-composer/commits) ![Language](https://img.shields.io/github/languages/top/possibilities/claude-composer?style=flat-square&labelColor=343b41)
<br>

[`claudekit`](https://github.com/carlrannaberg/claudekit) &nbsp; by &nbsp; [Carl Rannaberg](https://github.com/carlrannaberg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Impressive CLI toolkit providing auto-save checkpointing, code quality hooks, specification generation and execution, and 20+ specialized subagents including oracle (gpt-5), code-reviewer (6-aspect deep analysis), ai-sdk-expert (Vercel AI SDK), typescript-expert and many more for Claude Code workflows.

[![Stars](https://img.shields.io/github/stars/carlrannaberg/claudekit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/carlrannaberg/claudekit/stargazers) ![License](https://img.shields.io/github/license/carlrannaberg/claudekit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/carlrannaberg/claudekit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/carlrannaberg/claudekit/commits) ![Language](https://img.shields.io/github/languages/top/carlrannaberg/claudekit?style=flat-square&labelColor=343b41)
<br>

[`claudekit`](https://github.com/carlrannaberg/claudekit) &nbsp; by &nbsp; [Carl Rannaberg](https://github.com/carlrannaberg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Impressive CLI toolkit providing auto-save checkpointing, code quality hooks, specification generation and execution, and 20+ specialized subagents including oracle (gpt-5), code-reviewer (6-aspect deep analysis), ai-sdk-expert (Vercel AI SDK), typescript-expert and many more for Claude Code workflows.

[![Stars](https://img.shields.io/github/stars/carlrannaberg/claudekit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/carlrannaberg/claudekit/stargazers) ![License](https://img.shields.io/github/license/carlrannaberg/claudekit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/carlrannaberg/claudekit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/carlrannaberg/claudekit/commits) ![Language](https://img.shields.io/github/languages/top/carlrannaberg/claudekit?style=flat-square&labelColor=343b41)
<br>

[`Codanna`](https://github.com/bartolli/codanna) &nbsp; by &nbsp; [bartolli](https://github.com/bartolli)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Semantic code search and relationship tracking via MCP and Unix CLI. Features 91,318 symbols/sec parsing, Tree-sitter AST parsing for Rust and Python, 384-dimensional vectors, Tantivy full-text search, <10ms lookups, ~300ms MCP response time. FNV-1a hashed lookups with memory-mapped storage and specialized caches.

[![Stars](https://img.shields.io/github/stars/bartolli/codanna?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/codanna/stargazers) ![License](https://img.shields.io/github/license/bartolli/codanna?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/bartolli/codanna?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/codanna/commits) ![Language](https://img.shields.io/github/languages/top/bartolli/codanna?style=flat-square&labelColor=343b41)
<br>

[`Codanna`](https://github.com/bartolli/codanna) &nbsp; by &nbsp; [bartolli](https://github.com/bartolli)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Semantic code search and relationship tracking via MCP and Unix CLI. Features 91,318 symbols/sec parsing, Tree-sitter AST parsing for Rust and Python, 384-dimensional vectors, Tantivy full-text search, <10ms lookups, ~300ms MCP response time. FNV-1a hashed lookups with memory-mapped storage and specialized caches.

[![Stars](https://img.shields.io/github/stars/bartolli/codanna?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/codanna/stargazers) ![License](https://img.shields.io/github/license/bartolli/codanna?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/bartolli/codanna?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/codanna/commits) ![Language](https://img.shields.io/github/languages/top/bartolli/codanna?style=flat-square&labelColor=343b41)
<br>

[`Claude Hub`](https://github.com/claude-did-this/claude-hub) &nbsp; by &nbsp; [Claude Did This](https://github.com/claude-did-this)    
A webhook service that connects Claude Code to GitHub repositories, enabling AI-powered code assistance directly through pull requests and issues. This integration allows Claude to analyze repositories, answer technical questions, and help developers understand and improve their codebase through simple @mentions.

[![Stars](https://img.shields.io/github/stars/claude-did-this/claude-hub?style=flat-square&logo=github&labelColor=343b41)](https://github.com/claude-did-this/claude-hub/stargazers) ![License](https://img.shields.io/github/license/claude-did-this/claude-hub?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/claude-did-this/claude-hub?style=flat-square&logo=github&labelColor=343b41)](https://github.com/claude-did-this/claude-hub/commits) ![Language](https://img.shields.io/github/languages/top/claude-did-this/claude-hub?style=flat-square&labelColor=343b41)
<br>

[`Claude Hub`](https://github.com/claude-did-this/claude-hub) &nbsp; by &nbsp; [Claude Did This](https://github.com/claude-did-this)    
A webhook service that connects Claude Code to GitHub repositories, enabling AI-powered code assistance directly through pull requests and issues. This integration allows Claude to analyze repositories, answer technical questions, and help developers understand and improve their codebase through simple @mentions.

[![Stars](https://img.shields.io/github/stars/claude-did-this/claude-hub?style=flat-square&logo=github&labelColor=343b41)](https://github.com/claude-did-this/claude-hub/stargazers) ![License](https://img.shields.io/github/license/claude-did-this/claude-hub?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/claude-did-this/claude-hub?style=flat-square&logo=github&labelColor=343b41)](https://github.com/claude-did-this/claude-hub/commits) ![Language](https://img.shields.io/github/languages/top/claude-did-this/claude-hub?style=flat-square&labelColor=343b41)
<br>

[`Vibe-Log`](https://github.com/vibe-log/vibe-log-cli) &nbsp; by &nbsp; [Vibe-Log](https://github.com/vibe-log)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes your Claude Code prompts locally (using CC), provides intelligent session analysis and actionable strategic guidance - works in the statusline and produces very pretty HTML reports as well. Easy to install and remove.

[![Stars](https://img.shields.io/github/stars/vibe-log/vibe-log-cli?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vibe-log/vibe-log-cli/stargazers) ![License](https://img.shields.io/github/license/vibe-log/vibe-log-cli?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/vibe-log/vibe-log-cli?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vibe-log/vibe-log-cli/commits) ![Language](https://img.shields.io/github/languages/top/vibe-log/vibe-log-cli?style=flat-square&labelColor=343b41)
<br>

[`Vibe-Log`](https://github.com/vibe-log/vibe-log-cli) &nbsp; by &nbsp; [Vibe-Log](https://github.com/vibe-log)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes your Claude Code prompts locally (using CC), provides intelligent session analysis and actionable strategic guidance - works in the statusline and produces very pretty HTML reports as well. Easy to install and remove.

[![Stars](https://img.shields.io/github/stars/vibe-log/vibe-log-cli?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vibe-log/vibe-log-cli/stargazers) ![License](https://img.shields.io/github/license/vibe-log/vibe-log-cli?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/vibe-log/vibe-log-cli?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vibe-log/vibe-log-cli/commits) ![Language](https://img.shields.io/github/languages/top/vibe-log/vibe-log-cli?style=flat-square&labelColor=343b41)
<br>

[`Schaltwerk`](https://github.com/2mawi2/schaltwerk) &nbsp; by &nbsp; [Marius Wichtner](https://github.com/2mawi2)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Schaltwerk is a macOS Tauri desktop app that runs multiple terminal agents (Claude, Codex, OpenCode, Gemini-CLI) in parallel. Each session is isolated in its own git worktree/branch and includes a driving spec plus multiple terminals for running and testing. The keyboard-first, spec-driven workflow and local diff review keep humans in control.

[![Stars](https://img.shields.io/github/stars/2mawi2/schaltwerk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/2mawi2/schaltwerk/stargazers) ![License](https://img.shields.io/github/license/2mawi2/schaltwerk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/2mawi2/schaltwerk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/2mawi2/schaltwerk/commits) ![Language](https://img.shields.io/github/languages/top/2mawi2/schaltwerk?style=flat-square&labelColor=343b41)
<br>

[`Schaltwerk`](https://github.com/2mawi2/schaltwerk) &nbsp; by &nbsp; [Marius Wichtner](https://github.com/2mawi2)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Schaltwerk is a macOS Tauri desktop app that runs multiple terminal agents (Claude, Codex, OpenCode, Gemini-CLI) in parallel. Each session is isolated in its own git worktree/branch and includes a driving spec plus multiple terminals for running and testing. The keyboard-first, spec-driven workflow and local diff review keep humans in control.

[![Stars](https://img.shields.io/github/stars/2mawi2/schaltwerk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/2mawi2/schaltwerk/stargazers) ![License](https://img.shields.io/github/license/2mawi2/schaltwerk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/2mawi2/schaltwerk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/2mawi2/schaltwerk/commits) ![Language](https://img.shields.io/github/languages/top/2mawi2/schaltwerk?style=flat-square&labelColor=343b41)
<br>

[`ccexp`](https://github.com/nyatinte/ccexp) &nbsp; by &nbsp; [nyatinte](https://github.com/nyatinte)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Interactive CLI tool for discovering and managing Claude Code configuration files and slash commands with a beautiful terminal UI.

[![Stars](https://img.shields.io/github/stars/nyatinte/ccexp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nyatinte/ccexp/stargazers) ![License](https://img.shields.io/github/license/nyatinte/ccexp?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/nyatinte/ccexp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nyatinte/ccexp/commits) ![Language](https://img.shields.io/github/languages/top/nyatinte/ccexp?style=flat-square&labelColor=343b41)
<br>

[`ccexp`](https://github.com/nyatinte/ccexp) &nbsp; by &nbsp; [nyatinte](https://github.com/nyatinte)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Interactive CLI tool for discovering and managing Claude Code configuration files and slash commands with a beautiful terminal UI.

[![Stars](https://img.shields.io/github/stars/nyatinte/ccexp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nyatinte/ccexp/stargazers) ![License](https://img.shields.io/github/license/nyatinte/ccexp?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/nyatinte/ccexp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nyatinte/ccexp/commits) ![Language](https://img.shields.io/github/languages/top/nyatinte/ccexp?style=flat-square&labelColor=343b41)
<br>

[`Claude Codex Api`](https://github.com/4xian/claude-codex-api) &nbsp; by &nbsp; [4xian](https://github.com/4xian)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A CLI tool for managing Claude Code and Codex configurations, allowing one-click switching between multiple transit station API configurations; One-click switching of system environment variables, one-click testing of API latency/validity, automatic optimal route switching with internationalization support.

[![Stars](https://img.shields.io/github/stars/4xian/claude-codex-api?style=flat-square&logo=github&labelColor=343b41)](https://github.com/4xian/claude-codex-api/stargazers) ![License](https://img.shields.io/github/license/4xian/claude-codex-api?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/4xian/claude-codex-api?style=flat-square&logo=github&labelColor=343b41)](https://github.com/4xian/claude-codex-api/commits) ![Language](https://img.shields.io/github/languages/top/4xian/claude-codex-api?style=flat-square&labelColor=343b41)
<br>

[`Claude Codex Api`](https://github.com/4xian/claude-codex-api) &nbsp; by &nbsp; [4xian](https://github.com/4xian)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A CLI tool for managing Claude Code and Codex configurations, allowing one-click switching between multiple transit station API configurations; One-click switching of system environment variables, one-click testing of API latency/validity, automatic optimal route switching with internationalization support.

[![Stars](https://img.shields.io/github/stars/4xian/claude-codex-api?style=flat-square&logo=github&labelColor=343b41)](https://github.com/4xian/claude-codex-api/stargazers) ![License](https://img.shields.io/github/license/4xian/claude-codex-api?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/4xian/claude-codex-api?style=flat-square&logo=github&labelColor=343b41)](https://github.com/4xian/claude-codex-api/commits) ![Language](https://img.shields.io/github/languages/top/4xian/claude-codex-api?style=flat-square&labelColor=343b41)
<br>

[`ContextKit`](https://github.com/FlineDev/ContextKit) &nbsp; by &nbsp; [Cihat Gündüz](https://github.com/Jeehut)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A systematic development framework that transforms Claude Code into a proactive development partner. Features 4-phase planning methodology, specialized quality agents, and structured workflows that help AI produce production-ready code on first try.

[![Stars](https://img.shields.io/github/stars/FlineDev/ContextKit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/FlineDev/ContextKit/stargazers) ![License](https://img.shields.io/github/license/FlineDev/ContextKit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/FlineDev/ContextKit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/FlineDev/ContextKit/commits) ![Language](https://img.shields.io/github/languages/top/FlineDev/ContextKit?style=flat-square&labelColor=343b41)
<br>

[`ContextKit`](https://github.com/FlineDev/ContextKit) &nbsp; by &nbsp; [Cihat Gündüz](https://github.com/Jeehut)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A systematic development framework that transforms Claude Code into a proactive development partner. Features 4-phase planning methodology, specialized quality agents, and structured workflows that help AI produce production-ready code on first try.

[![Stars](https://img.shields.io/github/stars/FlineDev/ContextKit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/FlineDev/ContextKit/stargazers) ![License](https://img.shields.io/github/license/FlineDev/ContextKit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/FlineDev/ContextKit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/FlineDev/ContextKit/commits) ![Language](https://img.shields.io/github/languages/top/FlineDev/ContextKit?style=flat-square&labelColor=343b41)
<br>

[`cchistory`](https://github.com/eckardt/cchistory) &nbsp; by &nbsp; [eckardt](https://github.com/eckardt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Like the shell history command but for your Claude Code sessions. Easily list all Bash or "Bash-mode" (`!`) commands Claude Code ran in a session for reference.

[![Stars](https://img.shields.io/github/stars/eckardt/cchistory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eckardt/cchistory/stargazers) ![License](https://img.shields.io/github/license/eckardt/cchistory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eckardt/cchistory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eckardt/cchistory/commits) ![Language](https://img.shields.io/github/languages/top/eckardt/cchistory?style=flat-square&labelColor=343b41)
<br>

[`cchistory`](https://github.com/eckardt/cchistory) &nbsp; by &nbsp; [eckardt](https://github.com/eckardt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Like the shell history command but for your Claude Code sessions. Easily list all Bash or "Bash-mode" (`!`) commands Claude Code ran in a session for reference.

[![Stars](https://img.shields.io/github/stars/eckardt/cchistory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eckardt/cchistory/stargazers) ![License](https://img.shields.io/github/license/eckardt/cchistory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eckardt/cchistory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eckardt/cchistory/commits) ![Language](https://img.shields.io/github/languages/top/eckardt/cchistory?style=flat-square&labelColor=343b41)
<br>

[`Claw Code`](https://github.com/jamesrochabrun/Claw) &nbsp; by &nbsp; [James Rochabrun](https://github.com/jamesrochabrun)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A friendly macOS app for Claude Code. Uses Claude Code SDK to bring most of the well known features from Claude Code to a macOS app. In addition uses accessibility API to inspect Xcode workspaces making it a great tool for iOS engineers.

[![Stars](https://img.shields.io/github/stars/jamesrochabrun/Claw?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jamesrochabrun/Claw/stargazers) ![License](https://img.shields.io/github/license/jamesrochabrun/Claw?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jamesrochabrun/Claw?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jamesrochabrun/Claw/commits) ![Language](https://img.shields.io/github/languages/top/jamesrochabrun/Claw?style=flat-square&labelColor=343b41)
<br>

[`Claw Code`](https://github.com/jamesrochabrun/Claw) &nbsp; by &nbsp; [James Rochabrun](https://github.com/jamesrochabrun)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A friendly macOS app for Claude Code. Uses Claude Code SDK to bring most of the well known features from Claude Code to a macOS app. In addition uses accessibility API to inspect Xcode workspaces making it a great tool for iOS engineers.

[![Stars](https://img.shields.io/github/stars/jamesrochabrun/Claw?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jamesrochabrun/Claw/stargazers) ![License](https://img.shields.io/github/license/jamesrochabrun/Claw?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jamesrochabrun/Claw?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jamesrochabrun/Claw/commits) ![Language](https://img.shields.io/github/languages/top/jamesrochabrun/Claw?style=flat-square&labelColor=343b41)
<br>

[`cclogviewer`](https://github.com/Brads3290/cclogviewer) &nbsp; by &nbsp; [Brad S.](https://github.com/Brads3290)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A humble but handy utility for viewing Claude Code `.jsonl` conversation files in a pretty HTML UI.

[![Stars](https://img.shields.io/github/stars/Brads3290/cclogviewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Brads3290/cclogviewer/stargazers) ![License](https://img.shields.io/github/license/Brads3290/cclogviewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Brads3290/cclogviewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Brads3290/cclogviewer/commits) ![Language](https://img.shields.io/github/languages/top/Brads3290/cclogviewer?style=flat-square&labelColor=343b41)
<br>

[`cclogviewer`](https://github.com/Brads3290/cclogviewer) &nbsp; by &nbsp; [Brad S.](https://github.com/Brads3290)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A humble but handy utility for viewing Claude Code `.jsonl` conversation files in a pretty HTML UI.

[![Stars](https://img.shields.io/github/stars/Brads3290/cclogviewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Brads3290/cclogviewer/stargazers) ![License](https://img.shields.io/github/license/Brads3290/cclogviewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Brads3290/cclogviewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Brads3290/cclogviewer/commits) ![Language](https://img.shields.io/github/languages/top/Brads3290/cclogviewer?style=flat-square&labelColor=343b41)
<br>

[`run-claude-docker`](https://github.com/icanhasjonas/run-claude-docker) &nbsp; by &nbsp; [Jonas](https://github.com/icanhasjonas/)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A self-contained Docker runner that forwards your current workspace into a safe(r) isolated docker container, where you still have access to your Claude Code settings, authentication, ssh agent, pgp, optionally aws keys etc.

[![Stars](https://img.shields.io/github/stars/icanhasjonas/run-claude-docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/icanhasjonas/run-claude-docker/stargazers) ![License](https://img.shields.io/github/license/icanhasjonas/run-claude-docker?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/icanhasjonas/run-claude-docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/icanhasjonas/run-claude-docker/commits) ![Language](https://img.shields.io/github/languages/top/icanhasjonas/run-claude-docker?style=flat-square&labelColor=343b41)
<br>

[`run-claude-docker`](https://github.com/icanhasjonas/run-claude-docker) &nbsp; by &nbsp; [Jonas](https://github.com/icanhasjonas/)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A self-contained Docker runner that forwards your current workspace into a safe(r) isolated docker container, where you still have access to your Claude Code settings, authentication, ssh agent, pgp, optionally aws keys etc.

[![Stars](https://img.shields.io/github/stars/icanhasjonas/run-claude-docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/icanhasjonas/run-claude-docker/stargazers) ![License](https://img.shields.io/github/license/icanhasjonas/run-claude-docker?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/icanhasjonas/run-claude-docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/icanhasjonas/run-claude-docker/commits) ![Language](https://img.shields.io/github/languages/top/icanhasjonas/run-claude-docker?style=flat-square&labelColor=343b41)
<br>

[`cc-tools`](https://github.com/Veraticus/cc-tools) &nbsp; by &nbsp; [Josh Symonds](https://github.com/Veraticus)    
High-performance Go implementation of Claude Code hooks and utilities. Provides smart linting, testing, and statusline generation with minimal overhead.

[![Stars](https://img.shields.io/github/stars/Veraticus/cc-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Veraticus/cc-tools/stargazers) ![License](https://img.shields.io/github/license/Veraticus/cc-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Veraticus/cc-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Veraticus/cc-tools/commits) ![Language](https://img.shields.io/github/languages/top/Veraticus/cc-tools?style=flat-square&labelColor=343b41)
<br>

[`cc-tools`](https://github.com/Veraticus/cc-tools) &nbsp; by &nbsp; [Josh Symonds](https://github.com/Veraticus)    
High-performance Go implementation of Claude Code hooks and utilities. Provides smart linting, testing, and statusline generation with minimal overhead.

[![Stars](https://img.shields.io/github/stars/Veraticus/cc-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Veraticus/cc-tools/stargazers) ![License](https://img.shields.io/github/license/Veraticus/cc-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Veraticus/cc-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Veraticus/cc-tools/commits) ![Language](https://img.shields.io/github/languages/top/Veraticus/cc-tools?style=flat-square&labelColor=343b41)
<br>

[`DevRag`](https://github.com/tomohiro-owada/devrag) &nbsp; by &nbsp; [Tomohiro Owada](https://github.com/tomohiro-owada)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Lightweight local RAG system for Claude Code that uses vector search to retrieve only relevant document chunks, reducing token usage by 40x and search time by 15x compared to reading entire files.

[![Stars](https://img.shields.io/github/stars/tomohiro-owada/devrag?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tomohiro-owada/devrag/stargazers) ![License](https://img.shields.io/github/license/tomohiro-owada/devrag?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tomohiro-owada/devrag?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tomohiro-owada/devrag/commits) ![Language](https://img.shields.io/github/languages/top/tomohiro-owada/devrag?style=flat-square&labelColor=343b41)
<br>

[`DevRag`](https://github.com/tomohiro-owada/devrag) &nbsp; by &nbsp; [Tomohiro Owada](https://github.com/tomohiro-owada)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Lightweight local RAG system for Claude Code that uses vector search to retrieve only relevant document chunks, reducing token usage by 40x and search time by 15x compared to reading entire files.

[![Stars](https://img.shields.io/github/stars/tomohiro-owada/devrag?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tomohiro-owada/devrag/stargazers) ![License](https://img.shields.io/github/license/tomohiro-owada/devrag?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/tomohiro-owada/devrag?style=flat-square&logo=github&labelColor=343b41)](https://github.com/tomohiro-owada/devrag/commits) ![Language](https://img.shields.io/github/languages/top/tomohiro-owada/devrag?style=flat-square&labelColor=343b41)
<br>

[`Claude Agent Toolkit`](https://github.com/cheolwanpark/claude-agent-toolkit) &nbsp; by &nbsp; [Cheolwan Park](https://github.com/cheolwanpark)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Python framework that wraps claude-code-sdk to provide better developer experience through decorator-based tools, runtime isolation, and simplified agent development. Built for production safety with Docker containers. Features simple class-based definition with @tool decorator, built-in parallel execution, and FileSystemTool with permission control.

[![Stars](https://img.shields.io/github/stars/cheolwanpark/claude-agent-toolkit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cheolwanpark/claude-agent-toolkit/stargazers) ![License](https://img.shields.io/github/license/cheolwanpark/claude-agent-toolkit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/cheolwanpark/claude-agent-toolkit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cheolwanpark/claude-agent-toolkit/commits) ![Language](https://img.shields.io/github/languages/top/cheolwanpark/claude-agent-toolkit?style=flat-square&labelColor=343b41)
<br>

[`Claude Agent Toolkit`](https://github.com/cheolwanpark/claude-agent-toolkit) &nbsp; by &nbsp; [Cheolwan Park](https://github.com/cheolwanpark)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Python framework that wraps claude-code-sdk to provide better developer experience through decorator-based tools, runtime isolation, and simplified agent development. Built for production safety with Docker containers. Features simple class-based definition with @tool decorator, built-in parallel execution, and FileSystemTool with permission control.

[![Stars](https://img.shields.io/github/stars/cheolwanpark/claude-agent-toolkit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cheolwanpark/claude-agent-toolkit/stargazers) ![License](https://img.shields.io/github/license/cheolwanpark/claude-agent-toolkit?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/cheolwanpark/claude-agent-toolkit?style=flat-square&logo=github&labelColor=343b41)](https://github.com/cheolwanpark/claude-agent-toolkit/commits) ![Language](https://img.shields.io/github/languages/top/cheolwanpark/claude-agent-toolkit?style=flat-square&labelColor=343b41)
<br>

[`stt-mcp-server-linux`](https://github.com/marcindulak/stt-mcp-server-linux) &nbsp; by &nbsp; [marcindulak](https://github.com/marcindulak)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
A push-to-talk speech transcription setup for Linux using a Python MCP server. Runs locally in Docker with no external API calls. Your speech is recorded, transcribed into text, and then sent to Claude running in a Tmux session.

[![Stars](https://img.shields.io/github/stars/marcindulak/stt-mcp-server-linux?style=flat-square&logo=github&labelColor=343b41)](https://github.com/marcindulak/stt-mcp-server-linux/stargazers) ![License](https://img.shields.io/github/license/marcindulak/stt-mcp-server-linux?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/marcindulak/stt-mcp-server-linux?style=flat-square&logo=github&labelColor=343b41)](https://github.com/marcindulak/stt-mcp-server-linux/commits) ![Language](https://img.shields.io/github/languages/top/marcindulak/stt-mcp-server-linux?style=flat-square&labelColor=343b41)
<br>

[`stt-mcp-server-linux`](https://github.com/marcindulak/stt-mcp-server-linux) &nbsp; by &nbsp; [marcindulak](https://github.com/marcindulak)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
A push-to-talk speech transcription setup for Linux using a Python MCP server. Runs locally in Docker with no external API calls. Your speech is recorded, transcribed into text, and then sent to Claude running in a Tmux session.

[![Stars](https://img.shields.io/github/stars/marcindulak/stt-mcp-server-linux?style=flat-square&logo=github&labelColor=343b41)](https://github.com/marcindulak/stt-mcp-server-linux/stargazers) ![License](https://img.shields.io/github/license/marcindulak/stt-mcp-server-linux?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/marcindulak/stt-mcp-server-linux?style=flat-square&logo=github&labelColor=343b41)](https://github.com/marcindulak/stt-mcp-server-linux/commits) ![Language](https://img.shields.io/github/languages/top/marcindulak/stt-mcp-server-linux?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Agent SDK Pretty Printer`](https://github.com/PepijnSenders/claude-pretty-printer) &nbsp; by &nbsp; [PepijnSenders](https://github.com/PepijnSenders)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A lightweight utility that transforms raw Claude Agent SDK JSON messages into beautiful, readable CLI output with color-coded boxes and professional formatting.

[![Stars](https://img.shields.io/github/stars/PepijnSenders/claude-pretty-printer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/PepijnSenders/claude-pretty-printer/stargazers) ![License](https://img.shields.io/github/license/PepijnSenders/claude-pretty-printer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/PepijnSenders/claude-pretty-printer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/PepijnSenders/claude-pretty-printer/commits) ![Language](https://img.shields.io/github/languages/top/PepijnSenders/claude-pretty-printer?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Agent SDK Pretty Printer`](https://github.com/PepijnSenders/claude-pretty-printer) &nbsp; by &nbsp; [PepijnSenders](https://github.com/PepijnSenders)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A lightweight utility that transforms raw Claude Agent SDK JSON messages into beautiful, readable CLI output with color-coded boxes and professional formatting.

[![Stars](https://img.shields.io/github/stars/PepijnSenders/claude-pretty-printer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/PepijnSenders/claude-pretty-printer/stargazers) ![License](https://img.shields.io/github/license/PepijnSenders/claude-pretty-printer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/PepijnSenders/claude-pretty-printer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/PepijnSenders/claude-pretty-printer/commits) ![Language](https://img.shields.io/github/languages/top/PepijnSenders/claude-pretty-printer?style=flat-square&labelColor=343b41)
<br>

[`mcp_docker`](https://github.com/williajm/mcp_docker) &nbsp; by &nbsp; [williajm](https://github.com/williajm)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
MCP server for Docker management with 36 tools, 3 AI prompts, and enterprise safety controls (three-tier system: SAFE/MODERATE/DESTRUCTIVE operations).

> ⚠️ **High Privilege Tool**: Provides Docker daemon access (equivalent to root). Enable authentication for non-local use. Review [security documentation](https://github.com/williajm/mcp_docker/blob/main/SECURITY.md).

[![Stars](https://img.shields.io/github/stars/williajm/mcp_docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/williajm/mcp_docker/stargazers) ![License](https://img.shields.io/github/license/williajm/mcp_docker?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/williajm/mcp_docker?style=flat-square&logo=github&labelColor=343b41)](https://github.com/williajm/mcp_docker/commits) ![Language](https://img.shields.io/github/languages/top/williajm/mcp_docker?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Web Shell`](https://github.com/vaderyang/claudecode_web_shell) &nbsp; by &nbsp; [vaderyang](https://github.com/vaderyang)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A web-based terminal interface for Claude Code that allows you to interact with Claude Code through your browser.

[![Stars](https://img.shields.io/github/stars/vaderyang/claudecode_web_shell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vaderyang/claudecode_web_shell/stargazers) ![License](https://img.shields.io/github/license/vaderyang/claudecode_web_shell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/vaderyang/claudecode_web_shell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vaderyang/claudecode_web_shell/commits) ![Language](https://img.shields.io/github/languages/top/vaderyang/claudecode_web_shell?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Web Shell`](https://github.com/vaderyang/claudecode_web_shell) &nbsp; by &nbsp; [vaderyang](https://github.com/vaderyang)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A web-based terminal interface for Claude Code that allows you to interact with Claude Code through your browser.

[![Stars](https://img.shields.io/github/stars/vaderyang/claudecode_web_shell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vaderyang/claudecode_web_shell/stargazers) ![License](https://img.shields.io/github/license/vaderyang/claudecode_web_shell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/vaderyang/claudecode_web_shell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/vaderyang/claudecode_web_shell/commits) ![Language](https://img.shields.io/github/languages/top/vaderyang/claudecode_web_shell?style=flat-square&labelColor=343b41)
<br>

[`Claude Control Terminal`](https://github.com/schlunsen/claude-control-terminal) &nbsp; by &nbsp; [schlunsen](https://github.com/schlunsen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
High-performance Go port of claude-code-templates providing component installation (600+ agents, 200+ commands, MCPs), Docker containerization, real-time analytics dashboard with WebSocket monitoring, and cross-platform deployment. Features 10-50x faster startup and 3-5x lower memory usage compared to Node.js alternatives.

[![Stars](https://img.shields.io/github/stars/schlunsen/claude-control-terminal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/schlunsen/claude-control-terminal/stargazers) ![License](https://img.shields.io/github/license/schlunsen/claude-control-terminal?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/schlunsen/claude-control-terminal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/schlunsen/claude-control-terminal/commits) ![Language](https://img.shields.io/github/languages/top/schlunsen/claude-control-terminal?style=flat-square&labelColor=343b41)
<br>

[`Claude Control Terminal`](https://github.com/schlunsen/claude-control-terminal) &nbsp; by &nbsp; [schlunsen](https://github.com/schlunsen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
High-performance Go port of claude-code-templates providing component installation (600+ agents, 200+ commands, MCPs), Docker containerization, real-time analytics dashboard with WebSocket monitoring, and cross-platform deployment. Features 10-50x faster startup and 3-5x lower memory usage compared to Node.js alternatives.

[![Stars](https://img.shields.io/github/stars/schlunsen/claude-control-terminal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/schlunsen/claude-control-terminal/stargazers) ![License](https://img.shields.io/github/license/schlunsen/claude-control-terminal?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/schlunsen/claude-control-terminal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/schlunsen/claude-control-terminal/commits) ![Language](https://img.shields.io/github/languages/top/schlunsen/claude-control-terminal?style=flat-square&labelColor=343b41)
<br>

[`conduit8`](https://github.com/conduit8/conduit8) &nbsp; by &nbsp; [Alexander Zuev](https://github.com/alexander-zuev)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
CLI registry for discovering, installing, and managing Claude Code skills. Search 20+ curated skills by keyword or category, install directly to ~/.claude/skills/ with one command. Like context7 for Claude Code skills. Available via npx - no global installation required.

[![Stars](https://img.shields.io/github/stars/conduit8/conduit8?style=flat-square&logo=github&labelColor=343b41)](https://github.com/conduit8/conduit8/stargazers) ![License](https://img.shields.io/github/license/conduit8/conduit8?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/conduit8/conduit8?style=flat-square&logo=github&labelColor=343b41)](https://github.com/conduit8/conduit8/commits) ![Language](https://img.shields.io/github/languages/top/conduit8/conduit8?style=flat-square&labelColor=343b41)
<br>

[`conduit8`](https://github.com/conduit8/conduit8) &nbsp; by &nbsp; [Alexander Zuev](https://github.com/alexander-zuev)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
CLI registry for discovering, installing, and managing Claude Code skills. Search 20+ curated skills by keyword or category, install directly to ~/.claude/skills/ with one command. Like context7 for Claude Code skills. Available via npx - no global installation required.

[![Stars](https://img.shields.io/github/stars/conduit8/conduit8?style=flat-square&logo=github&labelColor=343b41)](https://github.com/conduit8/conduit8/stargazers) ![License](https://img.shields.io/github/license/conduit8/conduit8?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/conduit8/conduit8?style=flat-square&logo=github&labelColor=343b41)](https://github.com/conduit8/conduit8/commits) ![Language](https://img.shields.io/github/languages/top/conduit8/conduit8?style=flat-square&labelColor=343b41)
<br>

[`Helium MCP`](https://github.com/connerlambden/helium-mcp) &nbsp; by &nbsp; [Conner Lambden](https://github.com/connerlambden)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Remote MCP server for real-time news with multi-dimensional bias scoring (3.2M+ articles, 5000+ sources, 15+ dimensions), market data with AI bull and bear cases and probability scenarios, machine-learning options pricing, balanced multi-source news synthesis, and meme search.

[![Stars](https://img.shields.io/github/stars/connerlambden/helium-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/connerlambden/helium-mcp/stargazers) ![License](https://img.shields.io/github/license/connerlambden/helium-mcp?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/connerlambden/helium-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/connerlambden/helium-mcp/commits) ![Language](https://img.shields.io/github/languages/top/connerlambden/helium-mcp?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>IDE Integrations <a href="#awesome-claude-code">🔝</a></h3></summary>

[`claude-code.nvim`](https://github.com/greggh/claude-code.nvim) &nbsp; by &nbsp; [greggh](https://github.com/greggh)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A seamless integration between Claude Code AI assistant and Neovim.

[![Stars](https://img.shields.io/github/stars/greggh/claude-code.nvim?style=flat-square&logo=github&labelColor=343b41)](https://github.com/greggh/claude-code.nvim/stargazers) ![License](https://img.shields.io/github/license/greggh/claude-code.nvim?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/greggh/claude-code.nvim?style=flat-square&logo=github&labelColor=343b41)](https://github.com/greggh/claude-code.nvim/commits) ![Language](https://img.shields.io/github/languages/top/greggh/claude-code.nvim?style=flat-square&labelColor=343b41)
<br>

[`claude-code.nvim`](https://github.com/greggh/claude-code.nvim) &nbsp; by &nbsp; [greggh](https://github.com/greggh)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A seamless integration between Claude Code AI assistant and Neovim.

[![Stars](https://img.shields.io/github/stars/greggh/claude-code.nvim?style=flat-square&logo=github&labelColor=343b41)](https://github.com/greggh/claude-code.nvim/stargazers) ![License](https://img.shields.io/github/license/greggh/claude-code.nvim?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/greggh/claude-code.nvim?style=flat-square&logo=github&labelColor=343b41)](https://github.com/greggh/claude-code.nvim/commits) ![Language](https://img.shields.io/github/languages/top/greggh/claude-code.nvim?style=flat-square&labelColor=343b41)
<br>

[`claude-code-ide.el`](https://github.com/manzaltu/claude-code-ide.el) &nbsp; by &nbsp; [manzaltu](https://github.com/manzaltu)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
claude-code-ide.el integrates Claude Code with Emacs, like Anthropic’s VS Code/IntelliJ extensions. It shows ediff-based code suggestions, pulls LSP/flymake/flycheck diagnostics, and tracks buffer context. It adds an extensible MCP tool support for symbol refs/defs, project metadata, and tree-sitter AST queries.

[![Stars](https://img.shields.io/github/stars/manzaltu/claude-code-ide.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/manzaltu/claude-code-ide.el/stargazers) ![License](https://img.shields.io/github/license/manzaltu/claude-code-ide.el?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/manzaltu/claude-code-ide.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/manzaltu/claude-code-ide.el/commits) ![Language](https://img.shields.io/github/languages/top/manzaltu/claude-code-ide.el?style=flat-square&labelColor=343b41)
<br>

[`claude-code-ide.el`](https://github.com/manzaltu/claude-code-ide.el) &nbsp; by &nbsp; [manzaltu](https://github.com/manzaltu)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
claude-code-ide.el integrates Claude Code with Emacs, like Anthropic’s VS Code/IntelliJ extensions. It shows ediff-based code suggestions, pulls LSP/flymake/flycheck diagnostics, and tracks buffer context. It adds an extensible MCP tool support for symbol refs/defs, project metadata, and tree-sitter AST queries.

[![Stars](https://img.shields.io/github/stars/manzaltu/claude-code-ide.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/manzaltu/claude-code-ide.el/stargazers) ![License](https://img.shields.io/github/license/manzaltu/claude-code-ide.el?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/manzaltu/claude-code-ide.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/manzaltu/claude-code-ide.el/commits) ![Language](https://img.shields.io/github/languages/top/manzaltu/claude-code-ide.el?style=flat-square&labelColor=343b41)
<br>

[`claude-code.el`](https://github.com/stevemolitor/claude-code.el) &nbsp; by &nbsp; [stevemolitor](https://github.com/stevemolitor)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
An Emacs interface for Claude Code CLI.

[![Stars](https://img.shields.io/github/stars/stevemolitor/claude-code.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stevemolitor/claude-code.el/stargazers) ![License](https://img.shields.io/github/license/stevemolitor/claude-code.el?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/stevemolitor/claude-code.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stevemolitor/claude-code.el/commits) ![Language](https://img.shields.io/github/languages/top/stevemolitor/claude-code.el?style=flat-square&labelColor=343b41)
<br>

[`claude-code.el`](https://github.com/stevemolitor/claude-code.el) &nbsp; by &nbsp; [stevemolitor](https://github.com/stevemolitor)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
An Emacs interface for Claude Code CLI.

[![Stars](https://img.shields.io/github/stars/stevemolitor/claude-code.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stevemolitor/claude-code.el/stargazers) ![License](https://img.shields.io/github/license/stevemolitor/claude-code.el?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/stevemolitor/claude-code.el?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stevemolitor/claude-code.el/commits) ![Language](https://img.shields.io/github/languages/top/stevemolitor/claude-code.el?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Chat`](https://marketplace.visualstudio.com/items?itemName=AndrePimenta.claude-code-chat) &nbsp; by &nbsp; [andrepimenta](https://github.com/andrepimenta)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;&copy;  
An elegant and user-friendly Claude Code chat interface for VS Code.

[`Claude Code Chat`](https://marketplace.visualstudio.com/items?itemName=AndrePimenta.claude-code-chat) &nbsp; by &nbsp; [andrepimenta](https://github.com/andrepimenta)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;&copy;  
An elegant and user-friendly Claude Code chat interface for VS Code.

[`crystal`](https://github.com/stravu/crystal) &nbsp; by &nbsp; [stravu](https://github.com/stravu)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A full-fledged desktop application for orchestrating, monitoring, and interacting with Claude Code agents.

[![Stars](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stravu/crystal/stargazers) ![License](https://img.shields.io/github/license/stravu/crystal?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/stravu/crystal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stravu/crystal/commits) ![Language](https://img.shields.io/github/languages/top/stravu/crystal?style=flat-square&labelColor=343b41)
<br>

[`crystal`](https://github.com/stravu/crystal) &nbsp; by &nbsp; [stravu](https://github.com/stravu)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A full-fledged desktop application for orchestrating, monitoring, and interacting with Claude Code agents.

[![Stars](https://img.shields.io/github/stars/stravu/crystal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stravu/crystal/stargazers) ![License](https://img.shields.io/github/license/stravu/crystal?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/stravu/crystal?style=flat-square&logo=github&labelColor=343b41)](https://github.com/stravu/crystal/commits) ![Language](https://img.shields.io/github/languages/top/stravu/crystal?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Usage Monitors <a href="#awesome-claude-code">🔝</a></h3></summary>

[`CC Usage`](https://github.com/ryoppippi/ccusage) &nbsp; by &nbsp; [ryoppippi](https://github.com/ryoppippi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Handy CLI tool for managing and analyzing Claude Code usage, based on analyzing local Claude Code logs. Presents a nice dashboard regarding cost information, token consumption, etc.

[![Stars](https://img.shields.io/github/stars/ryoppippi/ccusage?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ryoppippi/ccusage/stargazers) ![License](https://img.shields.io/github/license/ryoppippi/ccusage?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ryoppippi/ccusage?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ryoppippi/ccusage/commits) ![Language](https://img.shields.io/github/languages/top/ryoppippi/ccusage?style=flat-square&labelColor=343b41)
<br>

[`CC Usage`](https://github.com/ryoppippi/ccusage) &nbsp; by &nbsp; [ryoppippi](https://github.com/ryoppippi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Handy CLI tool for managing and analyzing Claude Code usage, based on analyzing local Claude Code logs. Presents a nice dashboard regarding cost information, token consumption, etc.

[![Stars](https://img.shields.io/github/stars/ryoppippi/ccusage?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ryoppippi/ccusage/stargazers) ![License](https://img.shields.io/github/license/ryoppippi/ccusage?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ryoppippi/ccusage?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ryoppippi/ccusage/commits) ![Language](https://img.shields.io/github/languages/top/ryoppippi/ccusage?style=flat-square&labelColor=343b41)
<br>

[`ccflare`](https://github.com/snipeship/ccflare) &nbsp; by &nbsp; [snipeship](https://github.com/snipeship)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claude Code usage dashboard with a web-UI that would put Tableau to shame. Thoroughly comprehensive metrics, frictionless setup, detailed logging, really really nice UI.

[![Stars](https://img.shields.io/github/stars/snipeship/ccflare?style=flat-square&logo=github&labelColor=343b41)](https://github.com/snipeship/ccflare/stargazers) ![License](https://img.shields.io/github/license/snipeship/ccflare?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/snipeship/ccflare?style=flat-square&logo=github&labelColor=343b41)](https://github.com/snipeship/ccflare/commits) ![Language](https://img.shields.io/github/languages/top/snipeship/ccflare?style=flat-square&labelColor=343b41)
<br>

[`ccflare`](https://github.com/snipeship/ccflare) &nbsp; by &nbsp; [snipeship](https://github.com/snipeship)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claude Code usage dashboard with a web-UI that would put Tableau to shame. Thoroughly comprehensive metrics, frictionless setup, detailed logging, really really nice UI.

[![Stars](https://img.shields.io/github/stars/snipeship/ccflare?style=flat-square&logo=github&labelColor=343b41)](https://github.com/snipeship/ccflare/stargazers) ![License](https://img.shields.io/github/license/snipeship/ccflare?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/snipeship/ccflare?style=flat-square&logo=github&labelColor=343b41)](https://github.com/snipeship/ccflare/commits) ![Language](https://img.shields.io/github/languages/top/snipeship/ccflare?style=flat-square&labelColor=343b41)
<br>

[`ccthink`](https://github.com/normalnormie/ccthink) &nbsp; by &nbsp; [Norman](https://github.com/normalnormie)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Thinking monitor with optional AI compression and git integration

[![Stars](https://img.shields.io/github/stars/normalnormie/ccthink?style=flat-square&logo=github&labelColor=343b41)](https://github.com/normalnormie/ccthink/stargazers) ![License](https://img.shields.io/github/license/normalnormie/ccthink?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/normalnormie/ccthink?style=flat-square&logo=github&labelColor=343b41)](https://github.com/normalnormie/ccthink/commits) ![Language](https://img.shields.io/github/languages/top/normalnormie/ccthink?style=flat-square&labelColor=343b41)
<br>

[`ccthink`](https://github.com/normalnormie/ccthink) &nbsp; by &nbsp; [Norman](https://github.com/normalnormie)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Thinking monitor with optional AI compression and git integration

[![Stars](https://img.shields.io/github/stars/normalnormie/ccthink?style=flat-square&logo=github&labelColor=343b41)](https://github.com/normalnormie/ccthink/stargazers) ![License](https://img.shields.io/github/license/normalnormie/ccthink?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/normalnormie/ccthink?style=flat-square&logo=github&labelColor=343b41)](https://github.com/normalnormie/ccthink/commits) ![Language](https://img.shields.io/github/languages/top/normalnormie/ccthink?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Usage Monitor`](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) &nbsp; by &nbsp; [Maciek-roboblog](https://github.com/Maciek-roboblog)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A real-time terminal-based tool for monitoring Claude Code token usage. It shows live token consumption, burn rate, and predictions for token depletion. Features include visual progress bars, session-aware analytics, and support for multiple subscription plans.

[![Stars](https://img.shields.io/github/stars/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor/stargazers) ![License](https://img.shields.io/github/license/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor/commits) ![Language](https://img.shields.io/github/languages/top/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Usage Monitor`](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) &nbsp; by &nbsp; [Maciek-roboblog](https://github.com/Maciek-roboblog)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A real-time terminal-based tool for monitoring Claude Code token usage. It shows live token consumption, burn rate, and predictions for token depletion. Features include visual progress bars, session-aware analytics, and support for multiple subscription plans.

[![Stars](https://img.shields.io/github/stars/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor/stargazers) ![License](https://img.shields.io/github/license/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor/commits) ![Language](https://img.shields.io/github/languages/top/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&labelColor=343b41)
<br>

[`viberank`](https://github.com/sculptdotfun/viberank) &nbsp; by &nbsp; [nikshepsvn](https://github.com/nikshepsvn)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A community-driven leaderboard tool that enables developers to visualize, track, and compete based on their Claude Code usage statistics. It features robust data analytics, GitHub OAuth, data validation, and user-friendly CLI/web submission methods.

[![Stars](https://img.shields.io/github/stars/sculptdotfun/viberank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sculptdotfun/viberank/stargazers) ![License](https://img.shields.io/github/license/sculptdotfun/viberank?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sculptdotfun/viberank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sculptdotfun/viberank/commits) ![Language](https://img.shields.io/github/languages/top/sculptdotfun/viberank?style=flat-square&labelColor=343b41)
<br>

[`viberank`](https://github.com/sculptdotfun/viberank) &nbsp; by &nbsp; [nikshepsvn](https://github.com/nikshepsvn)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A community-driven leaderboard tool that enables developers to visualize, track, and compete based on their Claude Code usage statistics. It features robust data analytics, GitHub OAuth, data validation, and user-friendly CLI/web submission methods.

[![Stars](https://img.shields.io/github/stars/sculptdotfun/viberank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sculptdotfun/viberank/stargazers) ![License](https://img.shields.io/github/license/sculptdotfun/viberank?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sculptdotfun/viberank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sculptdotfun/viberank/commits) ![Language](https://img.shields.io/github/languages/top/sculptdotfun/viberank?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Orchestrators <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Claude Code Flow`](https://github.com/ruvnet/claude-code-flow) &nbsp; by &nbsp; [ruvnet](https://github.com/ruvnet)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
This mode serves as a code-first orchestration layer, enabling Claude to write, edit, test, and optimize code autonomously across recursive agent cycles.

[![Stars](https://img.shields.io/github/stars/ruvnet/claude-code-flow?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ruvnet/claude-code-flow/stargazers) ![License](https://img.shields.io/github/license/ruvnet/claude-code-flow?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ruvnet/claude-code-flow?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ruvnet/claude-code-flow/commits) ![Language](https://img.shields.io/github/languages/top/ruvnet/claude-code-flow?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Flow`](https://github.com/ruvnet/claude-code-flow) &nbsp; by &nbsp; [ruvnet](https://github.com/ruvnet)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
This mode serves as a code-first orchestration layer, enabling Claude to write, edit, test, and optimize code autonomously across recursive agent cycles.

[![Stars](https://img.shields.io/github/stars/ruvnet/claude-code-flow?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ruvnet/claude-code-flow/stargazers) ![License](https://img.shields.io/github/license/ruvnet/claude-code-flow?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ruvnet/claude-code-flow?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ruvnet/claude-code-flow/commits) ![Language](https://img.shields.io/github/languages/top/ruvnet/claude-code-flow?style=flat-square&labelColor=343b41)
<br>

[`Claude Squad`](https://github.com/smtg-ai/claude-squad) &nbsp; by &nbsp; [smtg-ai](https://github.com/smtg-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Claude Squad is a terminal app that manages multiple Claude Code, Codex (and other local agents including Aider) in separate workspaces, allowing you to work on multiple tasks simultaneously.

[![Stars](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&logo=github&labelColor=343b41)](https://github.com/smtg-ai/claude-squad/stargazers) ![License](https://img.shields.io/github/license/smtg-ai/claude-squad?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/smtg-ai/claude-squad?style=flat-square&logo=github&labelColor=343b41)](https://github.com/smtg-ai/claude-squad/commits) ![Language](https://img.shields.io/github/languages/top/smtg-ai/claude-squad?style=flat-square&labelColor=343b41)
<br>

[`Claude Squad`](https://github.com/smtg-ai/claude-squad) &nbsp; by &nbsp; [smtg-ai](https://github.com/smtg-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Claude Squad is a terminal app that manages multiple Claude Code, Codex (and other local agents including Aider) in separate workspaces, allowing you to work on multiple tasks simultaneously.

[![Stars](https://img.shields.io/github/stars/smtg-ai/claude-squad?style=flat-square&logo=github&labelColor=343b41)](https://github.com/smtg-ai/claude-squad/stargazers) ![License](https://img.shields.io/github/license/smtg-ai/claude-squad?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/smtg-ai/claude-squad?style=flat-square&logo=github&labelColor=343b41)](https://github.com/smtg-ai/claude-squad/commits) ![Language](https://img.shields.io/github/languages/top/smtg-ai/claude-squad?style=flat-square&labelColor=343b41)
<br>

[`Claude Swarm`](https://github.com/parruda/claude-swarm) &nbsp; by &nbsp; [parruda](https://github.com/parruda)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Launch Claude Code session that is connected to a swarm of Claude Code Agents.

[![Stars](https://img.shields.io/github/stars/parruda/claude-swarm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/parruda/claude-swarm/stargazers) ![License](https://img.shields.io/github/license/parruda/claude-swarm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/parruda/claude-swarm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/parruda/claude-swarm/commits) ![Language](https://img.shields.io/github/languages/top/parruda/claude-swarm?style=flat-square&labelColor=343b41)
<br>

[`Claude Swarm`](https://github.com/parruda/claude-swarm) &nbsp; by &nbsp; [parruda](https://github.com/parruda)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Launch Claude Code session that is connected to a swarm of Claude Code Agents.

[![Stars](https://img.shields.io/github/stars/parruda/claude-swarm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/parruda/claude-swarm/stargazers) ![License](https://img.shields.io/github/license/parruda/claude-swarm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/parruda/claude-swarm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/parruda/claude-swarm/commits) ![Language](https://img.shields.io/github/languages/top/parruda/claude-swarm?style=flat-square&labelColor=343b41)
<br>

[`Claude Task Master`](https://github.com/eyaltoledano/claude-task-master) &nbsp; by &nbsp; [eyaltoledano](https://github.com/eyaltoledano)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
A task management system for AI-driven development with Claude, designed to work seamlessly with Cursor AI.

[![Stars](https://img.shields.io/github/stars/eyaltoledano/claude-task-master?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eyaltoledano/claude-task-master/stargazers) ![License](https://img.shields.io/github/license/eyaltoledano/claude-task-master?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eyaltoledano/claude-task-master?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eyaltoledano/claude-task-master/commits) ![Language](https://img.shields.io/github/languages/top/eyaltoledano/claude-task-master?style=flat-square&labelColor=343b41)
<br>

[`Claude Task Master`](https://github.com/eyaltoledano/claude-task-master) &nbsp; by &nbsp; [eyaltoledano](https://github.com/eyaltoledano)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
A task management system for AI-driven development with Claude, designed to work seamlessly with Cursor AI.

[![Stars](https://img.shields.io/github/stars/eyaltoledano/claude-task-master?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eyaltoledano/claude-task-master/stargazers) ![License](https://img.shields.io/github/license/eyaltoledano/claude-task-master?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eyaltoledano/claude-task-master?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eyaltoledano/claude-task-master/commits) ![Language](https://img.shields.io/github/languages/top/eyaltoledano/claude-task-master?style=flat-square&labelColor=343b41)
<br>

[`Claude Task Runner`](https://github.com/grahama1970/claude-task-runner) &nbsp; by &nbsp; [grahama1970](https://github.com/grahama1970)    
A specialized tool to manage context isolation and focused task execution with Claude Code, solving the critical challenge of context length limitations and task focus when working with Claude on complex, multi-step projects.

[![Stars](https://img.shields.io/github/stars/grahama1970/claude-task-runner?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-task-runner/stargazers) ![License](https://img.shields.io/github/license/grahama1970/claude-task-runner?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/grahama1970/claude-task-runner?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-task-runner/commits) ![Language](https://img.shields.io/github/languages/top/grahama1970/claude-task-runner?style=flat-square&labelColor=343b41)
<br>

[`Claude Task Runner`](https://github.com/grahama1970/claude-task-runner) &nbsp; by &nbsp; [grahama1970](https://github.com/grahama1970)    
A specialized tool to manage context isolation and focused task execution with Claude Code, solving the critical challenge of context length limitations and task focus when working with Claude on complex, multi-step projects.

[![Stars](https://img.shields.io/github/stars/grahama1970/claude-task-runner?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-task-runner/stargazers) ![License](https://img.shields.io/github/license/grahama1970/claude-task-runner?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/grahama1970/claude-task-runner?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-task-runner/commits) ![Language](https://img.shields.io/github/languages/top/grahama1970/claude-task-runner?style=flat-square&labelColor=343b41)
<br>

[`Happy Coder`](https://github.com/slopus/happy) &nbsp; by &nbsp; [GrocerPublishAgent](https://peoplesgrocers.com/en/projects)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Spawn and control multiple Claude Codes in parallel from your phone or desktop. Happy Coder runs Claude Code on your hardware, sends push notifications when Claude needs more input or permission, and costs nothing.

[![Stars](https://img.shields.io/github/stars/slopus/happy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slopus/happy/stargazers) ![License](https://img.shields.io/github/license/slopus/happy?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/slopus/happy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slopus/happy/commits) ![Language](https://img.shields.io/github/languages/top/slopus/happy?style=flat-square&labelColor=343b41)
<br>

[`Happy Coder`](https://github.com/slopus/happy) &nbsp; by &nbsp; [GrocerPublishAgent](https://peoplesgrocers.com/en/projects)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Spawn and control multiple Claude Codes in parallel from your phone or desktop. Happy Coder runs Claude Code on your hardware, sends push notifications when Claude needs more input or permission, and costs nothing.

[![Stars](https://img.shields.io/github/stars/slopus/happy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slopus/happy/stargazers) ![License](https://img.shields.io/github/license/slopus/happy?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/slopus/happy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slopus/happy/commits) ![Language](https://img.shields.io/github/languages/top/slopus/happy?style=flat-square&labelColor=343b41)
<br>

[`The Agentic Startup`](https://github.com/rsmdt/the-startup) &nbsp; by &nbsp; [Rudolf Schmidt](https://github.com/rsmdt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Yet Another Claude Orchestrator - a collection of agents, commands, etc., for shipping production code - but I like this because it's comprehensive, well-written, and one of the few resources that actually uses Output Styles! +10 points!

[![Stars](https://img.shields.io/github/stars/rsmdt/the-startup?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rsmdt/the-startup/stargazers) ![License](https://img.shields.io/github/license/rsmdt/the-startup?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rsmdt/the-startup?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rsmdt/the-startup/commits) ![Language](https://img.shields.io/github/languages/top/rsmdt/the-startup?style=flat-square&labelColor=343b41)
<br>

[`The Agentic Startup`](https://github.com/rsmdt/the-startup) &nbsp; by &nbsp; [Rudolf Schmidt](https://github.com/rsmdt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Yet Another Claude Orchestrator - a collection of agents, commands, etc., for shipping production code - but I like this because it's comprehensive, well-written, and one of the few resources that actually uses Output Styles! +10 points!

[![Stars](https://img.shields.io/github/stars/rsmdt/the-startup?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rsmdt/the-startup/stargazers) ![License](https://img.shields.io/github/license/rsmdt/the-startup?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rsmdt/the-startup?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rsmdt/the-startup/commits) ![Language](https://img.shields.io/github/languages/top/rsmdt/the-startup?style=flat-square&labelColor=343b41)
<br>

[`TSK - AI Agent Task Manager and Sandbox`](https://github.com/dtormoen/tsk) &nbsp; by &nbsp; [dtormoen](https://github.com/dtormoen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Rust CLI tool that lets you delegate development tasks to AI agents running in sandboxed Docker environments. Multiple agents work in parallel, returning git branches for human review.

[![Stars](https://img.shields.io/github/stars/dtormoen/tsk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dtormoen/tsk/stargazers) ![License](https://img.shields.io/github/license/dtormoen/tsk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dtormoen/tsk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dtormoen/tsk/commits) ![Language](https://img.shields.io/github/languages/top/dtormoen/tsk?style=flat-square&labelColor=343b41)
<br>

[`TSK - AI Agent Task Manager and Sandbox`](https://github.com/dtormoen/tsk) &nbsp; by &nbsp; [dtormoen](https://github.com/dtormoen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Rust CLI tool that lets you delegate development tasks to AI agents running in sandboxed Docker environments. Multiple agents work in parallel, returning git branches for human review.

[![Stars](https://img.shields.io/github/stars/dtormoen/tsk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dtormoen/tsk/stargazers) ![License](https://img.shields.io/github/license/dtormoen/tsk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dtormoen/tsk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dtormoen/tsk/commits) ![Language](https://img.shields.io/github/languages/top/dtormoen/tsk?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Status Lines 📊 [🔝](#awesome-claude-code)

> **Status lines** - Configurations and customizations for Claude Code's status bar functionality

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`ccstatusline`](https://github.com/sirmalloc/ccstatusline) &nbsp; by &nbsp; [sirmalloc](https://github.com/sirmalloc)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A highly customizable status line formatter for Claude Code CLI that displays model info, git branch, token usage, and other metrics in your terminal.

[![Stars](https://img.shields.io/github/stars/sirmalloc/ccstatusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sirmalloc/ccstatusline/stargazers) ![License](https://img.shields.io/github/license/sirmalloc/ccstatusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sirmalloc/ccstatusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sirmalloc/ccstatusline/commits) ![Language](https://img.shields.io/github/languages/top/sirmalloc/ccstatusline?style=flat-square&labelColor=343b41)
<br>

[`ccstatusline`](https://github.com/sirmalloc/ccstatusline) &nbsp; by &nbsp; [sirmalloc](https://github.com/sirmalloc)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A highly customizable status line formatter for Claude Code CLI that displays model info, git branch, token usage, and other metrics in your terminal.

[![Stars](https://img.shields.io/github/stars/sirmalloc/ccstatusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sirmalloc/ccstatusline/stargazers) ![License](https://img.shields.io/github/license/sirmalloc/ccstatusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sirmalloc/ccstatusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sirmalloc/ccstatusline/commits) ![Language](https://img.shields.io/github/languages/top/sirmalloc/ccstatusline?style=flat-square&labelColor=343b41)
<br>

[`claude-code-statusline`](https://github.com/rz1989s/claude-code-statusline) &nbsp; by &nbsp; [rz1989s](https://github.com/rz1989s)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enhanced 4-line statusline for Claude Code with themes, cost tracking, and MCP server monitoring

[![Stars](https://img.shields.io/github/stars/rz1989s/claude-code-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rz1989s/claude-code-statusline/stargazers) ![License](https://img.shields.io/github/license/rz1989s/claude-code-statusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rz1989s/claude-code-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rz1989s/claude-code-statusline/commits) ![Language](https://img.shields.io/github/languages/top/rz1989s/claude-code-statusline?style=flat-square&labelColor=343b41)
<br>

[`claude-code-statusline`](https://github.com/rz1989s/claude-code-statusline) &nbsp; by &nbsp; [rz1989s](https://github.com/rz1989s)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enhanced 4-line statusline for Claude Code with themes, cost tracking, and MCP server monitoring

[![Stars](https://img.shields.io/github/stars/rz1989s/claude-code-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rz1989s/claude-code-statusline/stargazers) ![License](https://img.shields.io/github/license/rz1989s/claude-code-statusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rz1989s/claude-code-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rz1989s/claude-code-statusline/commits) ![Language](https://img.shields.io/github/languages/top/rz1989s/claude-code-statusline?style=flat-square&labelColor=343b41)
<br>

[`claude-powerline`](https://github.com/Owloops/claude-powerline) &nbsp; by &nbsp; [Owloops](https://github.com/Owloops)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A vim-style powerline statusline for Claude Code with real-time usage tracking, git integration, custom themes, and more

[![Stars](https://img.shields.io/github/stars/Owloops/claude-powerline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Owloops/claude-powerline/stargazers) ![License](https://img.shields.io/github/license/Owloops/claude-powerline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Owloops/claude-powerline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Owloops/claude-powerline/commits) ![Language](https://img.shields.io/github/languages/top/Owloops/claude-powerline?style=flat-square&labelColor=343b41)
<br>

[`claude-powerline`](https://github.com/Owloops/claude-powerline) &nbsp; by &nbsp; [Owloops](https://github.com/Owloops)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A vim-style powerline statusline for Claude Code with real-time usage tracking, git integration, custom themes, and more

[![Stars](https://img.shields.io/github/stars/Owloops/claude-powerline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Owloops/claude-powerline/stargazers) ![License](https://img.shields.io/github/license/Owloops/claude-powerline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Owloops/claude-powerline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Owloops/claude-powerline/commits) ![Language](https://img.shields.io/github/languages/top/Owloops/claude-powerline?style=flat-square&labelColor=343b41)
<br>

[`claudia-statusline`](https://github.com/hagan/claudia-statusline) &nbsp; by &nbsp; [Hagan Franks](https://github.com/hagan)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
High-performance Rust-based statusline for Claude Code with persistent stats tracking, progress bars, and optional cloud sync. Features SQLite-first persistence, git integration, context progress bars, burn rate calculation, XDG-compliant with theme support (dark/light, NO_COLOR).

[![Stars](https://img.shields.io/github/stars/hagan/claudia-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hagan/claudia-statusline/stargazers) ![License](https://img.shields.io/github/license/hagan/claudia-statusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hagan/claudia-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hagan/claudia-statusline/commits) ![Language](https://img.shields.io/github/languages/top/hagan/claudia-statusline?style=flat-square&labelColor=343b41)
<br>

[`claudia-statusline`](https://github.com/hagan/claudia-statusline) &nbsp; by &nbsp; [Hagan Franks](https://github.com/hagan)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
High-performance Rust-based statusline for Claude Code with persistent stats tracking, progress bars, and optional cloud sync. Features SQLite-first persistence, git integration, context progress bars, burn rate calculation, XDG-compliant with theme support (dark/light, NO_COLOR).

[![Stars](https://img.shields.io/github/stars/hagan/claudia-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hagan/claudia-statusline/stargazers) ![License](https://img.shields.io/github/license/hagan/claudia-statusline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hagan/claudia-statusline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hagan/claudia-statusline/commits) ![Language](https://img.shields.io/github/languages/top/hagan/claudia-statusline?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Hooks 🪝 [🔝](#awesome-claude-code)

> **Hooks** are a powerful API for Claude Code that allows users to activate commands and run scripts at different points in Claude's agentic lifecycle.

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`CC Notify`](https://github.com/dazuiba/CCNotify) &nbsp; by &nbsp; [dazuiba](https://github.com/dazuiba)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
CCNotify provides desktop notifications for Claude Code, alerting you to input needs or task completion, with one-click jumps back to VS Code and task duration display.

[![Stars](https://img.shields.io/github/stars/dazuiba/CCNotify?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dazuiba/CCNotify/stargazers) ![License](https://img.shields.io/github/license/dazuiba/CCNotify?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dazuiba/CCNotify?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dazuiba/CCNotify/commits) ![Language](https://img.shields.io/github/languages/top/dazuiba/CCNotify?style=flat-square&labelColor=343b41)
<br>

[`CC Notify`](https://github.com/dazuiba/CCNotify) &nbsp; by &nbsp; [dazuiba](https://github.com/dazuiba)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
CCNotify provides desktop notifications for Claude Code, alerting you to input needs or task completion, with one-click jumps back to VS Code and task duration display.

[![Stars](https://img.shields.io/github/stars/dazuiba/CCNotify?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dazuiba/CCNotify/stargazers) ![License](https://img.shields.io/github/license/dazuiba/CCNotify?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/dazuiba/CCNotify?style=flat-square&logo=github&labelColor=343b41)](https://github.com/dazuiba/CCNotify/commits) ![Language](https://img.shields.io/github/languages/top/dazuiba/CCNotify?style=flat-square&labelColor=343b41)
<br>

[`cchooks`](https://github.com/GowayLee/cchooks) &nbsp; by &nbsp; [GowayLee](https://github.com/GowayLee)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A lightweight Python SDK with a clean API and good documentation; simplifies the process of writing hooks and integrating them into your codebase, providing a nice abstraction over the JSON configuration files.

[![Stars](https://img.shields.io/github/stars/GowayLee/cchooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GowayLee/cchooks/stargazers) ![License](https://img.shields.io/github/license/GowayLee/cchooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GowayLee/cchooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GowayLee/cchooks/commits) ![Language](https://img.shields.io/github/languages/top/GowayLee/cchooks?style=flat-square&labelColor=343b41)
<br>

[`cchooks`](https://github.com/GowayLee/cchooks) &nbsp; by &nbsp; [GowayLee](https://github.com/GowayLee)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A lightweight Python SDK with a clean API and good documentation; simplifies the process of writing hooks and integrating them into your codebase, providing a nice abstraction over the JSON configuration files.

[![Stars](https://img.shields.io/github/stars/GowayLee/cchooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GowayLee/cchooks/stargazers) ![License](https://img.shields.io/github/license/GowayLee/cchooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GowayLee/cchooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GowayLee/cchooks/commits) ![Language](https://img.shields.io/github/languages/top/GowayLee/cchooks?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Hook Comms (HCOM)`](https://github.com/aannoo/claude-hook-comms) &nbsp; by &nbsp; [aannoo](https://github.com/aannoo)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Lightweight CLI tool for real-time communication between Claude Code sub agents using hooks. Enables multi-agent collaboration with @-mention targeting, live dashboard monitoring, and zero-dependency implementation.

[![Stars](https://img.shields.io/github/stars/aannoo/claude-hook-comms?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aannoo/claude-hook-comms/stargazers) ![License](https://img.shields.io/github/license/aannoo/claude-hook-comms?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/aannoo/claude-hook-comms?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aannoo/claude-hook-comms/commits) ![Language](https://img.shields.io/github/languages/top/aannoo/claude-hook-comms?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Hook Comms (HCOM)`](https://github.com/aannoo/claude-hook-comms) &nbsp; by &nbsp; [aannoo](https://github.com/aannoo)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Lightweight CLI tool for real-time communication between Claude Code sub agents using hooks. Enables multi-agent collaboration with @-mention targeting, live dashboard monitoring, and zero-dependency implementation.

[![Stars](https://img.shields.io/github/stars/aannoo/claude-hook-comms?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aannoo/claude-hook-comms/stargazers) ![License](https://img.shields.io/github/license/aannoo/claude-hook-comms?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/aannoo/claude-hook-comms?style=flat-square&logo=github&labelColor=343b41)](https://github.com/aannoo/claude-hook-comms/commits) ![Language](https://img.shields.io/github/languages/top/aannoo/claude-hook-comms?style=flat-square&labelColor=343b41)
<br>

[`claude-code-guardian`](https://github.com/jfpedroza/claude-code-guardian) &nbsp; by &nbsp; [jfpedroza](https://github.com/jfpedroza)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Validation and permission system for Claude Code focused on controlling what Claude Code can execute, read or write. Allows users to define a set of rules to evaluate. E.g., allow `git push` but not `git push --force`.

[![Stars](https://img.shields.io/github/stars/jfpedroza/claude-code-guardian?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jfpedroza/claude-code-guardian/stargazers) ![License](https://img.shields.io/github/license/jfpedroza/claude-code-guardian?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jfpedroza/claude-code-guardian?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jfpedroza/claude-code-guardian/commits) ![Language](https://img.shields.io/github/languages/top/jfpedroza/claude-code-guardian?style=flat-square&labelColor=343b41)
<br>

[`claude-code-guardian`](https://github.com/jfpedroza/claude-code-guardian) &nbsp; by &nbsp; [jfpedroza](https://github.com/jfpedroza)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Validation and permission system for Claude Code focused on controlling what Claude Code can execute, read or write. Allows users to define a set of rules to evaluate. E.g., allow `git push` but not `git push --force`.

[![Stars](https://img.shields.io/github/stars/jfpedroza/claude-code-guardian?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jfpedroza/claude-code-guardian/stargazers) ![License](https://img.shields.io/github/license/jfpedroza/claude-code-guardian?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jfpedroza/claude-code-guardian?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jfpedroza/claude-code-guardian/commits) ![Language](https://img.shields.io/github/languages/top/jfpedroza/claude-code-guardian?style=flat-square&labelColor=343b41)
<br>

[`claude-code-hooks-sdk`](https://github.com/beyondcode/claude-hooks-sdk) &nbsp; by &nbsp; [beyondcode](https://github.com/beyondcode)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Laravel-inspired PHP SDK for building Claude Code hook responses with a clean, fluent API. This SDK makes it easy to create structured JSON responses for Claude Code hooks using an expressive, chainable interface.

[![Stars](https://img.shields.io/github/stars/beyondcode/claude-hooks-sdk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/beyondcode/claude-hooks-sdk/stargazers) ![License](https://img.shields.io/github/license/beyondcode/claude-hooks-sdk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/beyondcode/claude-hooks-sdk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/beyondcode/claude-hooks-sdk/commits) ![Language](https://img.shields.io/github/languages/top/beyondcode/claude-hooks-sdk?style=flat-square&labelColor=343b41)
<br>

[`claude-code-hooks-sdk`](https://github.com/beyondcode/claude-hooks-sdk) &nbsp; by &nbsp; [beyondcode](https://github.com/beyondcode)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A Laravel-inspired PHP SDK for building Claude Code hook responses with a clean, fluent API. This SDK makes it easy to create structured JSON responses for Claude Code hooks using an expressive, chainable interface.

[![Stars](https://img.shields.io/github/stars/beyondcode/claude-hooks-sdk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/beyondcode/claude-hooks-sdk/stargazers) ![License](https://img.shields.io/github/license/beyondcode/claude-hooks-sdk?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/beyondcode/claude-hooks-sdk?style=flat-square&logo=github&labelColor=343b41)](https://github.com/beyondcode/claude-hooks-sdk/commits) ![Language](https://img.shields.io/github/languages/top/beyondcode/claude-hooks-sdk?style=flat-square&labelColor=343b41)
<br>

[`claude-hooks`](https://github.com/johnlindquist/claude-hooks) &nbsp; by &nbsp; [John Lindquist](https://github.com/johnlindquist)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A TypeScript-based system for configuring and customizing Claude Code hooks with a powerful and flexible interface.

[![Stars](https://img.shields.io/github/stars/johnlindquist/claude-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/johnlindquist/claude-hooks/stargazers) ![License](https://img.shields.io/github/license/johnlindquist/claude-hooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/johnlindquist/claude-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/johnlindquist/claude-hooks/commits) ![Language](https://img.shields.io/github/languages/top/johnlindquist/claude-hooks?style=flat-square&labelColor=343b41)
<br>

[`claude-hooks`](https://github.com/johnlindquist/claude-hooks) &nbsp; by &nbsp; [John Lindquist](https://github.com/johnlindquist)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A TypeScript-based system for configuring and customizing Claude Code hooks with a powerful and flexible interface.

[![Stars](https://img.shields.io/github/stars/johnlindquist/claude-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/johnlindquist/claude-hooks/stargazers) ![License](https://img.shields.io/github/license/johnlindquist/claude-hooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/johnlindquist/claude-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/johnlindquist/claude-hooks/commits) ![Language](https://img.shields.io/github/languages/top/johnlindquist/claude-hooks?style=flat-square&labelColor=343b41)
<br>

[`claude-mem`](https://github.com/thedotmack/claude-mem) &nbsp; by &nbsp; [Alex Newman](https://github.com/thedotmack)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Persistent memory compression system that captures tool usage, generates AI-powered session summaries, and injects relevant context into future Claude Code sessions through SQLite storage and full-text search across project history (and no extra-cost dependencies!). 🦾

[![Stars](https://img.shields.io/github/stars/thedotmack/claude-mem?style=flat-square&logo=github&labelColor=343b41)](https://github.com/thedotmack/claude-mem/stargazers) ![License](https://img.shields.io/github/license/thedotmack/claude-mem?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/thedotmack/claude-mem?style=flat-square&logo=github&labelColor=343b41)](https://github.com/thedotmack/claude-mem/commits) ![Language](https://img.shields.io/github/languages/top/thedotmack/claude-mem?style=flat-square&labelColor=343b41)
<br>

[`claude-mem`](https://github.com/thedotmack/claude-mem) &nbsp; by &nbsp; [Alex Newman](https://github.com/thedotmack)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Persistent memory compression system that captures tool usage, generates AI-powered session summaries, and injects relevant context into future Claude Code sessions through SQLite storage and full-text search across project history (and no extra-cost dependencies!). 🦾

[![Stars](https://img.shields.io/github/stars/thedotmack/claude-mem?style=flat-square&logo=github&labelColor=343b41)](https://github.com/thedotmack/claude-mem/stargazers) ![License](https://img.shields.io/github/license/thedotmack/claude-mem?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/thedotmack/claude-mem?style=flat-square&logo=github&labelColor=343b41)](https://github.com/thedotmack/claude-mem/commits) ![Language](https://img.shields.io/github/languages/top/thedotmack/claude-mem?style=flat-square&labelColor=343b41)
<br>

[`Claudio`](https://github.com/ctoth/claudio) &nbsp; by &nbsp; [Christopher Toth](https://github.com/ctoth)    
A no-frills little library that adds delightful OS-native sounds to Claude Code via simple hooks. It really sparks joy.

[![Stars](https://img.shields.io/github/stars/ctoth/claudio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ctoth/claudio/stargazers) ![License](https://img.shields.io/github/license/ctoth/claudio?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ctoth/claudio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ctoth/claudio/commits) ![Language](https://img.shields.io/github/languages/top/ctoth/claudio?style=flat-square&labelColor=343b41)
<br>

[`Claudio`](https://github.com/ctoth/claudio) &nbsp; by &nbsp; [Christopher Toth](https://github.com/ctoth)    
A no-frills little library that adds delightful OS-native sounds to Claude Code via simple hooks. It really sparks joy.

[![Stars](https://img.shields.io/github/stars/ctoth/claudio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ctoth/claudio/stargazers) ![License](https://img.shields.io/github/license/ctoth/claudio?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ctoth/claudio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ctoth/claudio/commits) ![Language](https://img.shields.io/github/languages/top/ctoth/claudio?style=flat-square&labelColor=343b41)
<br>

[`fcakyon Collection (Code Quality and Tool Usage)`](https://github.com/fcakyon/claude-codex-settings/tree/main/.claude/hooks) &nbsp; by &nbsp; [Fatih Akyon](https://github.com/fcakyon)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Very well-written set of hooks for code quality and tool usage regulation (e.g. force Tavily over WebFetch tool).

[![Stars](https://img.shields.io/github/stars/fcakyon/claude-codex-settings?style=flat-square&logo=github&labelColor=343b41)](https://github.com/fcakyon/claude-codex-settings/stargazers) ![License](https://img.shields.io/github/license/fcakyon/claude-codex-settings?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/fcakyon/claude-codex-settings?style=flat-square&logo=github&labelColor=343b41)](https://github.com/fcakyon/claude-codex-settings/commits) ![Language](https://img.shields.io/github/languages/top/fcakyon/claude-codex-settings?style=flat-square&labelColor=343b41)
<br>

[`fcakyon Collection (Code Quality and Tool Usage)`](https://github.com/fcakyon/claude-codex-settings/tree/main/.claude/hooks) &nbsp; by &nbsp; [Fatih Akyon](https://github.com/fcakyon)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Very well-written set of hooks for code quality and tool usage regulation (e.g. force Tavily over WebFetch tool).

[![Stars](https://img.shields.io/github/stars/fcakyon/claude-codex-settings?style=flat-square&logo=github&labelColor=343b41)](https://github.com/fcakyon/claude-codex-settings/stargazers) ![License](https://img.shields.io/github/license/fcakyon/claude-codex-settings?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/fcakyon/claude-codex-settings?style=flat-square&logo=github&labelColor=343b41)](https://github.com/fcakyon/claude-codex-settings/commits) ![Language](https://img.shields.io/github/languages/top/fcakyon/claude-codex-settings?style=flat-square&labelColor=343b41)
<br>

[`TDD Guard`](https://github.com/nizos/tdd-guard) &nbsp; by &nbsp; [Nizar Selander](https://github.com/nizos)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A hooks-driven system that monitors file operations in real-time and blocks changes that violate TDD principles.

[![Stars](https://img.shields.io/github/stars/nizos/tdd-guard?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nizos/tdd-guard/stargazers) ![License](https://img.shields.io/github/license/nizos/tdd-guard?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/nizos/tdd-guard?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nizos/tdd-guard/commits) ![Language](https://img.shields.io/github/languages/top/nizos/tdd-guard?style=flat-square&labelColor=343b41)
<br>

[`TDD Guard`](https://github.com/nizos/tdd-guard) &nbsp; by &nbsp; [Nizar Selander](https://github.com/nizos)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A hooks-driven system that monitors file operations in real-time and blocks changes that violate TDD principles.

[![Stars](https://img.shields.io/github/stars/nizos/tdd-guard?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nizos/tdd-guard/stargazers) ![License](https://img.shields.io/github/license/nizos/tdd-guard?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/nizos/tdd-guard?style=flat-square&logo=github&labelColor=343b41)](https://github.com/nizos/tdd-guard/commits) ![Language](https://img.shields.io/github/languages/top/nizos/tdd-guard?style=flat-square&labelColor=343b41)
<br>

[`TypeScript Quality Hooks`](https://github.com/bartolli/claude-code-typescript-hooks) &nbsp; by &nbsp; [bartolli](https://github.com/bartolli)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Quality check hook for Node.js TypeScript projects with TypeScript compilation. ESLint auto-fixing, and Prettier formatting. Uses SHA256 config caching for <5ms validation performance during real-time editing.

[![Stars](https://img.shields.io/github/stars/bartolli/claude-code-typescript-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/claude-code-typescript-hooks/stargazers) ![License](https://img.shields.io/github/license/bartolli/claude-code-typescript-hooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/bartolli/claude-code-typescript-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/claude-code-typescript-hooks/commits) ![Language](https://img.shields.io/github/languages/top/bartolli/claude-code-typescript-hooks?style=flat-square&labelColor=343b41)
<br>

[`TypeScript Quality Hooks`](https://github.com/bartolli/claude-code-typescript-hooks) &nbsp; by &nbsp; [bartolli](https://github.com/bartolli)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Quality check hook for Node.js TypeScript projects with TypeScript compilation. ESLint auto-fixing, and Prettier formatting. Uses SHA256 config caching for <5ms validation performance during real-time editing.

[![Stars](https://img.shields.io/github/stars/bartolli/claude-code-typescript-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/claude-code-typescript-hooks/stargazers) ![License](https://img.shields.io/github/license/bartolli/claude-code-typescript-hooks?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/bartolli/claude-code-typescript-hooks?style=flat-square&logo=github&labelColor=343b41)](https://github.com/bartolli/claude-code-typescript-hooks/commits) ![Language](https://img.shields.io/github/languages/top/bartolli/claude-code-typescript-hooks?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Output Styles 💬 [🔝](#awesome-claude-code)

> **Output styles** allow you to use Claude Code as any type of agent while keeping its core capabilities, such as running local scripts, reading/writing files, and tracking TODOs.

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`ccoutputstyles`](https://github.com/viveknair/ccoutputstyles) &nbsp; by &nbsp; [Vivek Nair](https://github.com/viveknair)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
CLI tool and template gallery for customizing Claude Code output styles with pre-built templates. Features over 15 templates at the time of writing!

[![Stars](https://img.shields.io/github/stars/viveknair/ccoutputstyles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/viveknair/ccoutputstyles/stargazers) ![License](https://img.shields.io/github/license/viveknair/ccoutputstyles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/viveknair/ccoutputstyles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/viveknair/ccoutputstyles/commits) ![Language](https://img.shields.io/github/languages/top/viveknair/ccoutputstyles?style=flat-square&labelColor=343b41)
<br>

[`ccoutputstyles`](https://github.com/viveknair/ccoutputstyles) &nbsp; by &nbsp; [Vivek Nair](https://github.com/viveknair)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
CLI tool and template gallery for customizing Claude Code output styles with pre-built templates. Features over 15 templates at the time of writing!

[![Stars](https://img.shields.io/github/stars/viveknair/ccoutputstyles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/viveknair/ccoutputstyles/stargazers) ![License](https://img.shields.io/github/license/viveknair/ccoutputstyles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/viveknair/ccoutputstyles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/viveknair/ccoutputstyles/commits) ![Language](https://img.shields.io/github/languages/top/viveknair/ccoutputstyles?style=flat-square&labelColor=343b41)
<br>

[`Claude X`](https://github.com/kunwar-shah/claudex) &nbsp; by &nbsp; [Kunwar Shah](https://github.com/kunwar-shah)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claudex - A friendly viewer, Browse and explore your Claude conversations. Features auto project discovery (scans ~/.claude/projects), SQLite FTS5-powered full-text search, session analytics, and export options (JSON, HTML, TXT).

[![Stars](https://img.shields.io/github/stars/kunwar-shah/claudex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kunwar-shah/claudex/stargazers) ![License](https://img.shields.io/github/license/kunwar-shah/claudex?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kunwar-shah/claudex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kunwar-shah/claudex/commits) ![Language](https://img.shields.io/github/languages/top/kunwar-shah/claudex?style=flat-square&labelColor=343b41)
<br>

[`Claude X`](https://github.com/kunwar-shah/claudex) &nbsp; by &nbsp; [Kunwar Shah](https://github.com/kunwar-shah)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Claudex - A friendly viewer, Browse and explore your Claude conversations. Features auto project discovery (scans ~/.claude/projects), SQLite FTS5-powered full-text search, session analytics, and export options (JSON, HTML, TXT).

[![Stars](https://img.shields.io/github/stars/kunwar-shah/claudex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kunwar-shah/claudex/stargazers) ![License](https://img.shields.io/github/license/kunwar-shah/claudex?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kunwar-shah/claudex?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kunwar-shah/claudex/commits) ![Language](https://img.shields.io/github/languages/top/kunwar-shah/claudex?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Slash-Commands 🔪 [🔝](#awesome-claude-code)

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/create-hook`](https://github.com/omril321/automated-notebooklm/blob/main/.claude/commands/create-hook.md) &nbsp; by &nbsp; [Omri Lavi](https://github.com/omril321)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Slash command for hook creation - intelligently prompts you through the creation process with smart suggestions based on your project setup (TS, Prettier, ESLint...).

[![Stars](https://img.shields.io/github/stars/omril321/automated-notebooklm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omril321/automated-notebooklm/stargazers) ![License](https://img.shields.io/github/license/omril321/automated-notebooklm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/omril321/automated-notebooklm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omril321/automated-notebooklm/commits) ![Language](https://img.shields.io/github/languages/top/omril321/automated-notebooklm?style=flat-square&labelColor=343b41)
<br>

[`/create-hook`](https://github.com/omril321/automated-notebooklm/blob/main/.claude/commands/create-hook.md) &nbsp; by &nbsp; [Omri Lavi](https://github.com/omril321)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Slash command for hook creation - intelligently prompts you through the creation process with smart suggestions based on your project setup (TS, Prettier, ESLint...).

[![Stars](https://img.shields.io/github/stars/omril321/automated-notebooklm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omril321/automated-notebooklm/stargazers) ![License](https://img.shields.io/github/license/omril321/automated-notebooklm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/omril321/automated-notebooklm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/omril321/automated-notebooklm/commits) ![Language](https://img.shields.io/github/languages/top/omril321/automated-notebooklm?style=flat-square&labelColor=343b41)
<br>

[`/linux-desktop-slash-commands`](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands) &nbsp; by &nbsp; [Daniel Rosehill](https://github.com/danielrosehill)    
A library of slash commands intended specifically to facilitate common and advanced operations on Linux desktop environments (although many would also be useful on Linux servers). Command groups include hardware benchmarking, filesystem organisation, and security posture validation.

[![Stars](https://img.shields.io/github/stars/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&logo=github&labelColor=343b41)](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands/stargazers) ![License](https://img.shields.io/github/license/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&logo=github&labelColor=343b41)](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands/commits) ![Language](https://img.shields.io/github/languages/top/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&labelColor=343b41)
<br>

[`/linux-desktop-slash-commands`](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands) &nbsp; by &nbsp; [Daniel Rosehill](https://github.com/danielrosehill)    
A library of slash commands intended specifically to facilitate common and advanced operations on Linux desktop environments (although many would also be useful on Linux servers). Command groups include hardware benchmarking, filesystem organisation, and security posture validation.

[![Stars](https://img.shields.io/github/stars/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&logo=github&labelColor=343b41)](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands/stargazers) ![License](https://img.shields.io/github/license/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&logo=github&labelColor=343b41)](https://github.com/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands/commits) ![Language](https://img.shields.io/github/languages/top/danielrosehill/Claude-Code-Linux-Desktop-Slash-Commands?style=flat-square&labelColor=343b41)
<br>

[`Session Driven Development`](https://github.com/ankushdixit/sdd) &nbsp; by &nbsp; [Ankush Dixit](https://github.com/ankushdixit)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
SDD implements Session-Driven Development, a comprehensive methodology that enables AI coding assistants to work on software projects across multiple sessions with perfect context continuity, enforced quality standards, and accumulated institutional knowledge.

[![Stars](https://img.shields.io/github/stars/ankushdixit/sdd?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ankushdixit/sdd/stargazers) ![License](https://img.shields.io/github/license/ankushdixit/sdd?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ankushdixit/sdd?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ankushdixit/sdd/commits) ![Language](https://img.shields.io/github/languages/top/ankushdixit/sdd?style=flat-square&labelColor=343b41)
<br>

[`Session Driven Development`](https://github.com/ankushdixit/sdd) &nbsp; by &nbsp; [Ankush Dixit](https://github.com/ankushdixit)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
SDD implements Session-Driven Development, a comprehensive methodology that enables AI coding assistants to work on software projects across multiple sessions with perfect context continuity, enforced quality standards, and accumulated institutional knowledge.

[![Stars](https://img.shields.io/github/stars/ankushdixit/sdd?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ankushdixit/sdd/stargazers) ![License](https://img.shields.io/github/license/ankushdixit/sdd?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ankushdixit/sdd?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ankushdixit/sdd/commits) ![Language](https://img.shields.io/github/languages/top/ankushdixit/sdd?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Version Control & Git <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/commit-fast`](https://github.com/steadycursor/steadystart/blob/main/.claude/commands/2-commit-fast.md) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Automates git commit process by selecting the first suggested message, generating structured commits with consistent formatting while skipping manual confirmation and removing Claude co-Contributorship footer

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`/commit-fast`](https://github.com/steadycursor/steadystart/blob/main/.claude/commands/2-commit-fast.md) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Automates git commit process by selecting the first suggested message, generating structured commits with consistent formatting while skipping manual confirmation and removing Claude co-Contributorship footer

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`/analyze-issue`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/analyze-issue.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Fetches GitHub issue details to create comprehensive implementation specifications, analyzing requirements and planning structured approach with clear implementation steps.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/analyze-issue`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/analyze-issue.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Fetches GitHub issue details to create comprehensive implementation specifications, analyzing requirements and planning structured approach with clear implementation steps.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/commit`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/commit.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates git commits using conventional commit format with appropriate emojis, following project standards and creating descriptive messages that explain the purpose of changes.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/commit`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/commit.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates git commits using conventional commit format with appropriate emojis, following project standards and creating descriptive messages that explain the purpose of changes.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/create-pr`](https://github.com/toyamarinyon/giselle/blob/main/.claude/commands/create-pr.md) &nbsp; by &nbsp; [toyamarinyon](https://github.com/toyamarinyon)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Streamlines pull request creation by handling the entire workflow: creating a new branch, committing changes, formatting modified files with Biome, and submitting the PR.

[![Stars](https://img.shields.io/github/stars/toyamarinyon/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/toyamarinyon/giselle/stargazers) ![License](https://img.shields.io/github/license/toyamarinyon/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/toyamarinyon/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/toyamarinyon/giselle/commits) ![Language](https://img.shields.io/github/languages/top/toyamarinyon/giselle?style=flat-square&labelColor=343b41)
<br>

[`/create-pr`](https://github.com/toyamarinyon/giselle/blob/main/.claude/commands/create-pr.md) &nbsp; by &nbsp; [toyamarinyon](https://github.com/toyamarinyon)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Streamlines pull request creation by handling the entire workflow: creating a new branch, committing changes, formatting modified files with Biome, and submitting the PR.

[![Stars](https://img.shields.io/github/stars/toyamarinyon/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/toyamarinyon/giselle/stargazers) ![License](https://img.shields.io/github/license/toyamarinyon/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/toyamarinyon/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/toyamarinyon/giselle/commits) ![Language](https://img.shields.io/github/languages/top/toyamarinyon/giselle?style=flat-square&labelColor=343b41)
<br>

[`/create-pull-request`](https://github.com/liam-hq/liam/blob/main/.claude/commands/create-pull-request.md) &nbsp; by &nbsp; [liam-hq](https://github.com/liam-hq)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides comprehensive PR creation guidance with GitHub CLI, enforcing title conventions, following template structure, and offering concrete command examples with best practices.

[![Stars](https://img.shields.io/github/stars/liam-hq/liam?style=flat-square&logo=github&labelColor=343b41)](https://github.com/liam-hq/liam/stargazers) ![License](https://img.shields.io/github/license/liam-hq/liam?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/liam-hq/liam?style=flat-square&logo=github&labelColor=343b41)](https://github.com/liam-hq/liam/commits) ![Language](https://img.shields.io/github/languages/top/liam-hq/liam?style=flat-square&labelColor=343b41)
<br>

[`/create-pull-request`](https://github.com/liam-hq/liam/blob/main/.claude/commands/create-pull-request.md) &nbsp; by &nbsp; [liam-hq](https://github.com/liam-hq)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides comprehensive PR creation guidance with GitHub CLI, enforcing title conventions, following template structure, and offering concrete command examples with best practices.

[![Stars](https://img.shields.io/github/stars/liam-hq/liam?style=flat-square&logo=github&labelColor=343b41)](https://github.com/liam-hq/liam/stargazers) ![License](https://img.shields.io/github/license/liam-hq/liam?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/liam-hq/liam?style=flat-square&logo=github&labelColor=343b41)](https://github.com/liam-hq/liam/commits) ![Language](https://img.shields.io/github/languages/top/liam-hq/liam?style=flat-square&labelColor=343b41)
<br>

[`/create-worktrees`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/create-worktrees.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates git worktrees for all open PRs or specific branches, handling branches with slashes, cleaning up stale worktrees, and supporting custom branch creation for development.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/create-worktrees`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/create-worktrees.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates git worktrees for all open PRs or specific branches, handling branches with slashes, cleaning up stale worktrees, and supporting custom branch creation for development.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/fix-github-issue`](https://github.com/jeremymailen/kotlinter-gradle/blob/master/.claude/commands/fix-github-issue.md) &nbsp; by &nbsp; [jeremymailen](https://github.com/jeremymailen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Analyzes and fixes GitHub issues using a structured approach with GitHub CLI for issue details, implementing necessary code changes, running tests, and creating proper commit messages.

[![Stars](https://img.shields.io/github/stars/jeremymailen/kotlinter-gradle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jeremymailen/kotlinter-gradle/stargazers) ![License](https://img.shields.io/github/license/jeremymailen/kotlinter-gradle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jeremymailen/kotlinter-gradle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jeremymailen/kotlinter-gradle/commits) ![Language](https://img.shields.io/github/languages/top/jeremymailen/kotlinter-gradle?style=flat-square&labelColor=343b41)
<br>

[`/fix-github-issue`](https://github.com/jeremymailen/kotlinter-gradle/blob/master/.claude/commands/fix-github-issue.md) &nbsp; by &nbsp; [jeremymailen](https://github.com/jeremymailen)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Analyzes and fixes GitHub issues using a structured approach with GitHub CLI for issue details, implementing necessary code changes, running tests, and creating proper commit messages.

[![Stars](https://img.shields.io/github/stars/jeremymailen/kotlinter-gradle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jeremymailen/kotlinter-gradle/stargazers) ![License](https://img.shields.io/github/license/jeremymailen/kotlinter-gradle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jeremymailen/kotlinter-gradle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jeremymailen/kotlinter-gradle/commits) ![Language](https://img.shields.io/github/languages/top/jeremymailen/kotlinter-gradle?style=flat-square&labelColor=343b41)
<br>

[`/fix-issue`](https://github.com/metabase/metabase/blob/master/.claude/commands/fix-issue.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Addresses GitHub issues by taking issue number as parameter, analyzing context, implementing solution, and testing/validating the fix for proper integration.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`/fix-issue`](https://github.com/metabase/metabase/blob/master/.claude/commands/fix-issue.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Addresses GitHub issues by taking issue number as parameter, analyzing context, implementing solution, and testing/validating the fix for proper integration.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`/fix-pr`](https://github.com/metabase/metabase/blob/master/.claude/commands/fix-pr.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Fetches and fixes unresolved PR comments by automatically retrieving feedback, addressing reviewer concerns, making targeted code improvements, and streamlining the review process.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`/fix-pr`](https://github.com/metabase/metabase/blob/master/.claude/commands/fix-pr.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Fetches and fixes unresolved PR comments by automatically retrieving feedback, addressing reviewer concerns, making targeted code improvements, and streamlining the review process.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`/husky`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/husky.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Sets up and manages Husky Git hooks by configuring pre-commit hooks, establishing commit message standards, integrating with linting tools, and ensuring code quality on commits.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/husky`](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/husky.md) &nbsp; by &nbsp; [evmts](https://github.com/evmts)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Sets up and manages Husky Git hooks by configuring pre-commit hooks, establishing commit message standards, integrating with linting tools, and ensuring code quality on commits.

[![Stars](https://img.shields.io/github/stars/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/stargazers) ![License](https://img.shields.io/github/license/evmts/tevm-monorepo?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/evmts/tevm-monorepo?style=flat-square&logo=github&labelColor=343b41)](https://github.com/evmts/tevm-monorepo/commits) ![Language](https://img.shields.io/github/languages/top/evmts/tevm-monorepo?style=flat-square&labelColor=343b41)
<br>

[`/pr-review`](https://github.com/arkavo-org/opentdf-rs/blob/main/.claude/commands/pr-review.md) &nbsp; by &nbsp; [arkavo-org](https://github.com/arkavo-org)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Reviews pull request changes to provide feedback, check for issues, and suggest improvements before merging into the main codebase.

[![Stars](https://img.shields.io/github/stars/arkavo-org/opentdf-rs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/arkavo-org/opentdf-rs/stargazers) ![License](https://img.shields.io/github/license/arkavo-org/opentdf-rs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/arkavo-org/opentdf-rs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/arkavo-org/opentdf-rs/commits) ![Language](https://img.shields.io/github/languages/top/arkavo-org/opentdf-rs?style=flat-square&labelColor=343b41)
<br>

[`/pr-review`](https://github.com/arkavo-org/opentdf-rs/blob/main/.claude/commands/pr-review.md) &nbsp; by &nbsp; [arkavo-org](https://github.com/arkavo-org)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Reviews pull request changes to provide feedback, check for issues, and suggest improvements before merging into the main codebase.

[![Stars](https://img.shields.io/github/stars/arkavo-org/opentdf-rs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/arkavo-org/opentdf-rs/stargazers) ![License](https://img.shields.io/github/license/arkavo-org/opentdf-rs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/arkavo-org/opentdf-rs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/arkavo-org/opentdf-rs/commits) ![Language](https://img.shields.io/github/languages/top/arkavo-org/opentdf-rs?style=flat-square&labelColor=343b41)
<br>

[`/update-branch-name`](https://github.com/giselles-ai/giselle/blob/main/.claude/commands/update-branch-name.md) &nbsp; by &nbsp; [giselles-ai](https://github.com/giselles-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Updates branch names with proper prefixes and formats, enforcing naming conventions, supporting semantic prefixes, and managing remote branch updates.

[![Stars](https://img.shields.io/github/stars/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/stargazers) ![License](https://img.shields.io/github/license/giselles-ai/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/commits) ![Language](https://img.shields.io/github/languages/top/giselles-ai/giselle?style=flat-square&labelColor=343b41)
<br>

[`/update-branch-name`](https://github.com/giselles-ai/giselle/blob/main/.claude/commands/update-branch-name.md) &nbsp; by &nbsp; [giselles-ai](https://github.com/giselles-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Updates branch names with proper prefixes and formats, enforcing naming conventions, supporting semantic prefixes, and managing remote branch updates.

[![Stars](https://img.shields.io/github/stars/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/stargazers) ![License](https://img.shields.io/github/license/giselles-ai/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/commits) ![Language](https://img.shields.io/github/languages/top/giselles-ai/giselle?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Code Analysis & Testing <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/code_analysis`](https://github.com/kingler/n8n_agent/blob/main/.claude/commands/code_analysis.md) &nbsp; by &nbsp; [kingler](https://github.com/kingler)    
Provides a menu of advanced code analysis commands for deep inspection, including knowledge graph generation, optimization suggestions, and quality evaluation.

[![Stars](https://img.shields.io/github/stars/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/stargazers) ![License](https://img.shields.io/github/license/kingler/n8n_agent?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/commits) ![Language](https://img.shields.io/github/languages/top/kingler/n8n_agent?style=flat-square&labelColor=343b41)
<br>

[`/code_analysis`](https://github.com/kingler/n8n_agent/blob/main/.claude/commands/code_analysis.md) &nbsp; by &nbsp; [kingler](https://github.com/kingler)    
Provides a menu of advanced code analysis commands for deep inspection, including knowledge graph generation, optimization suggestions, and quality evaluation.

[![Stars](https://img.shields.io/github/stars/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/stargazers) ![License](https://img.shields.io/github/license/kingler/n8n_agent?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kingler/n8n_agent?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kingler/n8n_agent/commits) ![Language](https://img.shields.io/github/languages/top/kingler/n8n_agent?style=flat-square&labelColor=343b41)
<br>

[`/check`](https://github.com/rygwdn/slack-tools/blob/main/.claude/commands/check.md) &nbsp; by &nbsp; [rygwdn](https://github.com/rygwdn)    
Performs comprehensive code quality and security checks, featuring static analysis integration, security vulnerability scanning, code style enforcement, and detailed reporting.

[![Stars](https://img.shields.io/github/stars/rygwdn/slack-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rygwdn/slack-tools/stargazers) ![License](https://img.shields.io/github/license/rygwdn/slack-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rygwdn/slack-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rygwdn/slack-tools/commits) ![Language](https://img.shields.io/github/languages/top/rygwdn/slack-tools?style=flat-square&labelColor=343b41)
<br>

[`/check`](https://github.com/rygwdn/slack-tools/blob/main/.claude/commands/check.md) &nbsp; by &nbsp; [rygwdn](https://github.com/rygwdn)    
Performs comprehensive code quality and security checks, featuring static analysis integration, security vulnerability scanning, code style enforcement, and detailed reporting.

[![Stars](https://img.shields.io/github/stars/rygwdn/slack-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rygwdn/slack-tools/stargazers) ![License](https://img.shields.io/github/license/rygwdn/slack-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rygwdn/slack-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rygwdn/slack-tools/commits) ![Language](https://img.shields.io/github/languages/top/rygwdn/slack-tools?style=flat-square&labelColor=343b41)
<br>

[`/clean`](https://github.com/Graphlet-AI/eridu/blob/main/.claude/commands/clean.md) &nbsp; by &nbsp; [Graphlet-AI](https://github.com/Graphlet-AI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Addresses code formatting and quality issues by fixing black formatting problems, organizing imports with isort, resolving flake8 linting issues, and correcting mypy type errors.

[![Stars](https://img.shields.io/github/stars/Graphlet-AI/eridu?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Graphlet-AI/eridu/stargazers) ![License](https://img.shields.io/github/license/Graphlet-AI/eridu?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Graphlet-AI/eridu?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Graphlet-AI/eridu/commits) ![Language](https://img.shields.io/github/languages/top/Graphlet-AI/eridu?style=flat-square&labelColor=343b41)
<br>

[`/clean`](https://github.com/Graphlet-AI/eridu/blob/main/.claude/commands/clean.md) &nbsp; by &nbsp; [Graphlet-AI](https://github.com/Graphlet-AI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Addresses code formatting and quality issues by fixing black formatting problems, organizing imports with isort, resolving flake8 linting issues, and correcting mypy type errors.

[![Stars](https://img.shields.io/github/stars/Graphlet-AI/eridu?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Graphlet-AI/eridu/stargazers) ![License](https://img.shields.io/github/license/Graphlet-AI/eridu?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Graphlet-AI/eridu?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Graphlet-AI/eridu/commits) ![Language](https://img.shields.io/github/languages/top/Graphlet-AI/eridu?style=flat-square&labelColor=343b41)
<br>

[`/optimize`](https://github.com/to4iki/ai-project-rules/blob/main/.claude/commands/optimize.md) &nbsp; by &nbsp; [to4iki](https://github.com/to4iki)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes code performance to identify bottlenecks, proposing concrete optimizations with implementation guidance for improved application performance.

[![Stars](https://img.shields.io/github/stars/to4iki/ai-project-rules?style=flat-square&logo=github&labelColor=343b41)](https://github.com/to4iki/ai-project-rules/stargazers) ![License](https://img.shields.io/github/license/to4iki/ai-project-rules?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/to4iki/ai-project-rules?style=flat-square&logo=github&labelColor=343b41)](https://github.com/to4iki/ai-project-rules/commits) ![Language](https://img.shields.io/github/languages/top/to4iki/ai-project-rules?style=flat-square&labelColor=343b41)
<br>

[`/optimize`](https://github.com/to4iki/ai-project-rules/blob/main/.claude/commands/optimize.md) &nbsp; by &nbsp; [to4iki](https://github.com/to4iki)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes code performance to identify bottlenecks, proposing concrete optimizations with implementation guidance for improved application performance.

[![Stars](https://img.shields.io/github/stars/to4iki/ai-project-rules?style=flat-square&logo=github&labelColor=343b41)](https://github.com/to4iki/ai-project-rules/stargazers) ![License](https://img.shields.io/github/license/to4iki/ai-project-rules?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/to4iki/ai-project-rules?style=flat-square&logo=github&labelColor=343b41)](https://github.com/to4iki/ai-project-rules/commits) ![Language](https://img.shields.io/github/languages/top/to4iki/ai-project-rules?style=flat-square&labelColor=343b41)
<br>

[`/repro-issue`](https://github.com/rzykov/metabase/blob/master/.claude/commands/repro-issue.md) &nbsp; by &nbsp; [rzykov](https://github.com/rzykov)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Creates reproducible test cases for GitHub issues, ensuring tests fail reliably and documenting clear reproduction steps for developers.

[![Stars](https://img.shields.io/github/stars/rzykov/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rzykov/metabase/stargazers) ![License](https://img.shields.io/github/license/rzykov/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rzykov/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rzykov/metabase/commits) ![Language](https://img.shields.io/github/languages/top/rzykov/metabase?style=flat-square&labelColor=343b41)
<br>

[`/repro-issue`](https://github.com/rzykov/metabase/blob/master/.claude/commands/repro-issue.md) &nbsp; by &nbsp; [rzykov](https://github.com/rzykov)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Creates reproducible test cases for GitHub issues, ensuring tests fail reliably and documenting clear reproduction steps for developers.

[![Stars](https://img.shields.io/github/stars/rzykov/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rzykov/metabase/stargazers) ![License](https://img.shields.io/github/license/rzykov/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/rzykov/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/rzykov/metabase/commits) ![Language](https://img.shields.io/github/languages/top/rzykov/metabase?style=flat-square&labelColor=343b41)
<br>

[`/tdd`](https://github.com/zscott/pane/blob/main/.claude/commands/tdd.md) &nbsp; by &nbsp; [zscott](https://github.com/zscott)    
Guides development using Test-Driven Development principles, enforcing Red-Green-Refactor discipline, integrating with git workflow, and managing PR creation.

[![Stars](https://img.shields.io/github/stars/zscott/pane?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zscott/pane/stargazers) ![License](https://img.shields.io/github/license/zscott/pane?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/zscott/pane?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zscott/pane/commits) ![Language](https://img.shields.io/github/languages/top/zscott/pane?style=flat-square&labelColor=343b41)
<br>

[`/tdd`](https://github.com/zscott/pane/blob/main/.claude/commands/tdd.md) &nbsp; by &nbsp; [zscott](https://github.com/zscott)    
Guides development using Test-Driven Development principles, enforcing Red-Green-Refactor discipline, integrating with git workflow, and managing PR creation.

[![Stars](https://img.shields.io/github/stars/zscott/pane?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zscott/pane/stargazers) ![License](https://img.shields.io/github/license/zscott/pane?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/zscott/pane?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zscott/pane/commits) ![Language](https://img.shields.io/github/languages/top/zscott/pane?style=flat-square&labelColor=343b41)
<br>

[`/tdd-implement`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/tdd-implement.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Implements Test-Driven Development by analyzing feature requirements, creating tests first (red), implementing minimal passing code (green), and refactoring while maintaining tests.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/tdd-implement`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/tdd-implement.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Implements Test-Driven Development by analyzing feature requirements, creating tests first (red), implementing minimal passing code (green), and refactoring while maintaining tests.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Context Loading & Priming <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/context-prime`](https://github.com/elizaOS/elizaos.github.io/blob/main/.claude/commands/context-prime.md) &nbsp; by &nbsp; [elizaOS](https://github.com/elizaOS)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Primes Claude with comprehensive project understanding by loading repository structure, setting development context, establishing project goals, and defining collaboration parameters.

[![Stars](https://img.shields.io/github/stars/elizaOS/elizaos.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/elizaOS/elizaos.github.io/stargazers) ![License](https://img.shields.io/github/license/elizaOS/elizaos.github.io?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/elizaOS/elizaos.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/elizaOS/elizaos.github.io/commits) ![Language](https://img.shields.io/github/languages/top/elizaOS/elizaos.github.io?style=flat-square&labelColor=343b41)
<br>

[`/context-prime`](https://github.com/elizaOS/elizaos.github.io/blob/main/.claude/commands/context-prime.md) &nbsp; by &nbsp; [elizaOS](https://github.com/elizaOS)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Primes Claude with comprehensive project understanding by loading repository structure, setting development context, establishing project goals, and defining collaboration parameters.

[![Stars](https://img.shields.io/github/stars/elizaOS/elizaos.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/elizaOS/elizaos.github.io/stargazers) ![License](https://img.shields.io/github/license/elizaOS/elizaos.github.io?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/elizaOS/elizaos.github.io?style=flat-square&logo=github&labelColor=343b41)](https://github.com/elizaOS/elizaos.github.io/commits) ![Language](https://img.shields.io/github/languages/top/elizaOS/elizaos.github.io?style=flat-square&labelColor=343b41)
<br>

[`/initref`](https://github.com/okuvshynov/cubestat/blob/main/.claude/commands/initref.md) &nbsp; by &nbsp; [okuvshynov](https://github.com/okuvshynov)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Initializes reference documentation structure with standard doc templates, API reference setup, documentation conventions, and placeholder content generation.

[![Stars](https://img.shields.io/github/stars/okuvshynov/cubestat?style=flat-square&logo=github&labelColor=343b41)](https://github.com/okuvshynov/cubestat/stargazers) ![License](https://img.shields.io/github/license/okuvshynov/cubestat?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/okuvshynov/cubestat?style=flat-square&logo=github&labelColor=343b41)](https://github.com/okuvshynov/cubestat/commits) ![Language](https://img.shields.io/github/languages/top/okuvshynov/cubestat?style=flat-square&labelColor=343b41)
<br>

[`/initref`](https://github.com/okuvshynov/cubestat/blob/main/.claude/commands/initref.md) &nbsp; by &nbsp; [okuvshynov](https://github.com/okuvshynov)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Initializes reference documentation structure with standard doc templates, API reference setup, documentation conventions, and placeholder content generation.

[![Stars](https://img.shields.io/github/stars/okuvshynov/cubestat?style=flat-square&logo=github&labelColor=343b41)](https://github.com/okuvshynov/cubestat/stargazers) ![License](https://img.shields.io/github/license/okuvshynov/cubestat?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/okuvshynov/cubestat?style=flat-square&logo=github&labelColor=343b41)](https://github.com/okuvshynov/cubestat/commits) ![Language](https://img.shields.io/github/languages/top/okuvshynov/cubestat?style=flat-square&labelColor=343b41)
<br>

[`/load-llms-txt`](https://github.com/ethpandaops/xatu-data/blob/master/.claude/commands/load-llms-txt.md) &nbsp; by &nbsp; [ethpandaops](https://github.com/ethpandaops)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Loads LLM configuration files to context, importing specific terminology, model configurations, and establishing baseline terminology for AI discussions.

[![Stars](https://img.shields.io/github/stars/ethpandaops/xatu-data?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ethpandaops/xatu-data/stargazers) ![License](https://img.shields.io/github/license/ethpandaops/xatu-data?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ethpandaops/xatu-data?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ethpandaops/xatu-data/commits) ![Language](https://img.shields.io/github/languages/top/ethpandaops/xatu-data?style=flat-square&labelColor=343b41)
<br>

[`/load-llms-txt`](https://github.com/ethpandaops/xatu-data/blob/master/.claude/commands/load-llms-txt.md) &nbsp; by &nbsp; [ethpandaops](https://github.com/ethpandaops)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Loads LLM configuration files to context, importing specific terminology, model configurations, and establishing baseline terminology for AI discussions.

[![Stars](https://img.shields.io/github/stars/ethpandaops/xatu-data?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ethpandaops/xatu-data/stargazers) ![License](https://img.shields.io/github/license/ethpandaops/xatu-data?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ethpandaops/xatu-data?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ethpandaops/xatu-data/commits) ![Language](https://img.shields.io/github/languages/top/ethpandaops/xatu-data?style=flat-square&labelColor=343b41)
<br>

[`/load_coo_context`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/load_coo_context.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
References specific files for sparse matrix operations, explains transform usage, compares with previous approaches, and sets data formatting context for development.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/load_coo_context`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/load_coo_context.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
References specific files for sparse matrix operations, explains transform usage, compares with previous approaches, and sets data formatting context for development.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/load_dango_pipeline`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/load_dango_pipeline.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Sets context for model training by referencing pipeline files, establishing working context, and preparing for pipeline work with relevant documentation.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/load_dango_pipeline`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/load_dango_pipeline.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Sets context for model training by referencing pipeline files, establishing working context, and preparing for pipeline work with relevant documentation.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/prime`](https://github.com/yzyydev/AI-Engineering-Structure/blob/main/.claude/commands/prime.md) &nbsp; by &nbsp; [yzyydev](https://github.com/yzyydev)    
Sets up initial project context by viewing directory structure and reading key files, creating standardized context with directory visualization and key documentation focus.

[![Stars](https://img.shields.io/github/stars/yzyydev/AI-Engineering-Structure?style=flat-square&logo=github&labelColor=343b41)](https://github.com/yzyydev/AI-Engineering-Structure/stargazers) ![License](https://img.shields.io/github/license/yzyydev/AI-Engineering-Structure?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/yzyydev/AI-Engineering-Structure?style=flat-square&logo=github&labelColor=343b41)](https://github.com/yzyydev/AI-Engineering-Structure/commits) ![Language](https://img.shields.io/github/languages/top/yzyydev/AI-Engineering-Structure?style=flat-square&labelColor=343b41)
<br>

[`/prime`](https://github.com/yzyydev/AI-Engineering-Structure/blob/main/.claude/commands/prime.md) &nbsp; by &nbsp; [yzyydev](https://github.com/yzyydev)    
Sets up initial project context by viewing directory structure and reading key files, creating standardized context with directory visualization and key documentation focus.

[![Stars](https://img.shields.io/github/stars/yzyydev/AI-Engineering-Structure?style=flat-square&logo=github&labelColor=343b41)](https://github.com/yzyydev/AI-Engineering-Structure/stargazers) ![License](https://img.shields.io/github/license/yzyydev/AI-Engineering-Structure?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/yzyydev/AI-Engineering-Structure?style=flat-square&logo=github&labelColor=343b41)](https://github.com/yzyydev/AI-Engineering-Structure/commits) ![Language](https://img.shields.io/github/languages/top/yzyydev/AI-Engineering-Structure?style=flat-square&labelColor=343b41)
<br>

[`/rsi`](https://github.com/ddisisto/si/blob/main/.claude/commands/rsi.md) &nbsp; by &nbsp; [ddisisto](https://github.com/ddisisto)    
Reads all commands and key project files to optimize AI-assisted development by streamlining the process, loading command context, and setting up for better development workflow.

[![Stars](https://img.shields.io/github/stars/ddisisto/si?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ddisisto/si/stargazers) ![License](https://img.shields.io/github/license/ddisisto/si?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ddisisto/si?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ddisisto/si/commits) ![Language](https://img.shields.io/github/languages/top/ddisisto/si?style=flat-square&labelColor=343b41)
<br>

[`/rsi`](https://github.com/ddisisto/si/blob/main/.claude/commands/rsi.md) &nbsp; by &nbsp; [ddisisto](https://github.com/ddisisto)    
Reads all commands and key project files to optimize AI-assisted development by streamlining the process, loading command context, and setting up for better development workflow.

[![Stars](https://img.shields.io/github/stars/ddisisto/si?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ddisisto/si/stargazers) ![License](https://img.shields.io/github/license/ddisisto/si?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ddisisto/si?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ddisisto/si/commits) ![Language](https://img.shields.io/github/languages/top/ddisisto/si?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Documentation & Changelogs <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/add-to-changelog`](https://github.com/berrydev-ai/blockdoc-python/blob/main/.claude/commands/add-to-changelog.md) &nbsp; by &nbsp; [berrydev-ai](https://github.com/berrydev-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Adds new entries to changelog files while maintaining format consistency, properly documenting changes, and following established project standards for version tracking.

[![Stars](https://img.shields.io/github/stars/berrydev-ai/blockdoc-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/berrydev-ai/blockdoc-python/stargazers) ![License](https://img.shields.io/github/license/berrydev-ai/blockdoc-python?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/berrydev-ai/blockdoc-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/berrydev-ai/blockdoc-python/commits) ![Language](https://img.shields.io/github/languages/top/berrydev-ai/blockdoc-python?style=flat-square&labelColor=343b41)
<br>

[`/add-to-changelog`](https://github.com/berrydev-ai/blockdoc-python/blob/main/.claude/commands/add-to-changelog.md) &nbsp; by &nbsp; [berrydev-ai](https://github.com/berrydev-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Adds new entries to changelog files while maintaining format consistency, properly documenting changes, and following established project standards for version tracking.

[![Stars](https://img.shields.io/github/stars/berrydev-ai/blockdoc-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/berrydev-ai/blockdoc-python/stargazers) ![License](https://img.shields.io/github/license/berrydev-ai/blockdoc-python?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/berrydev-ai/blockdoc-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/berrydev-ai/blockdoc-python/commits) ![Language](https://img.shields.io/github/languages/top/berrydev-ai/blockdoc-python?style=flat-square&labelColor=343b41)
<br>

[`/create-docs`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/create-docs.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes code structure and purpose to create comprehensive documentation detailing inputs/outputs, behavior, user interaction flows, and edge cases with error handling.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/create-docs`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/create-docs.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Analyzes code structure and purpose to create comprehensive documentation detailing inputs/outputs, behavior, user interaction flows, and edge cases with error handling.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/docs`](https://github.com/slunsford/coffee-analytics/blob/main/.claude/commands/docs.md) &nbsp; by &nbsp; [slunsford](https://github.com/slunsford)    
Generates comprehensive documentation that follows project structure, documenting APIs and usage patterns with consistent formatting for better user understanding.

[![Stars](https://img.shields.io/github/stars/slunsford/coffee-analytics?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slunsford/coffee-analytics/stargazers) ![License](https://img.shields.io/github/license/slunsford/coffee-analytics?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/slunsford/coffee-analytics?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slunsford/coffee-analytics/commits) ![Language](https://img.shields.io/github/languages/top/slunsford/coffee-analytics?style=flat-square&labelColor=343b41)
<br>

[`/docs`](https://github.com/slunsford/coffee-analytics/blob/main/.claude/commands/docs.md) &nbsp; by &nbsp; [slunsford](https://github.com/slunsford)    
Generates comprehensive documentation that follows project structure, documenting APIs and usage patterns with consistent formatting for better user understanding.

[![Stars](https://img.shields.io/github/stars/slunsford/coffee-analytics?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slunsford/coffee-analytics/stargazers) ![License](https://img.shields.io/github/license/slunsford/coffee-analytics?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/slunsford/coffee-analytics?style=flat-square&logo=github&labelColor=343b41)](https://github.com/slunsford/coffee-analytics/commits) ![Language](https://img.shields.io/github/languages/top/slunsford/coffee-analytics?style=flat-square&labelColor=343b41)
<br>

[`/explain-issue-fix`](https://github.com/hackdays-io/toban-contribution-viewer/blob/main/.claude/commands/explain-issue-fix.md) &nbsp; by &nbsp; [hackdays-io](https://github.com/hackdays-io)    
Documents solution approaches for GitHub issues, explaining technical decisions, detailing challenges overcome, and providing implementation context for better understanding.

[![Stars](https://img.shields.io/github/stars/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/stargazers) ![License](https://img.shields.io/github/license/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/commits) ![Language](https://img.shields.io/github/languages/top/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41)
<br>

[`/explain-issue-fix`](https://github.com/hackdays-io/toban-contribution-viewer/blob/main/.claude/commands/explain-issue-fix.md) &nbsp; by &nbsp; [hackdays-io](https://github.com/hackdays-io)    
Documents solution approaches for GitHub issues, explaining technical decisions, detailing challenges overcome, and providing implementation context for better understanding.

[![Stars](https://img.shields.io/github/stars/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/stargazers) ![License](https://img.shields.io/github/license/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/commits) ![Language](https://img.shields.io/github/languages/top/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41)
<br>

[`/update-docs`](https://github.com/Consiliency/Flutter-Structurizr/blob/main/.claude/commands/update-docs.md) &nbsp; by &nbsp; [Consiliency](https://github.com/Consiliency)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Reviews current documentation status, updates implementation progress, reviews phase documents, and maintains documentation consistency across the project.

[![Stars](https://img.shields.io/github/stars/Consiliency/Flutter-Structurizr?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Consiliency/Flutter-Structurizr/stargazers) ![License](https://img.shields.io/github/license/Consiliency/Flutter-Structurizr?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Consiliency/Flutter-Structurizr?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Consiliency/Flutter-Structurizr/commits) ![Language](https://img.shields.io/github/languages/top/Consiliency/Flutter-Structurizr?style=flat-square&labelColor=343b41)
<br>

[`/update-docs`](https://github.com/Consiliency/Flutter-Structurizr/blob/main/.claude/commands/update-docs.md) &nbsp; by &nbsp; [Consiliency](https://github.com/Consiliency)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Reviews current documentation status, updates implementation progress, reviews phase documents, and maintains documentation consistency across the project.

[![Stars](https://img.shields.io/github/stars/Consiliency/Flutter-Structurizr?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Consiliency/Flutter-Structurizr/stargazers) ![License](https://img.shields.io/github/license/Consiliency/Flutter-Structurizr?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Consiliency/Flutter-Structurizr?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Consiliency/Flutter-Structurizr/commits) ![Language](https://img.shields.io/github/languages/top/Consiliency/Flutter-Structurizr?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>CI / Deployment <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/release`](https://github.com/kelp/webdown/blob/main/.claude/commands/release.md) &nbsp; by &nbsp; [kelp](https://github.com/kelp)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Manages software releases by updating changelogs, reviewing README changes, evaluating version increments, and documenting release changes for better version tracking.

[![Stars](https://img.shields.io/github/stars/kelp/webdown?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kelp/webdown/stargazers) ![License](https://img.shields.io/github/license/kelp/webdown?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kelp/webdown?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kelp/webdown/commits) ![Language](https://img.shields.io/github/languages/top/kelp/webdown?style=flat-square&labelColor=343b41)
<br>

[`/release`](https://github.com/kelp/webdown/blob/main/.claude/commands/release.md) &nbsp; by &nbsp; [kelp](https://github.com/kelp)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Manages software releases by updating changelogs, reviewing README changes, evaluating version increments, and documenting release changes for better version tracking.

[![Stars](https://img.shields.io/github/stars/kelp/webdown?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kelp/webdown/stargazers) ![License](https://img.shields.io/github/license/kelp/webdown?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/kelp/webdown?style=flat-square&logo=github&labelColor=343b41)](https://github.com/kelp/webdown/commits) ![Language](https://img.shields.io/github/languages/top/kelp/webdown?style=flat-square&labelColor=343b41)
<br>

[`/run-ci`](https://github.com/hackdays-io/toban-contribution-viewer/blob/main/.claude/commands/run-ci.md) &nbsp; by &nbsp; [hackdays-io](https://github.com/hackdays-io)    
Activates virtual environments, runs CI-compatible check scripts, iteratively fixes errors, and ensures all tests pass before completion.

[![Stars](https://img.shields.io/github/stars/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/stargazers) ![License](https://img.shields.io/github/license/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/commits) ![Language](https://img.shields.io/github/languages/top/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41)
<br>

[`/run-ci`](https://github.com/hackdays-io/toban-contribution-viewer/blob/main/.claude/commands/run-ci.md) &nbsp; by &nbsp; [hackdays-io](https://github.com/hackdays-io)    
Activates virtual environments, runs CI-compatible check scripts, iteratively fixes errors, and ensures all tests pass before completion.

[![Stars](https://img.shields.io/github/stars/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/stargazers) ![License](https://img.shields.io/github/license/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hackdays-io/toban-contribution-viewer?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hackdays-io/toban-contribution-viewer/commits) ![Language](https://img.shields.io/github/languages/top/hackdays-io/toban-contribution-viewer?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Project & Task Management <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/project_hello_w_name`](https://github.com/disler/just-prompt/blob/main/.claude/commands/project_hello_w_name.md) &nbsp; by &nbsp; [disler](https://github.com/disler)    
Creates customizable greeting components with name input, demonstrating argument passing, component reusability, state management, and user input handling.

[![Stars](https://img.shields.io/github/stars/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/stargazers) ![License](https://img.shields.io/github/license/disler/just-prompt?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/commits) ![Language](https://img.shields.io/github/languages/top/disler/just-prompt?style=flat-square&labelColor=343b41)
<br>

[`/project_hello_w_name`](https://github.com/disler/just-prompt/blob/main/.claude/commands/project_hello_w_name.md) &nbsp; by &nbsp; [disler](https://github.com/disler)    
Creates customizable greeting components with name input, demonstrating argument passing, component reusability, state management, and user input handling.

[![Stars](https://img.shields.io/github/stars/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/stargazers) ![License](https://img.shields.io/github/license/disler/just-prompt?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/disler/just-prompt?style=flat-square&logo=github&labelColor=343b41)](https://github.com/disler/just-prompt/commits) ![Language](https://img.shields.io/github/languages/top/disler/just-prompt?style=flat-square&labelColor=343b41)
<br>

[`/create-command`](https://github.com/scopecraft/command/blob/main/.claude/commands/create-command.md) &nbsp; by &nbsp; [scopecraft](https://github.com/scopecraft)    
Guides Claude through creating new custom commands with proper structure by analyzing requirements, templating commands by category, enforcing command standards, and creating supporting documentation.

[![Stars](https://img.shields.io/github/stars/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/stargazers) ![License](https://img.shields.io/github/license/scopecraft/command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/commits) ![Language](https://img.shields.io/github/languages/top/scopecraft/command?style=flat-square&labelColor=343b41)
<br>

[`/create-command`](https://github.com/scopecraft/command/blob/main/.claude/commands/create-command.md) &nbsp; by &nbsp; [scopecraft](https://github.com/scopecraft)    
Guides Claude through creating new custom commands with proper structure by analyzing requirements, templating commands by category, enforcing command standards, and creating supporting documentation.

[![Stars](https://img.shields.io/github/stars/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/stargazers) ![License](https://img.shields.io/github/license/scopecraft/command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/scopecraft/command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/scopecraft/command/commits) ![Language](https://img.shields.io/github/languages/top/scopecraft/command?style=flat-square&labelColor=343b41)
<br>

[`/create-jtbd`](https://github.com/taddyorg/inkverse/blob/main/.claude/commands/create-jtbd.md) &nbsp; by &nbsp; [taddyorg](https://github.com/taddyorg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Creates Jobs-to-be-Done frameworks that outline user needs with structured format, focusing on specific user problems and organizing by job categories for product development.

[![Stars](https://img.shields.io/github/stars/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/stargazers) ![License](https://img.shields.io/github/license/taddyorg/inkverse?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/commits) ![Language](https://img.shields.io/github/languages/top/taddyorg/inkverse?style=flat-square&labelColor=343b41)
<br>

[`/create-jtbd`](https://github.com/taddyorg/inkverse/blob/main/.claude/commands/create-jtbd.md) &nbsp; by &nbsp; [taddyorg](https://github.com/taddyorg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Creates Jobs-to-be-Done frameworks that outline user needs with structured format, focusing on specific user problems and organizing by job categories for product development.

[![Stars](https://img.shields.io/github/stars/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/stargazers) ![License](https://img.shields.io/github/license/taddyorg/inkverse?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/commits) ![Language](https://img.shields.io/github/languages/top/taddyorg/inkverse?style=flat-square&labelColor=343b41)
<br>

[`/create-prd`](https://github.com/taddyorg/inkverse/blob/main/.claude/commands/create-prd.md) &nbsp; by &nbsp; [taddyorg](https://github.com/taddyorg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Generates comprehensive product requirement documents outlining detailed specifications, requirements, and features following standardized document structure and format.

[![Stars](https://img.shields.io/github/stars/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/stargazers) ![License](https://img.shields.io/github/license/taddyorg/inkverse?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/commits) ![Language](https://img.shields.io/github/languages/top/taddyorg/inkverse?style=flat-square&labelColor=343b41)
<br>

[`/create-prd`](https://github.com/taddyorg/inkverse/blob/main/.claude/commands/create-prd.md) &nbsp; by &nbsp; [taddyorg](https://github.com/taddyorg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Generates comprehensive product requirement documents outlining detailed specifications, requirements, and features following standardized document structure and format.

[![Stars](https://img.shields.io/github/stars/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/stargazers) ![License](https://img.shields.io/github/license/taddyorg/inkverse?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/taddyorg/inkverse?style=flat-square&logo=github&labelColor=343b41)](https://github.com/taddyorg/inkverse/commits) ![Language](https://img.shields.io/github/languages/top/taddyorg/inkverse?style=flat-square&labelColor=343b41)
<br>

[`/create-prp`](https://github.com/Wirasm/claudecode-utils/blob/main/.claude/commands/create-prp.md) &nbsp; by &nbsp; [Wirasm](https://github.com/Wirasm)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates product requirement plans by reading PRP methodology, following template structure, creating comprehensive requirements, and structuring product definitions for development.

[![Stars](https://img.shields.io/github/stars/Wirasm/claudecode-utils?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Wirasm/claudecode-utils/stargazers) ![License](https://img.shields.io/github/license/Wirasm/claudecode-utils?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Wirasm/claudecode-utils?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Wirasm/claudecode-utils/commits) ![Language](https://img.shields.io/github/languages/top/Wirasm/claudecode-utils?style=flat-square&labelColor=343b41)
<br>

[`/create-prp`](https://github.com/Wirasm/claudecode-utils/blob/main/.claude/commands/create-prp.md) &nbsp; by &nbsp; [Wirasm](https://github.com/Wirasm)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates product requirement plans by reading PRP methodology, following template structure, creating comprehensive requirements, and structuring product definitions for development.

[![Stars](https://img.shields.io/github/stars/Wirasm/claudecode-utils?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Wirasm/claudecode-utils/stargazers) ![License](https://img.shields.io/github/license/Wirasm/claudecode-utils?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Wirasm/claudecode-utils?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Wirasm/claudecode-utils/commits) ![Language](https://img.shields.io/github/languages/top/Wirasm/claudecode-utils?style=flat-square&labelColor=343b41)
<br>

[`/do-issue`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/do-issue.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Implements GitHub issues with manual review points, following a structured approach with issue number parameter and offering alternative automated mode for efficiency.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/do-issue`](https://github.com/jerseycheese/Narraitor/blob/feature/issue-227-ai-suggestions/.claude/commands/do-issue.md) &nbsp; by &nbsp; [jerseycheese](https://github.com/jerseycheese)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Implements GitHub issues with manual review points, following a structured approach with issue number parameter and offering alternative automated mode for efficiency.

[![Stars](https://img.shields.io/github/stars/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/stargazers) ![License](https://img.shields.io/github/license/jerseycheese/Narraitor?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/jerseycheese/Narraitor?style=flat-square&logo=github&labelColor=343b41)](https://github.com/jerseycheese/Narraitor/commits) ![Language](https://img.shields.io/github/languages/top/jerseycheese/Narraitor?style=flat-square&labelColor=343b41)
<br>

[`/todo`](https://github.com/chrisleyva/todo-slash-command/blob/main/todo.md) &nbsp; by &nbsp; [chrisleyva](https://github.com/chrisleyva)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A convenient command to quickly manage project todo items without leaving the Claude Code interface, featuring due dates, sorting, task prioritization, and comprehensive todo list management.

[![Stars](https://img.shields.io/github/stars/chrisleyva/todo-slash-command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/chrisleyva/todo-slash-command/stargazers) ![License](https://img.shields.io/github/license/chrisleyva/todo-slash-command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/chrisleyva/todo-slash-command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/chrisleyva/todo-slash-command/commits) ![Language](https://img.shields.io/github/languages/top/chrisleyva/todo-slash-command?style=flat-square&labelColor=343b41)
<br>

[`/todo`](https://github.com/chrisleyva/todo-slash-command/blob/main/todo.md) &nbsp; by &nbsp; [chrisleyva](https://github.com/chrisleyva)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
A convenient command to quickly manage project todo items without leaving the Claude Code interface, featuring due dates, sorting, task prioritization, and comprehensive todo list management.

[![Stars](https://img.shields.io/github/stars/chrisleyva/todo-slash-command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/chrisleyva/todo-slash-command/stargazers) ![License](https://img.shields.io/github/license/chrisleyva/todo-slash-command?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/chrisleyva/todo-slash-command?style=flat-square&logo=github&labelColor=343b41)](https://github.com/chrisleyva/todo-slash-command/commits) ![Language](https://img.shields.io/github/languages/top/chrisleyva/todo-slash-command?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Miscellaneous <a href="#awesome-claude-code">🔝</a></h3></summary>

[`/five`](https://github.com/TuckerTucker/tkr-portfolio/blob/main/.claude/commands/five.md) &nbsp; by &nbsp; [TuckerTucker](https://github.com/TuckerTucker)    
Applies the "five whys" methodology to perform root cause analysis, identify underlying issues, and create solution approaches for complex problems.

[![Stars](https://img.shields.io/github/stars/TuckerTucker/tkr-portfolio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/TuckerTucker/tkr-portfolio/stargazers) ![License](https://img.shields.io/github/license/TuckerTucker/tkr-portfolio?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/TuckerTucker/tkr-portfolio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/TuckerTucker/tkr-portfolio/commits) ![Language](https://img.shields.io/github/languages/top/TuckerTucker/tkr-portfolio?style=flat-square&labelColor=343b41)
<br>

[`/five`](https://github.com/TuckerTucker/tkr-portfolio/blob/main/.claude/commands/five.md) &nbsp; by &nbsp; [TuckerTucker](https://github.com/TuckerTucker)    
Applies the "five whys" methodology to perform root cause analysis, identify underlying issues, and create solution approaches for complex problems.

[![Stars](https://img.shields.io/github/stars/TuckerTucker/tkr-portfolio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/TuckerTucker/tkr-portfolio/stargazers) ![License](https://img.shields.io/github/license/TuckerTucker/tkr-portfolio?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/TuckerTucker/tkr-portfolio?style=flat-square&logo=github&labelColor=343b41)](https://github.com/TuckerTucker/tkr-portfolio/commits) ![Language](https://img.shields.io/github/languages/top/TuckerTucker/tkr-portfolio?style=flat-square&labelColor=343b41)
<br>

[`/fixing_go_in_graph`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/fixing_go_in_graph.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Focuses on Gene Ontology annotation integration in graph databases, handling multiple data sources, addressing graph representation issues, and ensuring correct data incorporation.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/fixing_go_in_graph`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/fixing_go_in_graph.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Focuses on Gene Ontology annotation integration in graph databases, handling multiple data sources, addressing graph representation issues, and ensuring correct data incorporation.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/mermaid`](https://github.com/GaloyMoney/lana-bank/blob/main/.claude/commands/mermaid.md) &nbsp; by &nbsp; [GaloyMoney](https://github.com/GaloyMoney)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Generates Mermaid diagrams from SQL schema files, creating entity relationship diagrams with table properties, validating diagram compilation, and ensuring complete entity coverage.

[![Stars](https://img.shields.io/github/stars/GaloyMoney/lana-bank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GaloyMoney/lana-bank/stargazers) ![License](https://img.shields.io/github/license/GaloyMoney/lana-bank?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GaloyMoney/lana-bank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GaloyMoney/lana-bank/commits) ![Language](https://img.shields.io/github/languages/top/GaloyMoney/lana-bank?style=flat-square&labelColor=343b41)
<br>

[`/mermaid`](https://github.com/GaloyMoney/lana-bank/blob/main/.claude/commands/mermaid.md) &nbsp; by &nbsp; [GaloyMoney](https://github.com/GaloyMoney)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Generates Mermaid diagrams from SQL schema files, creating entity relationship diagrams with table properties, validating diagram compilation, and ensuring complete entity coverage.

[![Stars](https://img.shields.io/github/stars/GaloyMoney/lana-bank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GaloyMoney/lana-bank/stargazers) ![License](https://img.shields.io/github/license/GaloyMoney/lana-bank?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/GaloyMoney/lana-bank?style=flat-square&logo=github&labelColor=343b41)](https://github.com/GaloyMoney/lana-bank/commits) ![Language](https://img.shields.io/github/languages/top/GaloyMoney/lana-bank?style=flat-square&labelColor=343b41)
<br>

[`/review_dcell_model`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/review_dcell_model.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Reviews old Dcell implementation files, comparing with newer Dango model, noting changes over time, and analyzing refactoring approaches for better code organization.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/review_dcell_model`](https://github.com/Mjvolk3/torchcell/blob/main/.claude/commands/review_dcell_model.md) &nbsp; by &nbsp; [Mjvolk3](https://github.com/Mjvolk3)    
Reviews old Dcell implementation files, comparing with newer Dango model, noting changes over time, and analyzing refactoring approaches for better code organization.

[![Stars](https://img.shields.io/github/stars/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/stargazers) ![License](https://img.shields.io/github/license/Mjvolk3/torchcell?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Mjvolk3/torchcell?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Mjvolk3/torchcell/commits) ![Language](https://img.shields.io/github/languages/top/Mjvolk3/torchcell?style=flat-square&labelColor=343b41)
<br>

[`/use-stepper`](https://github.com/zuplo/docs/blob/main/.claude/commands/use-stepper.md) &nbsp; by &nbsp; [zuplo](https://github.com/zuplo)    
Reformats documentation to use React Stepper component, transforming heading formats, applying proper indentation, and maintaining markdown compatibility with admonition formatting.

[![Stars](https://img.shields.io/github/stars/zuplo/docs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zuplo/docs/stargazers) ![License](https://img.shields.io/github/license/zuplo/docs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/zuplo/docs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zuplo/docs/commits) ![Language](https://img.shields.io/github/languages/top/zuplo/docs?style=flat-square&labelColor=343b41)
<br>

[`/use-stepper`](https://github.com/zuplo/docs/blob/main/.claude/commands/use-stepper.md) &nbsp; by &nbsp; [zuplo](https://github.com/zuplo)    
Reformats documentation to use React Stepper component, transforming heading formats, applying proper indentation, and maintaining markdown compatibility with admonition formatting.

[![Stars](https://img.shields.io/github/stars/zuplo/docs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zuplo/docs/stargazers) ![License](https://img.shields.io/github/license/zuplo/docs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/zuplo/docs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/zuplo/docs/commits) ![Language](https://img.shields.io/github/languages/top/zuplo/docs?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## CLAUDE.md Files 📂 [🔝](#awesome-claude-code)

> **`CLAUDE.md` files** are files that contain important guidelines and context-specific information or instructions that help Claude Code to better understand your project and your coding standards

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`AI Coding Project Boilerplate`](https://github.com/shinpr/ai-coding-project-boilerplate) &nbsp; by &nbsp; [shinpr](https://github.com/shinpr)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
TypeScript boilerplate designed for AI-driven development with 10+ specialized sub-agents, preventive control mechanisms, and automated quality gates that enable Claude Code to work autonomously while maintaining production standards.

[![Stars](https://img.shields.io/github/stars/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/stargazers) ![License](https://img.shields.io/github/license/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/commits) ![Language](https://img.shields.io/github/languages/top/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41)
<br>

[`AI Coding Project Boilerplate`](https://github.com/shinpr/ai-coding-project-boilerplate) &nbsp; by &nbsp; [shinpr](https://github.com/shinpr)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
TypeScript boilerplate designed for AI-driven development with 10+ specialized sub-agents, preventive control mechanisms, and automated quality gates that enable Claude Code to work autonomously while maintaining production standards.

[![Stars](https://img.shields.io/github/stars/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/stargazers) ![License](https://img.shields.io/github/license/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/commits) ![Language](https://img.shields.io/github/languages/top/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Sub agents Starter Kit`](https://github.com/shinpr/ai-coding-project-boilerplate) &nbsp; by &nbsp; [shinpr](https://github.com/shinpr)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Comprehensive Claude Code configuration featuring 11 specialized Sub agents with independent contexts and rule-based development system - maintains production-grade TypeScript quality across 770K+ token sessions without context exhaustion.

[![Stars](https://img.shields.io/github/stars/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/stargazers) ![License](https://img.shields.io/github/license/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/commits) ![Language](https://img.shields.io/github/languages/top/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41)
<br>

[`Claude Code Sub agents Starter Kit`](https://github.com/shinpr/ai-coding-project-boilerplate) &nbsp; by &nbsp; [shinpr](https://github.com/shinpr)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Comprehensive Claude Code configuration featuring 11 specialized Sub agents with independent contexts and rule-based development system - maintains production-grade TypeScript quality across 770K+ token sessions without context exhaustion.

[![Stars](https://img.shields.io/github/stars/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/stargazers) ![License](https://img.shields.io/github/license/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/shinpr/ai-coding-project-boilerplate?style=flat-square&logo=github&labelColor=343b41)](https://github.com/shinpr/ai-coding-project-boilerplate/commits) ![Language](https://img.shields.io/github/languages/top/shinpr/ai-coding-project-boilerplate?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Language-Specific <a href="#awesome-claude-code">🔝</a></h3></summary>

[`AI IntelliJ Plugin`](https://github.com/didalgolab/ai-intellij-plugin/blob/main/CLAUDE.md) &nbsp; by &nbsp; [didalgolab](https://github.com/didalgolab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides comprehensive Gradle commands for IntelliJ plugin development with platform-specific coding patterns, detailed package structure guidelines, and clear internationalization standards.

[![Stars](https://img.shields.io/github/stars/didalgolab/ai-intellij-plugin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/didalgolab/ai-intellij-plugin/stargazers) ![License](https://img.shields.io/github/license/didalgolab/ai-intellij-plugin?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/didalgolab/ai-intellij-plugin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/didalgolab/ai-intellij-plugin/commits) ![Language](https://img.shields.io/github/languages/top/didalgolab/ai-intellij-plugin?style=flat-square&labelColor=343b41)
<br>

[`AI IntelliJ Plugin`](https://github.com/didalgolab/ai-intellij-plugin/blob/main/CLAUDE.md) &nbsp; by &nbsp; [didalgolab](https://github.com/didalgolab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides comprehensive Gradle commands for IntelliJ plugin development with platform-specific coding patterns, detailed package structure guidelines, and clear internationalization standards.

[![Stars](https://img.shields.io/github/stars/didalgolab/ai-intellij-plugin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/didalgolab/ai-intellij-plugin/stargazers) ![License](https://img.shields.io/github/license/didalgolab/ai-intellij-plugin?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/didalgolab/ai-intellij-plugin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/didalgolab/ai-intellij-plugin/commits) ![Language](https://img.shields.io/github/languages/top/didalgolab/ai-intellij-plugin?style=flat-square&labelColor=343b41)
<br>

[`AWS MCP Server`](https://github.com/alexei-led/aws-mcp-server/blob/main/CLAUDE.md) &nbsp; by &nbsp; [alexei-led](https://github.com/alexei-led)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Features multiple Python environment setup options with detailed code style guidelines, comprehensive error handling recommendations, and security considerations for AWS CLI interactions.

[![Stars](https://img.shields.io/github/stars/alexei-led/aws-mcp-server?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alexei-led/aws-mcp-server/stargazers) ![License](https://img.shields.io/github/license/alexei-led/aws-mcp-server?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/alexei-led/aws-mcp-server?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alexei-led/aws-mcp-server/commits) ![Language](https://img.shields.io/github/languages/top/alexei-led/aws-mcp-server?style=flat-square&labelColor=343b41)
<br>

[`AWS MCP Server`](https://github.com/alexei-led/aws-mcp-server/blob/main/CLAUDE.md) &nbsp; by &nbsp; [alexei-led](https://github.com/alexei-led)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Features multiple Python environment setup options with detailed code style guidelines, comprehensive error handling recommendations, and security considerations for AWS CLI interactions.

[![Stars](https://img.shields.io/github/stars/alexei-led/aws-mcp-server?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alexei-led/aws-mcp-server/stargazers) ![License](https://img.shields.io/github/license/alexei-led/aws-mcp-server?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/alexei-led/aws-mcp-server?style=flat-square&logo=github&labelColor=343b41)](https://github.com/alexei-led/aws-mcp-server/commits) ![Language](https://img.shields.io/github/languages/top/alexei-led/aws-mcp-server?style=flat-square&labelColor=343b41)
<br>

[`DroidconKotlin`](https://github.com/touchlab/DroidconKotlin/blob/main/CLAUDE.md) &nbsp; by &nbsp; [touchlab](https://github.com/touchlab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Delivers comprehensive Gradle commands for cross-platform Kotlin Multiplatform development with clear module structure and practical guidance for dependency injection.

[![Stars](https://img.shields.io/github/stars/touchlab/DroidconKotlin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/touchlab/DroidconKotlin/stargazers) ![License](https://img.shields.io/github/license/touchlab/DroidconKotlin?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/touchlab/DroidconKotlin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/touchlab/DroidconKotlin/commits) ![Language](https://img.shields.io/github/languages/top/touchlab/DroidconKotlin?style=flat-square&labelColor=343b41)
<br>

[`DroidconKotlin`](https://github.com/touchlab/DroidconKotlin/blob/main/CLAUDE.md) &nbsp; by &nbsp; [touchlab](https://github.com/touchlab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Delivers comprehensive Gradle commands for cross-platform Kotlin Multiplatform development with clear module structure and practical guidance for dependency injection.

[![Stars](https://img.shields.io/github/stars/touchlab/DroidconKotlin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/touchlab/DroidconKotlin/stargazers) ![License](https://img.shields.io/github/license/touchlab/DroidconKotlin?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/touchlab/DroidconKotlin?style=flat-square&logo=github&labelColor=343b41)](https://github.com/touchlab/DroidconKotlin/commits) ![Language](https://img.shields.io/github/languages/top/touchlab/DroidconKotlin?style=flat-square&labelColor=343b41)
<br>

[`EDSL`](https://github.com/hesreallyhim/awesome-claude-code/blob/main/resources/claude.md-files/EDSL/CLAUDE.md) &nbsp; by &nbsp; [expectedparrot](https://github.com/expectedparrot)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers detailed build and test commands with strict code style enforcement, comprehensive testing requirements, and standardized development workflow using Black and mypy.*  
<sub>* Removed from origin</sub>

[`EDSL`](https://github.com/hesreallyhim/awesome-claude-code/blob/main/resources/claude.md-files/EDSL/CLAUDE.md) &nbsp; by &nbsp; [expectedparrot](https://github.com/expectedparrot)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers detailed build and test commands with strict code style enforcement, comprehensive testing requirements, and standardized development workflow using Black and mypy.*  
<sub>* Removed from origin</sub>

[`Giselle`](https://github.com/giselles-ai/giselle/blob/main/CLAUDE.md) &nbsp; by &nbsp; [giselles-ai](https://github.com/giselles-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides detailed build and test commands using pnpm and Vitest with strict code formatting requirements and comprehensive naming conventions for code consistency.

[![Stars](https://img.shields.io/github/stars/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/stargazers) ![License](https://img.shields.io/github/license/giselles-ai/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/commits) ![Language](https://img.shields.io/github/languages/top/giselles-ai/giselle?style=flat-square&labelColor=343b41)
<br>

[`Giselle`](https://github.com/giselles-ai/giselle/blob/main/CLAUDE.md) &nbsp; by &nbsp; [giselles-ai](https://github.com/giselles-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Provides detailed build and test commands using pnpm and Vitest with strict code formatting requirements and comprehensive naming conventions for code consistency.

[![Stars](https://img.shields.io/github/stars/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/stargazers) ![License](https://img.shields.io/github/license/giselles-ai/giselle?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/giselles-ai/giselle?style=flat-square&logo=github&labelColor=343b41)](https://github.com/giselles-ai/giselle/commits) ![Language](https://img.shields.io/github/languages/top/giselles-ai/giselle?style=flat-square&labelColor=343b41)
<br>

[`HASH`](https://github.com/hashintel/hash/blob/main/CLAUDE.md) &nbsp; by &nbsp; [hashintel](https://github.com/hashintel)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Features comprehensive repository structure breakdown with strong emphasis on coding standards, detailed Rust documentation guidelines, and systematic PR review process.

[![Stars](https://img.shields.io/github/stars/hashintel/hash?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hashintel/hash/stargazers) ![License](https://img.shields.io/github/license/hashintel/hash?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hashintel/hash?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hashintel/hash/commits) ![Language](https://img.shields.io/github/languages/top/hashintel/hash?style=flat-square&labelColor=343b41)
<br>

[`HASH`](https://github.com/hashintel/hash/blob/main/CLAUDE.md) &nbsp; by &nbsp; [hashintel](https://github.com/hashintel)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Features comprehensive repository structure breakdown with strong emphasis on coding standards, detailed Rust documentation guidelines, and systematic PR review process.

[![Stars](https://img.shields.io/github/stars/hashintel/hash?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hashintel/hash/stargazers) ![License](https://img.shields.io/github/license/hashintel/hash?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/hashintel/hash?style=flat-square&logo=github&labelColor=343b41)](https://github.com/hashintel/hash/commits) ![Language](https://img.shields.io/github/languages/top/hashintel/hash?style=flat-square&labelColor=343b41)
<br>

[`Inkline`](https://github.com/inkline/inkline/blob/main/CLAUDE.md) &nbsp; by &nbsp; [inkline](https://github.com/inkline)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Structures development workflow using pnpm with emphasis on TypeScript and Vue 3 Composition API, detailed component creation process, and comprehensive testing recommendations.

[![Stars](https://img.shields.io/github/stars/inkline/inkline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/inkline/inkline/stargazers) ![License](https://img.shields.io/github/license/inkline/inkline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/inkline/inkline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/inkline/inkline/commits) ![Language](https://img.shields.io/github/languages/top/inkline/inkline?style=flat-square&labelColor=343b41)
<br>

[`Inkline`](https://github.com/inkline/inkline/blob/main/CLAUDE.md) &nbsp; by &nbsp; [inkline](https://github.com/inkline)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Structures development workflow using pnpm with emphasis on TypeScript and Vue 3 Composition API, detailed component creation process, and comprehensive testing recommendations.

[![Stars](https://img.shields.io/github/stars/inkline/inkline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/inkline/inkline/stargazers) ![License](https://img.shields.io/github/license/inkline/inkline?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/inkline/inkline?style=flat-square&logo=github&labelColor=343b41)](https://github.com/inkline/inkline/commits) ![Language](https://img.shields.io/github/languages/top/inkline/inkline?style=flat-square&labelColor=343b41)
<br>

[`JSBeeb`](https://github.com/mattgodbolt/jsbeeb/blob/main/CLAUDE.md) &nbsp; by &nbsp; [mattgodbolt](https://github.com/mattgodbolt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
Provides development guide for JavaScript BBC Micro emulator with build and testing instructions, architecture documentation, and debugging workflows.

[![Stars](https://img.shields.io/github/stars/mattgodbolt/jsbeeb?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mattgodbolt/jsbeeb/stargazers) ![License](https://img.shields.io/github/license/mattgodbolt/jsbeeb?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/mattgodbolt/jsbeeb?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mattgodbolt/jsbeeb/commits) ![Language](https://img.shields.io/github/languages/top/mattgodbolt/jsbeeb?style=flat-square&labelColor=343b41)
<br>

[`JSBeeb`](https://github.com/mattgodbolt/jsbeeb/blob/main/CLAUDE.md) &nbsp; by &nbsp; [mattgodbolt](https://github.com/mattgodbolt)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
Provides development guide for JavaScript BBC Micro emulator with build and testing instructions, architecture documentation, and debugging workflows.

[![Stars](https://img.shields.io/github/stars/mattgodbolt/jsbeeb?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mattgodbolt/jsbeeb/stargazers) ![License](https://img.shields.io/github/license/mattgodbolt/jsbeeb?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/mattgodbolt/jsbeeb?style=flat-square&logo=github&labelColor=343b41)](https://github.com/mattgodbolt/jsbeeb/commits) ![Language](https://img.shields.io/github/languages/top/mattgodbolt/jsbeeb?style=flat-square&labelColor=343b41)
<br>

[`Lamoom Python`](https://github.com/LamoomAI/lamoom-python/blob/main/CLAUDE.md) &nbsp; by &nbsp; [LamoomAI](https://github.com/LamoomAI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Serves as reference for production prompt engineering library with load balancing of AI Models, API documentation, and usage patterns with examples.

[![Stars](https://img.shields.io/github/stars/LamoomAI/lamoom-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/LamoomAI/lamoom-python/stargazers) ![License](https://img.shields.io/github/license/LamoomAI/lamoom-python?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/LamoomAI/lamoom-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/LamoomAI/lamoom-python/commits) ![Language](https://img.shields.io/github/languages/top/LamoomAI/lamoom-python?style=flat-square&labelColor=343b41)
<br>

[`Lamoom Python`](https://github.com/LamoomAI/lamoom-python/blob/main/CLAUDE.md) &nbsp; by &nbsp; [LamoomAI](https://github.com/LamoomAI)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;Apache-2.0  
Serves as reference for production prompt engineering library with load balancing of AI Models, API documentation, and usage patterns with examples.

[![Stars](https://img.shields.io/github/stars/LamoomAI/lamoom-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/LamoomAI/lamoom-python/stargazers) ![License](https://img.shields.io/github/license/LamoomAI/lamoom-python?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/LamoomAI/lamoom-python?style=flat-square&logo=github&labelColor=343b41)](https://github.com/LamoomAI/lamoom-python/commits) ![Language](https://img.shields.io/github/languages/top/LamoomAI/lamoom-python?style=flat-square&labelColor=343b41)
<br>

[`LangGraphJS`](https://github.com/langchain-ai/langgraphjs/blob/main/CLAUDE.md) &nbsp; by &nbsp; [langchain-ai](https://github.com/langchain-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers comprehensive build and test commands with detailed TypeScript style guidelines, layered library architecture, and monorepo structure using yarn workspaces.

[![Stars](https://img.shields.io/github/stars/langchain-ai/langgraphjs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/langchain-ai/langgraphjs/stargazers) ![License](https://img.shields.io/github/license/langchain-ai/langgraphjs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/langchain-ai/langgraphjs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/langchain-ai/langgraphjs/commits) ![Language](https://img.shields.io/github/languages/top/langchain-ai/langgraphjs?style=flat-square&labelColor=343b41)
<br>

[`LangGraphJS`](https://github.com/langchain-ai/langgraphjs/blob/main/CLAUDE.md) &nbsp; by &nbsp; [langchain-ai](https://github.com/langchain-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers comprehensive build and test commands with detailed TypeScript style guidelines, layered library architecture, and monorepo structure using yarn workspaces.

[![Stars](https://img.shields.io/github/stars/langchain-ai/langgraphjs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/langchain-ai/langgraphjs/stargazers) ![License](https://img.shields.io/github/license/langchain-ai/langgraphjs?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/langchain-ai/langgraphjs?style=flat-square&logo=github&labelColor=343b41)](https://github.com/langchain-ai/langgraphjs/commits) ![Language](https://img.shields.io/github/languages/top/langchain-ai/langgraphjs?style=flat-square&labelColor=343b41)
<br>

[`Metabase`](https://github.com/metabase/metabase/blob/master/CLAUDE.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Details workflow for REPL-driven development in Clojure/ClojureScript with emphasis on incremental development, testing, and step-by-step approach for feature implementation.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`Metabase`](https://github.com/metabase/metabase/blob/master/CLAUDE.md) &nbsp; by &nbsp; [metabase](https://github.com/metabase)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;NOASSERTION  
Details workflow for REPL-driven development in Clojure/ClojureScript with emphasis on incremental development, testing, and step-by-step approach for feature implementation.

[![Stars](https://img.shields.io/github/stars/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/stargazers) ![License](https://img.shields.io/github/license/metabase/metabase?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/metabase/metabase?style=flat-square&logo=github&labelColor=343b41)](https://github.com/metabase/metabase/commits) ![Language](https://img.shields.io/github/languages/top/metabase/metabase?style=flat-square&labelColor=343b41)
<br>

[`SG Cars Trends Backend`](https://github.com/sgcarstrends/backend/blob/main/CLAUDE.md) &nbsp; by &nbsp; [sgcarstrends](https://github.com/sgcarstrends)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides comprehensive structure for TypeScript monorepo projects with detailed commands for development, testing, deployment, and AWS/Cloudflare integration.

[![Stars](https://img.shields.io/github/stars/sgcarstrends/backend?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sgcarstrends/backend/stargazers) ![License](https://img.shields.io/github/license/sgcarstrends/backend?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sgcarstrends/backend?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sgcarstrends/backend/commits) ![Language](https://img.shields.io/github/languages/top/sgcarstrends/backend?style=flat-square&labelColor=343b41)
<br>

[`SG Cars Trends Backend`](https://github.com/sgcarstrends/backend/blob/main/CLAUDE.md) &nbsp; by &nbsp; [sgcarstrends](https://github.com/sgcarstrends)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides comprehensive structure for TypeScript monorepo projects with detailed commands for development, testing, deployment, and AWS/Cloudflare integration.

[![Stars](https://img.shields.io/github/stars/sgcarstrends/backend?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sgcarstrends/backend/stargazers) ![License](https://img.shields.io/github/license/sgcarstrends/backend?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/sgcarstrends/backend?style=flat-square&logo=github&labelColor=343b41)](https://github.com/sgcarstrends/backend/commits) ![Language](https://img.shields.io/github/languages/top/sgcarstrends/backend?style=flat-square&labelColor=343b41)
<br>

[`SPy`](https://github.com/spylang/spy/blob/main/CLAUDE.md) &nbsp; by &nbsp; [spylang](https://github.com/spylang)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enforces strict coding conventions with comprehensive testing guidelines, multiple code compilation options, and backend-specific test decorators for targeted filtering.

[![Stars](https://img.shields.io/github/stars/spylang/spy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/spylang/spy/stargazers) ![License](https://img.shields.io/github/license/spylang/spy?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/spylang/spy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/spylang/spy/commits) ![Language](https://img.shields.io/github/languages/top/spylang/spy?style=flat-square&labelColor=343b41)
<br>

[`SPy`](https://github.com/spylang/spy/blob/main/CLAUDE.md) &nbsp; by &nbsp; [spylang](https://github.com/spylang)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enforces strict coding conventions with comprehensive testing guidelines, multiple code compilation options, and backend-specific test decorators for targeted filtering.

[![Stars](https://img.shields.io/github/stars/spylang/spy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/spylang/spy/stargazers) ![License](https://img.shields.io/github/license/spylang/spy?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/spylang/spy?style=flat-square&logo=github&labelColor=343b41)](https://github.com/spylang/spy/commits) ![Language](https://img.shields.io/github/languages/top/spylang/spy?style=flat-square&labelColor=343b41)
<br>

[`TPL`](https://github.com/KarpelesLab/tpl/blob/master/CLAUDE.md) &nbsp; by &nbsp; [KarpelesLab](https://github.com/KarpelesLab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Details Go project conventions with comprehensive error handling recommendations, table-driven testing approach guidelines, and modernization suggestions for latest Go features.

[![Stars](https://img.shields.io/github/stars/KarpelesLab/tpl?style=flat-square&logo=github&labelColor=343b41)](https://github.com/KarpelesLab/tpl/stargazers) ![License](https://img.shields.io/github/license/KarpelesLab/tpl?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/KarpelesLab/tpl?style=flat-square&logo=github&labelColor=343b41)](https://github.com/KarpelesLab/tpl/commits) ![Language](https://img.shields.io/github/languages/top/KarpelesLab/tpl?style=flat-square&labelColor=343b41)
<br>

[`TPL`](https://github.com/KarpelesLab/tpl/blob/master/CLAUDE.md) &nbsp; by &nbsp; [KarpelesLab](https://github.com/KarpelesLab)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Details Go project conventions with comprehensive error handling recommendations, table-driven testing approach guidelines, and modernization suggestions for latest Go features.

[![Stars](https://img.shields.io/github/stars/KarpelesLab/tpl?style=flat-square&logo=github&labelColor=343b41)](https://github.com/KarpelesLab/tpl/stargazers) ![License](https://img.shields.io/github/license/KarpelesLab/tpl?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/KarpelesLab/tpl?style=flat-square&logo=github&labelColor=343b41)](https://github.com/KarpelesLab/tpl/commits) ![Language](https://img.shields.io/github/languages/top/KarpelesLab/tpl?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Domain-Specific <a href="#awesome-claude-code">🔝</a></h3></summary>

[`SteadyStart`](https://github.com/steadycursor/steadystart/blob/main/CLAUDE.md) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Clear and direct instructives about style, permissions, Claude's "role", communications, and documentation of Claude Code sessions for other team members to stay abreast.

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`SteadyStart`](https://github.com/steadycursor/steadystart/blob/main/CLAUDE.md) &nbsp; by &nbsp; [steadycursor](https://github.com/steadycursor)    
Clear and direct instructives about style, permissions, Claude's "role", communications, and documentation of Claude Code sessions for other team members to stay abreast.

[![Stars](https://img.shields.io/github/stars/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/stargazers) ![License](https://img.shields.io/github/license/steadycursor/steadystart?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/steadycursor/steadystart?style=flat-square&logo=github&labelColor=343b41)](https://github.com/steadycursor/steadystart/commits) ![Language](https://img.shields.io/github/languages/top/steadycursor/steadystart?style=flat-square&labelColor=343b41)
<br>

[`AVS Vibe Developer Guide`](https://github.com/Layr-Labs/avs-vibe-developer-guide/blob/master/CLAUDE.md) &nbsp; by &nbsp; [Layr-Labs](https://github.com/Layr-Labs)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Structures AI-assisted EigenLayer AVS development workflow with consistent naming conventions for prompt files and established terminology standards for blockchain concepts.

[![Stars](https://img.shields.io/github/stars/Layr-Labs/avs-vibe-developer-guide?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Layr-Labs/avs-vibe-developer-guide/stargazers) ![License](https://img.shields.io/github/license/Layr-Labs/avs-vibe-developer-guide?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Layr-Labs/avs-vibe-developer-guide?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Layr-Labs/avs-vibe-developer-guide/commits) ![Language](https://img.shields.io/github/languages/top/Layr-Labs/avs-vibe-developer-guide?style=flat-square&labelColor=343b41)
<br>

[`AVS Vibe Developer Guide`](https://github.com/Layr-Labs/avs-vibe-developer-guide/blob/master/CLAUDE.md) &nbsp; by &nbsp; [Layr-Labs](https://github.com/Layr-Labs)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Structures AI-assisted EigenLayer AVS development workflow with consistent naming conventions for prompt files and established terminology standards for blockchain concepts.

[![Stars](https://img.shields.io/github/stars/Layr-Labs/avs-vibe-developer-guide?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Layr-Labs/avs-vibe-developer-guide/stargazers) ![License](https://img.shields.io/github/license/Layr-Labs/avs-vibe-developer-guide?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Layr-Labs/avs-vibe-developer-guide?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Layr-Labs/avs-vibe-developer-guide/commits) ![Language](https://img.shields.io/github/languages/top/Layr-Labs/avs-vibe-developer-guide?style=flat-square&labelColor=343b41)
<br>

[`Comm`](https://github.com/CommE2E/comm/blob/master/CLAUDE.md) &nbsp; by &nbsp; [CommE2E](https://github.com/CommE2E)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;BSD-3-Clause  
Serves as a development reference for E2E-encrypted messaging applications with code organization architecture, security implementation details, and testing procedures.

[![Stars](https://img.shields.io/github/stars/CommE2E/comm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/CommE2E/comm/stargazers) ![License](https://img.shields.io/github/license/CommE2E/comm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/CommE2E/comm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/CommE2E/comm/commits) ![Language](https://img.shields.io/github/languages/top/CommE2E/comm?style=flat-square&labelColor=343b41)
<br>

[`Comm`](https://github.com/CommE2E/comm/blob/master/CLAUDE.md) &nbsp; by &nbsp; [CommE2E](https://github.com/CommE2E)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;BSD-3-Clause  
Serves as a development reference for E2E-encrypted messaging applications with code organization architecture, security implementation details, and testing procedures.

[![Stars](https://img.shields.io/github/stars/CommE2E/comm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/CommE2E/comm/stargazers) ![License](https://img.shields.io/github/license/CommE2E/comm?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/CommE2E/comm?style=flat-square&logo=github&labelColor=343b41)](https://github.com/CommE2E/comm/commits) ![Language](https://img.shields.io/github/languages/top/CommE2E/comm?style=flat-square&labelColor=343b41)
<br>

[`Course Builder`](https://github.com/badass-courses/course-builder/blob/main/CLAUDE.md) &nbsp; by &nbsp; [badass-courses](https://github.com/badass-courses)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enables real-time multiplayer capabilities for collaborative course creation with diverse tech stack integration and monorepo architecture using Turborepo.

[![Stars](https://img.shields.io/github/stars/badass-courses/course-builder?style=flat-square&logo=github&labelColor=343b41)](https://github.com/badass-courses/course-builder/stargazers) ![License](https://img.shields.io/github/license/badass-courses/course-builder?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/badass-courses/course-builder?style=flat-square&logo=github&labelColor=343b41)](https://github.com/badass-courses/course-builder/commits) ![Language](https://img.shields.io/github/languages/top/badass-courses/course-builder?style=flat-square&labelColor=343b41)
<br>

[`Course Builder`](https://github.com/badass-courses/course-builder/blob/main/CLAUDE.md) &nbsp; by &nbsp; [badass-courses](https://github.com/badass-courses)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Enables real-time multiplayer capabilities for collaborative course creation with diverse tech stack integration and monorepo architecture using Turborepo.

[![Stars](https://img.shields.io/github/stars/badass-courses/course-builder?style=flat-square&logo=github&labelColor=343b41)](https://github.com/badass-courses/course-builder/stargazers) ![License](https://img.shields.io/github/license/badass-courses/course-builder?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/badass-courses/course-builder?style=flat-square&logo=github&labelColor=343b41)](https://github.com/badass-courses/course-builder/commits) ![Language](https://img.shields.io/github/languages/top/badass-courses/course-builder?style=flat-square&labelColor=343b41)
<br>

[`Cursor Tools`](https://github.com/eastlondoner/cursor-tools/blob/main/CLAUDE.md) &nbsp; by &nbsp; [eastlondoner](https://github.com/eastlondoner)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates a versatile AI command interface supporting multiple providers and models with flexible command options and browser automation through "Stagehand" feature.

[![Stars](https://img.shields.io/github/stars/eastlondoner/cursor-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eastlondoner/cursor-tools/stargazers) ![License](https://img.shields.io/github/license/eastlondoner/cursor-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eastlondoner/cursor-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eastlondoner/cursor-tools/commits) ![Language](https://img.shields.io/github/languages/top/eastlondoner/cursor-tools?style=flat-square&labelColor=343b41)
<br>

[`Cursor Tools`](https://github.com/eastlondoner/cursor-tools/blob/main/CLAUDE.md) &nbsp; by &nbsp; [eastlondoner](https://github.com/eastlondoner)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Creates a versatile AI command interface supporting multiple providers and models with flexible command options and browser automation through "Stagehand" feature.

[![Stars](https://img.shields.io/github/stars/eastlondoner/cursor-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eastlondoner/cursor-tools/stargazers) ![License](https://img.shields.io/github/license/eastlondoner/cursor-tools?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/eastlondoner/cursor-tools?style=flat-square&logo=github&labelColor=343b41)](https://github.com/eastlondoner/cursor-tools/commits) ![Language](https://img.shields.io/github/languages/top/eastlondoner/cursor-tools?style=flat-square&labelColor=343b41)
<br>

[`Guitar`](https://github.com/soramimi/Guitar/blob/master/CLAUDE.md) &nbsp; by &nbsp; [soramimi](https://github.com/soramimi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-2.0  
Serves as development guide for Guitar Git GUI Client with build commands for various platforms, code style guidelines for contributing, and project structure explanation.

[![Stars](https://img.shields.io/github/stars/soramimi/Guitar?style=flat-square&logo=github&labelColor=343b41)](https://github.com/soramimi/Guitar/stargazers) ![License](https://img.shields.io/github/license/soramimi/Guitar?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/soramimi/Guitar?style=flat-square&logo=github&labelColor=343b41)](https://github.com/soramimi/Guitar/commits) ![Language](https://img.shields.io/github/languages/top/soramimi/Guitar?style=flat-square&labelColor=343b41)
<br>

[`Guitar`](https://github.com/soramimi/Guitar/blob/master/CLAUDE.md) &nbsp; by &nbsp; [soramimi](https://github.com/soramimi)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-2.0  
Serves as development guide for Guitar Git GUI Client with build commands for various platforms, code style guidelines for contributing, and project structure explanation.

[![Stars](https://img.shields.io/github/stars/soramimi/Guitar?style=flat-square&logo=github&labelColor=343b41)](https://github.com/soramimi/Guitar/stargazers) ![License](https://img.shields.io/github/license/soramimi/Guitar?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/soramimi/Guitar?style=flat-square&logo=github&labelColor=343b41)](https://github.com/soramimi/Guitar/commits) ![Language](https://img.shields.io/github/languages/top/soramimi/Guitar?style=flat-square&labelColor=343b41)
<br>

[`Network Chronicles`](https://github.com/Fimeg/NetworkChronicles/blob/legacy-v1/CLAUDE.md) &nbsp; by &nbsp; [Fimeg](https://github.com/Fimeg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Presents detailed implementation plan for AI-driven game characters with technical specifications for LLM integration, character guidelines, and service discovery mechanics.

[![Stars](https://img.shields.io/github/stars/Fimeg/NetworkChronicles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Fimeg/NetworkChronicles/stargazers) ![License](https://img.shields.io/github/license/Fimeg/NetworkChronicles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Fimeg/NetworkChronicles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Fimeg/NetworkChronicles/commits) ![Language](https://img.shields.io/github/languages/top/Fimeg/NetworkChronicles?style=flat-square&labelColor=343b41)
<br>

[`Network Chronicles`](https://github.com/Fimeg/NetworkChronicles/blob/legacy-v1/CLAUDE.md) &nbsp; by &nbsp; [Fimeg](https://github.com/Fimeg)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Presents detailed implementation plan for AI-driven game characters with technical specifications for LLM integration, character guidelines, and service discovery mechanics.

[![Stars](https://img.shields.io/github/stars/Fimeg/NetworkChronicles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Fimeg/NetworkChronicles/stargazers) ![License](https://img.shields.io/github/license/Fimeg/NetworkChronicles?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Fimeg/NetworkChronicles?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Fimeg/NetworkChronicles/commits) ![Language](https://img.shields.io/github/languages/top/Fimeg/NetworkChronicles?style=flat-square&labelColor=343b41)
<br>

[`Note Companion`](https://github.com/different-ai/note-companion/blob/master/CLAUDE.md) &nbsp; by &nbsp; [different-ai](https://github.com/different-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides detailed styling isolation techniques for Obsidian plugins using Tailwind with custom prefix to prevent style conflicts and practical troubleshooting steps.

[![Stars](https://img.shields.io/github/stars/different-ai/note-companion?style=flat-square&logo=github&labelColor=343b41)](https://github.com/different-ai/note-companion/stargazers) ![License](https://img.shields.io/github/license/different-ai/note-companion?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/different-ai/note-companion?style=flat-square&logo=github&labelColor=343b41)](https://github.com/different-ai/note-companion/commits) ![Language](https://img.shields.io/github/languages/top/different-ai/note-companion?style=flat-square&labelColor=343b41)
<br>

[`Note Companion`](https://github.com/different-ai/note-companion/blob/master/CLAUDE.md) &nbsp; by &nbsp; [different-ai](https://github.com/different-ai)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides detailed styling isolation techniques for Obsidian plugins using Tailwind with custom prefix to prevent style conflicts and practical troubleshooting steps.

[![Stars](https://img.shields.io/github/stars/different-ai/note-companion?style=flat-square&logo=github&labelColor=343b41)](https://github.com/different-ai/note-companion/stargazers) ![License](https://img.shields.io/github/license/different-ai/note-companion?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/different-ai/note-companion?style=flat-square&logo=github&labelColor=343b41)](https://github.com/different-ai/note-companion/commits) ![Language](https://img.shields.io/github/languages/top/different-ai/note-companion?style=flat-square&labelColor=343b41)
<br>

[`Pareto Mac`](https://github.com/ParetoSecurity/pareto-mac/blob/main/CLAUDE.md) &nbsp; by &nbsp; [ParetoSecurity](https://github.com/ParetoSecurity)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
Serves as development guide for Mac security audit tool with build instructions, contribution guidelines, testing procedures, and workflow documentation.

[![Stars](https://img.shields.io/github/stars/ParetoSecurity/pareto-mac?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ParetoSecurity/pareto-mac/stargazers) ![License](https://img.shields.io/github/license/ParetoSecurity/pareto-mac?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ParetoSecurity/pareto-mac?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ParetoSecurity/pareto-mac/commits) ![Language](https://img.shields.io/github/languages/top/ParetoSecurity/pareto-mac?style=flat-square&labelColor=343b41)
<br>

[`Pareto Mac`](https://github.com/ParetoSecurity/pareto-mac/blob/main/CLAUDE.md) &nbsp; by &nbsp; [ParetoSecurity](https://github.com/ParetoSecurity)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;GPL-3.0  
Serves as development guide for Mac security audit tool with build instructions, contribution guidelines, testing procedures, and workflow documentation.

[![Stars](https://img.shields.io/github/stars/ParetoSecurity/pareto-mac?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ParetoSecurity/pareto-mac/stargazers) ![License](https://img.shields.io/github/license/ParetoSecurity/pareto-mac?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/ParetoSecurity/pareto-mac?style=flat-square&logo=github&labelColor=343b41)](https://github.com/ParetoSecurity/pareto-mac/commits) ![Language](https://img.shields.io/github/languages/top/ParetoSecurity/pareto-mac?style=flat-square&labelColor=343b41)
<br>

</details>

<details open>
<summary><h3>Project Scaffolding & MCP <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Basic Memory`](https://github.com/basicmachines-co/basic-memory/blob/main/CLAUDE.md) &nbsp; by &nbsp; [basicmachines-co](https://github.com/basicmachines-co)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Presents an innovative AI-human collaboration framework with Model Context Protocol for bidirectional LLM-markdown communication and flexible knowledge structure for complex projects.

[![Stars](https://img.shields.io/github/stars/basicmachines-co/basic-memory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/basicmachines-co/basic-memory/stargazers) ![License](https://img.shields.io/github/license/basicmachines-co/basic-memory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/basicmachines-co/basic-memory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/basicmachines-co/basic-memory/commits) ![Language](https://img.shields.io/github/languages/top/basicmachines-co/basic-memory?style=flat-square&labelColor=343b41)
<br>

[`Basic Memory`](https://github.com/basicmachines-co/basic-memory/blob/main/CLAUDE.md) &nbsp; by &nbsp; [basicmachines-co](https://github.com/basicmachines-co)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;AGPL-3.0  
Presents an innovative AI-human collaboration framework with Model Context Protocol for bidirectional LLM-markdown communication and flexible knowledge structure for complex projects.

[![Stars](https://img.shields.io/github/stars/basicmachines-co/basic-memory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/basicmachines-co/basic-memory/stargazers) ![License](https://img.shields.io/github/license/basicmachines-co/basic-memory?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/basicmachines-co/basic-memory?style=flat-square&logo=github&labelColor=343b41)](https://github.com/basicmachines-co/basic-memory/commits) ![Language](https://img.shields.io/github/languages/top/basicmachines-co/basic-memory?style=flat-square&labelColor=343b41)
<br>

[`claude-code-mcp-enhanced`](https://github.com/grahama1970/claude-code-mcp-enhanced/blob/main/CLAUDE.md) &nbsp; by &nbsp; [grahama1970](https://github.com/grahama1970)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides detailed and emphatic instructions for Claude to follow as a coding agent, with testing guidance, code examples, and compliance checks.

[![Stars](https://img.shields.io/github/stars/grahama1970/claude-code-mcp-enhanced?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-code-mcp-enhanced/stargazers) ![License](https://img.shields.io/github/license/grahama1970/claude-code-mcp-enhanced?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/grahama1970/claude-code-mcp-enhanced?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-code-mcp-enhanced/commits) ![Language](https://img.shields.io/github/languages/top/grahama1970/claude-code-mcp-enhanced?style=flat-square&labelColor=343b41)
<br>

[`claude-code-mcp-enhanced`](https://github.com/grahama1970/claude-code-mcp-enhanced/blob/main/CLAUDE.md) &nbsp; by &nbsp; [grahama1970](https://github.com/grahama1970)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Provides detailed and emphatic instructions for Claude to follow as a coding agent, with testing guidance, code examples, and compliance checks.

[![Stars](https://img.shields.io/github/stars/grahama1970/claude-code-mcp-enhanced?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-code-mcp-enhanced/stargazers) ![License](https://img.shields.io/github/license/grahama1970/claude-code-mcp-enhanced?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/grahama1970/claude-code-mcp-enhanced?style=flat-square&logo=github&labelColor=343b41)](https://github.com/grahama1970/claude-code-mcp-enhanced/commits) ![Language](https://img.shields.io/github/languages/top/grahama1970/claude-code-mcp-enhanced?style=flat-square&labelColor=343b41)
<br>

[`Perplexity MCP`](https://github.com/Family-IT-Guy/perplexity-mcp/blob/main/CLAUDE.md) &nbsp; by &nbsp; [Family-IT-Guy](https://github.com/Family-IT-Guy)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;ISC  
Offers clear step-by-step installation instructions with multiple configuration options, detailed troubleshooting guidance, and concise architecture overview of the MCP protocol.

[![Stars](https://img.shields.io/github/stars/Family-IT-Guy/perplexity-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Family-IT-Guy/perplexity-mcp/stargazers) ![License](https://img.shields.io/github/license/Family-IT-Guy/perplexity-mcp?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Family-IT-Guy/perplexity-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Family-IT-Guy/perplexity-mcp/commits) ![Language](https://img.shields.io/github/languages/top/Family-IT-Guy/perplexity-mcp?style=flat-square&labelColor=343b41)
<br>

[`Perplexity MCP`](https://github.com/Family-IT-Guy/perplexity-mcp/blob/main/CLAUDE.md) &nbsp; by &nbsp; [Family-IT-Guy](https://github.com/Family-IT-Guy)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;ISC  
Offers clear step-by-step installation instructions with multiple configuration options, detailed troubleshooting guidance, and concise architecture overview of the MCP protocol.

[![Stars](https://img.shields.io/github/stars/Family-IT-Guy/perplexity-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Family-IT-Guy/perplexity-mcp/stargazers) ![License](https://img.shields.io/github/license/Family-IT-Guy/perplexity-mcp?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/Family-IT-Guy/perplexity-mcp?style=flat-square&logo=github&labelColor=343b41)](https://github.com/Family-IT-Guy/perplexity-mcp/commits) ![Language](https://img.shields.io/github/languages/top/Family-IT-Guy/perplexity-mcp?style=flat-square&labelColor=343b41)
<br>

</details>

<br>

## Alternative Clients 📱 [🔝](#awesome-claude-code)

> **Alternative Clients** are alternative UIs and front-ends for interacting with Claude Code, either on mobile or on the desktop.

<br>

## Official Documentation 🏛️ [🔝](#awesome-claude-code)

> Links to some of Anthropic's terrific documentation and resources regarding Claude Code

<!--lint disable double-link-->

<details open>
<summary><h3>General <a href="#awesome-claude-code">🔝</a></h3></summary>

[`Anthropic Documentation`](https://docs.claude.com/en/home) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;&copy;  
The official documentation for Claude Code, including installation instructions, usage guidelines, API references, tutorials, examples, loads of information that I won't list individually. Like Claude Code, the documentation is frequently updated.

[`Anthropic Documentation`](https://docs.claude.com/en/home) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;&copy;  
The official documentation for Claude Code, including installation instructions, usage guidelines, API references, tutorials, examples, loads of information that I won't list individually. Like Claude Code, the documentation is frequently updated.

[`Anthropic Quickstarts`](https://github.com/anthropics/claude-quickstarts) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers comprehensive development guides for three distinct AI-powered demo projects with standardized workflows, strict code style guidelines, and containerization instructions.

[![Stars](https://img.shields.io/github/stars/anthropics/claude-quickstarts?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-quickstarts/stargazers) ![License](https://img.shields.io/github/license/anthropics/claude-quickstarts?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/anthropics/claude-quickstarts?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-quickstarts/commits) ![Language](https://img.shields.io/github/languages/top/anthropics/claude-quickstarts?style=flat-square&labelColor=343b41)
<br>

[`Anthropic Quickstarts`](https://github.com/anthropics/claude-quickstarts) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Offers comprehensive development guides for three distinct AI-powered demo projects with standardized workflows, strict code style guidelines, and containerization instructions.

[![Stars](https://img.shields.io/github/stars/anthropics/claude-quickstarts?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-quickstarts/stargazers) ![License](https://img.shields.io/github/license/anthropics/claude-quickstarts?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/anthropics/claude-quickstarts?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-quickstarts/commits) ![Language](https://img.shields.io/github/languages/top/anthropics/claude-quickstarts?style=flat-square&labelColor=343b41)
<br>

[`Claude Code GitHub Actions`](https://github.com/anthropics/claude-code-action/tree/main/examples) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Official GitHub Actions integration for Claude Code with examples and documentation for automating AI-powered workflows in CI/CD pipelines.

[![Stars](https://img.shields.io/github/stars/anthropics/claude-code-action?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-code-action/stargazers) ![License](https://img.shields.io/github/license/anthropics/claude-code-action?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/anthropics/claude-code-action?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-code-action/commits) ![Language](https://img.shields.io/github/languages/top/anthropics/claude-code-action?style=flat-square&labelColor=343b41)
<br>

[`Claude Code GitHub Actions`](https://github.com/anthropics/claude-code-action/tree/main/examples) &nbsp; by &nbsp; [Anthropic](https://github.com/anthropics)  &nbsp;&nbsp;⚖️&nbsp;&nbsp;MIT  
Official GitHub Actions integration for Claude Code with examples and documentation for automating AI-powered workflows in CI/CD pipelines.

[![Stars](https://img.shields.io/github/stars/anthropics/claude-code-action?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-code-action/stargazers) ![License](https://img.shields.io/github/license/anthropics/claude-code-action?style=flat-square&labelColor=343b41) [![Last Commit](https://img.shields.io/github/last-commit/anthropics/claude-code-action?style=flat-square&logo=github&labelColor=343b41)](https://github.com/anthropics/claude-code-action/commits) ![Language](https://img.shields.io/github/languages/top/anthropics/claude-code-action?style=flat-square&labelColor=343b41)
<br>

</details>


## Contributing 🌻 [🔝](#awesome-claude-code)

### 🚀 **[Submit a new resource here!](https://github.com/thedotmack/awesome-claude-code/issues/new?template=submit-resource.yml)**

It's easy! Just click the link above and fill out the form. No Git knowledge required - our automated system handles everything for you.

**How we evaluate submissions**

- **Automated Validation**: All submissions go through automated validation checks for security, licensing, and basic quality standards.
- **Auto-Approval**: If validation passes, your submission is automatically approved and added to the list within an hour. No human gatekeeping!
- **Community-Driven**: The community decides value through stars, forks, and usage. We don't impose subjective opinions on what's "valuable enough."

**What we welcome**

- All Claude Code tools, workflows, configurations, and resources
- All categories: orchestrators, IDE integrations, handbooks, cheat sheets, skills, hooks, commands, and more
- Projects at any stage: new, mature, experimental, or production-ready
- All approaches: simple utilities and complex frameworks alike

See [CONTRIBUTING.md](/CONTRIBUTING.md) for the complete submission guide and review process.

For suggestions about the repository itself, please [open a general issue](https://github.com/thedotmack/awesome-claude-code/issues/new).

This project is released with a [Contributor Code of Conduct](/code-of-conduct.md). By participating, you agree to abide by its terms. 

## Growing thanks to you ❤️
[![Stargazers over time](https://starchart.cc/thedotmack/awesome-claude-code.svg?variant=adaptive)](https://starchart.cc/thedotmack/awesome-claude-code)
