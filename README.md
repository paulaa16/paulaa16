## Hi there 👋

<!--
**paulaa16/paulaa16** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

# Paula | Things I've built

Business Insights Manager at a travel-activities marketplace. MSc in Data Science, BSc in Economics and Finance.

Data and strategy by trade, builder by habit. I help teams make better decisions with data, and increasingly build the tools and AI automations that put those decisions to work.

---

## 1. doiflow: Side-hustle WhatsApp booking assistant for small tourism businesses

**Problem.** Small activity operators (kayak rental, tours) get the same questions all day on WhatsApp: availability, schedules, prices. Many answer late or not at all, especially outside opening hours. I tested this myself by messaging operators as a mystery shopper at night; most never answered the actual availability question.

**What I built.** An AI assistant that answers availability questions and FAQs on WhatsApp, 24/7.

```
Customer on WhatsApp
        |
WhatsApp Cloud API (Meta) -> webhook
        |
Make scenario (routing + logic)
        |
Availability source (Google Sheets in the prototype) + AI model for the reply
        |
Answer sent back on WhatsApp
```

**Status.**
- Working prototype: receives a message, checks availability, replies automatically. <!-- TODO: [Add a 30 second demo GIF or video here] -->. 
- Phase 2 planned: automatic appointment reminders.
- Validating demand: I cold-emailed ~50 active-tourism operators and, in a second test, 20 physiotherapy clinics in Madrid. Two operators asked for a demo meeting, but both no-showed when the time came.
    
**What I learned.**
- To keep the LLM from losing the thread, I store the latest message in a temporary database, so each reply has the context of the conversation.
- I'm moving from Make to self-hosted n8n: Make charges per operation, and with this many steps per conversation the credits were burning very fast. Self-hosting means paying for the server but not per module.
- Building the bot was the easy part. Getting a small business owner to book a call is the hard part.
- In my mystery shopper tests, few operators answered the availability question. What I'm validating now is whether the pain is strong enough for owners to pay for it.

**Stack:** Make, WhatsApp Cloud API (Meta for Developers), webhooks, Google Sheets, LLM API.

---

## 2. Supply optimization workflow (in production at my current company)

**Problem.** A catalog of tens of thousands of activities where a small share drives most of the revenue. The supply team could not manually watch everything that mattered.

**What I built.** An internal web tool, one view per destination, that flags:
- activities with availability problems,
- conversion rate below benchmark,
- prices above competitors.

The team gets a prioritized view instead of a spreadsheet to dig through.

**Impact.** Used daily by the ~30-person supply growth team, covering the top 500 destinations. It changed how the team works day to day.

**Stack:** TypeScript, built with Claude Code. I defined the problem, the metrics and alert logic, and reviewed and iterated on the output with the supply team.

---

## 3. "Related activities" feature (in production at my current company)

**Problem.** When a top attraction had no availability, customers left the site.

**What I did.** I found this pattern in the funnel data, proposed the fix, and worked with product and tech to ship a feature that suggests related activities in that moment.

**Impact.** Drives tens of thousands of euros per month in bookings attributed to the feature: when a user clicks a related activity and buys it within 48 hours, we track it in GA4 by joining user IDs and product IDs.

---

## How I work

- I start from a measurable problem and the people who feel it, then build the smallest thing that tests it.
- I use AI as a builder's tool: agents, automations, and Claude Code to move fast, with a human checking the output.
- I write about data and startups on X to learn in public.
