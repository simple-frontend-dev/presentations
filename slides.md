---
theme: default
colorSchema: light
title: Frontend Engineering at Scale
transition: slide-left
mdc: true
---

# Frontend Engineering at scale

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
        <div class="mx-auto mt-12">I am working part-time at Storyblok (headless CMS) where I lead the Product Frontend team</div>
        <img src="/images/storyblok-logo.png" class="mx-auto mt-30 h-10" />
    </template>
    <template #4>
        <div class="mx-auto mt-12">I built Watchly, an incident management tool that knows everything about your production changes from deployments to feature flags changes.</div>
        <img src="/images/watchly.png" class="mx-auto mt-14 h-60" />
    </template>
</v-switch>

---
layout: center
---

# Why you should care about today's presentation

(even if it's not about AI..)

---
layout: quote
---

### "One of the most durable mental models around AI has been that of an amplifier. We largely agree, by now, that AI amplifies your existing practices — good and bad."

<br />
<br />

### "The best time to invest in good developer experience was years ago, but the second best time is now. Good devex is the floor that enables your team to profit from AI."

<br />

Luca Rossi - Refactoring (March 2026)

---
layout: center
---

# Tiers of frontend development

---
layout: center
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

2. Large monorepo with evergreen dependencies (Vercel). Colocation means it's easy to share, synchronize and updates patterns accross and products.

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
---

## Still not convinced?

<br />
<br />

## Another lense to look at things with frontend technical debt vs technical investment over time

<!--
Here I am using technical debt as a proxy for productivity which we know is kind of plain wrong
-->

---

<div>The "traditional" approach</div>
<img src="/images/tech-debt-investment-1.png" class="mx-auto mt-14 h-100" />

---

<div>With a Frontend Platform</div>
<img src="/images/tech-debt-investment-2.png" class="mx-auto mt-14 h-100" />

---
layout: center
---

# How to get there?

<!--
Le fil rouge (Continuous small investment to prevent decay) “In an isolated system, entropy will only increase”
Engineers taking kind of the product role

Part 3. Some good stuff you should ask

It’s custom / based on your business but common things include..
Design System (with tokens)
End-to-End types
Package manager
Linting
Formatting
Observability
AB testing / Feature Flags

How to experiment with a small tool

Monorepo tooling
-->
