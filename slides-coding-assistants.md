---
theme: default
colorSchema: light
title: AI coding assistants
transition: slide-left
mdc: true
---

# AI Coding Assistants

---
layout: center
---

# They are both a blessing and a curse

---
layout: center
---

# Let's get the curse out of the way

---

# It's not **intelligent**, it's **statically relevant**

<br />
<br />

- ## Given an input query, with they will product a statically relevant output and autogenerate from there

<br />
<br />

- ## LLMs will **make mistakes** and **hallucinate**

<br />
<br />

- ## You are **responsible** for their output

---

# They will **atrophy** your developer brain

<br />
<br />

- ## Do not delegate things you don't already know (especially with agent mode)

<br />
<br />

- ## You will lose your code **mental model**

<br />
<br />

- ## Some things are great to delegate like a refactoring task or doing an integration you already know well how to do

---
layout: center
---

# Now the good parts

---
layout: center
---

# Tab Tab Tab

<br />

## This is my personal favorite experience of using AI coding assistants

---
layout: center
---

# Storyfront demo apps/storyfront/src/store/modules/App/discussions.ts

---
layout: center
---

# Let's chat!

<br />

## Local "ChatGPT" with full code context

---
layout: center
---

# Storyfront demo .github/workflows/e2e-playwright-tests.yml

---
layout: center
---

# Agent Mode

<br />

## ~~Vibe Coding~~ Context Engineering

---
layout: image
image: /images/bumper.webp
backgroundSize: contain
---

---

# You need **guardrails**

<br />
<br />

## 1. Very clear expectations

<br />
<br />

## 2. Focused Context

<br />
<br />

## 3. Success Criteria for feedback loops

<br />
<br />

## 4. Accept mistakes and fix input rules

---

# 1. Very clear expectations

## We're getting used to prompting now so it's about following best practices

<br />

### Be as specific and explicit as possible:

~~"Please refactor this code"~~

"Please refactor this component from the Vue options API to the Composition API following guidelines in our AGENTS.md file"

~~"Help me solve a bug in this file"~~

"We have an issue where the tooltips are staying on screen, we tracked the problem down to this method (highlight lines for agent), can you give it a try?"

---
layout: center
---

# **AGENTS.md**

<br />
<br />

# Storyfront demo AGENTS.md

---

# 2. Focused Context

<br />
<br />

### - Fresh Chats: each time you start with a new task, create a new chat, even on most follow up tasks as it helps keeping token usage down and limits hallucinations with smaller context windows

<br />
<br />

### - When you know the code changes span multiple files, include all of them in the context

<br />
<br />

### - You can pass additional context such as a docs page

[Example with Jira API breaking changes](https://developer.atlassian.com/changelog/#CHANGE-2046)

---

# 3. Success Criteria for feedback loops

<br />

### 1. Explain the "definition of done"

"The code needs to adhere to our TypeScript and ESLint rules"

"You can run this command to validate the unit tests are passing:

`yarn test:unit apps/storyfront/src/components/counter/__tests__/Counter.test.ts`"

For backend tests, you can use a TDD approach, ask the assistant to write the spec first, review it and then ask it to implement the code by validating the spec is passing.

### 2. Give guidance if the task is complex or target file is large

"After you've done a few changes, immediately run the tests to validate them before continuing."

### 3. Soon these assistants will also be able to access browser windows

---

# 4. Accept mistakes and fix input rules

Unlike us humans - they will make mistakes but we can prevent them by repeating them

<br />

### As mentioned before you are **responsible** for their output

<br />

### Update the **AGENTS.md** file to fix the input rules with guidance (use examples and negative prompts) when:

<br />

- You review the outputs and find issues
- You find a bug in code produced by the assistant (for example with large refactorings hard to review)

<br />

### Like with humans, what's not acceptable is repeating the same mistakes over and over again

---
layout: center
---

# Happy Coding!

<br />

## Thanks to Nathan for the help with the slides

<br />

## Time for Questions & Discussions
