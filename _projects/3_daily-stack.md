---
layout: page
title: Daily Stack
description: A mobile web app for friend groups doing habit challenges, with daily photo check-ins, a live group chat and a wager on who keeps their streak.
img: assets/img/projects/daily-stack.jpg
importance: 3
---

Daily Stack turns a group habit challenge into a shared daily ritual. Friends pick a few habits and a challenge length. Every day, each person proves each habit with a photo. The check-ins land in a live group chat, everyone can see each other's progress, and anyone who misses a day loses the wager. It runs in the phone browser and can be added to the home screen like an app.

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem; margin: 1.5rem 0;">
  <div style="flex: 1 1 180px; max-width: 240px;">
    {% include figure.liquid loading="eager" path="assets/img/projects/daily-stack-challenge.webp" title="Challenge screen" class="img-fluid rounded z-depth-1" caption="Today's habits and progress" %}
  </div>
  <div style="flex: 1 1 180px; max-width: 240px;">
    {% include figure.liquid loading="eager" path="assets/img/projects/daily-stack-checkin.webp" title="Check-in screen" class="img-fluid rounded z-depth-1" caption="Photo check-ins" %}
  </div>
  <div style="flex: 1 1 180px; max-width: 240px;">
    {% include figure.liquid loading="eager" path="assets/img/projects/daily-stack-chat.webp" title="Chat screen" class="img-fluid rounded z-depth-1" caption="Live group chat" %}
  </div>
</div>

**Tools used**

- **React + Vite** for the mobile-first front end
- **Supabase** for sign-in, the database, photo storage and the realtime chat
- **Vercel** for hosting and automatic deploys
- **Brevo** for delivering the sign-in emails

<div style="text-align: center; margin: 2rem 0 1rem;">
  <a href="https://habit-challenge-pi.vercel.app/" target="_blank" rel="noopener" style="display: inline-block; padding: 0.8rem 2rem; border-radius: 999px; background: var(--global-theme-color); color: #fff; font-size: 1.05rem; font-weight: 500; text-decoration: none; box-shadow: 0 4px 14px rgba(0, 0, 0, 0.15);">Try the live app →</a>
</div>
