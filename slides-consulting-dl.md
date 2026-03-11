---
theme: default
colorSchema: light
title: Frontend Engineering at Scale & Migrating to a Frontend Platform
transition: slide-left
mdc: true
author: Jeremy Colin
favicon: /images/favicon.svg
---

# Frontend Engineering at Scale & Migrating to a Frontend Platform

---

# Hi! I'm Jeremy

<v-switch>
    <template #1>
        <div class="mx-auto mt-12">I contributed to then led the Web Platform team at Zalando from 2018 to 2024</div>
        <img src="/images/zalando-blog-2018.png" class="mx-auto mt-14 h-60" />
    </template>
    <template #2>
        <div class="mx-auto mt-12">Now I am helping companies ship better web experiences, faster with Simple Frontend</div>
        <img src="/images/simple-frontend.png" class="mx-auto mt-20 h-40" />
    </template>
    <template #3>
        <div class="mx-auto mt-12">I am also working part-time at Storyblok (headless CMS) where I lead the Product Frontend team</div>
        <img src="/images/storyblok-logo.png" class="mx-auto mt-30 h-10" />
    </template>
</v-switch>

---
layout: center
class: text-center
---

# Tiers of frontend development

---
layout: center
class: text-center
---

# Tier 1: The Growing Monolith

---

<div class="text-xl">
Supported by a framework, all of your code code is in a shared repo that is bundled and deployed all at once.

This is the what the default starting point for most frontend setups lead to.

<br />

<v-clicks>

- It's not a bad thing!
- It will get you much further than you might think
- As your app grows, you organize your code by features, and you start worrying about increasing build and deployment time

</v-clicks>

<br />

<v-clicks>

This starts to break down when you have multiple teams responsible for different product areas.

Everyone wants more autonomy in order to ship faster and more frequently. It's time for Tier 2

</v-clicks>

</div>

---
layout: center
class: text-center
---

# Tier 2: Polyrepositories (and Frontend Microservices)

---

There are 2 flavors here depending on your actual product but they both involve seperate repositories:

1. Independant products with their own repositories
2. A product with independant teams with their own repositories, composed at runtime

<v-clicks>

There are a lot of upsides:

</v-clicks>

<v-clicks>

- Teams are now fully autonomous
- They have independant, easy-to-deploy releases
- They can decide and own their architecture and patterns

</v-clicks>

<v-clicks>

You might already see some downsides:

</v-clicks>

<v-clicks>

- In case of frontend microservices, you have to maintain a new layer
- Patterns and best practices start to diverge accross repositories
- Teams may start to re-implement similar functionalities and requirements (authentication, data fetching, accessibility etc)

</v-clicks>

<br />

---

This works well for a while but if your business is still successful after a year or so you will notice bigger downsides:

<v-clicks>

- You start to notice UI inconsistencies (whichs effect are worse for a single product setup)
- 30%+ of your frontend teams's capacity is spent on maintenance (dependencies update, vulnerabilities, bug fixes, etc) and infrastructure (developer experience, observability, etc)
- Cross team contributions are hard to execute and not super effective
- There are more and more functionalities duplicated accross repositories

</v-clicks>

<v-clicks>

Of course, there are many things you can do to improve the situation:

</v-clicks>

<v-clicks>

- A shared Design System and component library
- Shared libraries for repeated functionalities
- Agreements on patterns and best practices

</v-clicks>

<v-clicks>

However, updates are still painful and with more teams, redudant work is costly. You're now ready for Tier 3

</v-clicks>

---
layout: center
class: text-center
---

# Tier 3: Frontend Platform

---

What if all your frontend product teams didn’t have to worry about upgrading their version of Node.JS or React, implementing internationalization, or integrating with your latest observability vendor?

Enter your **Frontend Platform**.

<v-clicks>

Here they are also different possible implementations for a Frontend Platform Architecture:

</v-clicks>

<v-clicks>

1. Platform as a runtime (Zalando, Wix). Think of it as "Vercel" for all your frontend changes. You have access to observability, A/B testing, opininated data fetching and state management and can focus on writing business logic for product features.

2. Large monorepo with evergreen dependencies (Vercel). Colocation means it's easy to share, synchronize and updates patterns accross teams and products.

</v-clicks>

<br />

<v-clicks>

The Wix.com team has reported development velocity improvements in the 50% to 80% range with their platform runtime initiative (which was not limited to the frontend).

At Zalando, I saw similar productivity gains with our microfrontends approach, Interface Framework.

</v-clicks>

<!--
by giving developers a golden path with an in-house, highly opinionated framework. It takes time to get there, but the reward is well worth it
-->

---
layout: center
class: text-center
---

# Zalando Migration to Interface Framework

---

<img src=" /images/html-page-fragments.webp" class="mx-auto mt-15 h-80" />

---

## Motivation for the migration

<br />
<br />

<v-clicks>

- ### Fix UI inconsistency to push a stronger brand proposition
  <br />
- ### Facilitate cross team contributions and projects
  <br />
- ### Remove duplicated infra and maintenance work
  <br />
- ### Create a "level playing field": lower the barrier for contributions for smaller teams
  <br />
- ### Dynamic View Composition

</v-clicks>

---

## Core Migration Principles

<br />
<br />

<v-clicks>

- ### Deliver value early
  <br />
- ### Wrap the previous system: Interface Framework was designed as a superset of Tailor. This allowed for Incremental Migration and Strangler Fig Pattern.
  <br />
- ### Align migrations with business deliveries: only migrates premises when they is actually a need or large changes
  <br />
- ### High level of alignments from the top

</v-clicks>

---

## Early Challenges

<br />
<br />

<v-clicks>

- ### Keeping page performance on par with previously heavily optimized pages
  <br />
- ### Push back on "over simplicity" and lack of expert engineers buy-in
  <br />
- ### Inner source contribution model definition
  <br />
- ### A lot to build

</v-clicks>

---

## Early Success

<br />
<br />

<v-clicks>

- ### Find and rely on your champions
  <br />
- ### Show the value
  <br />
- ### Make teams want to migrate versus a mandate
  <br />
- ### Celebrate every small wins

</v-clicks>

---

## Organization Impact

<br />
<br />

<v-clicks>

- ### Work Scope change (from Infra to Product) for most engineers
  <br />
- ### Owning pieces of code in multiple systems
  <br />
- ### Product Mindset
  <br />
- ### Global projects wins

</v-clicks>

---

## Communication challenges and what worked

<br />
<br />

<v-clicks>

- ### Frequent syncs, early feedback and validation
  <br />
- ### Short feedback loops were key
  <br />
- ### Finding the right level of abstraction: understand what to build versus what people want

</v-clicks>

---

## What we initially did not get right

<br />
<br />

<v-clicks>

- ### The platform becoming a bottleneck (code reviews / gatekeeping / support)
  <br />
- ### Unclear or insufficient onboarding and documentation
  <br />
- ### Unclear ownership boundaries between the Platform team and the Features team
  <br />
- ### A bit of over-engineering

</v-clicks>

---

## What worked well

<br />
<br />

<v-clicks>

- ### Building self-service capabilities
  <br />
- ### Providing horizontal capabilities: A/B testing, Observability, Configuration etc
  <br />
- ### CODEOWNERS file
  <br />
- ### Sharing Roadmaps and RFCs transparently
  <br />
- ### Collaboration with infra teams

</v-clicks>

---

## Quotes from the Zalando Engineering Blog

"We are still organized around feature teams which have frontend engineers embedded. The main difference is that now they are working in a monolithic repository providing a unified and automated environment that offers new joiners a quick onboarding"

"There is quite a cultural shift as some ownership lines are now blurred in Renderers, with multiple teams contributing to most of them. As a result, we now have a much more collaborative development environment where teams benefit from their best practices. A centralized repository also means it is easier to ship large project changes and contribute to other teams' code, supported by a set of contribution guidelines."

"We now have an aligned set of modern frontend technologies (React, TypeScript, GraphQL), a centralized server infrastructure, a release process, and a robust set of monitoring capabilities with dashboards and alerts. We are more efficient in terms of operations, and new reliability patterns immediately impact the whole website."

---

## Wrapping up

<br />
<br />

<v-clicks>

- ### It took years but it was well worth it
  <br />
- ### Biggest shift was the product mindset for the platform and inner contribution model
  <br />
- ### Impact was so big that now the Web Platform architecture is being transferred to the Mobile Apps.

</v-clicks>
