---
name: paid-community-design
description: Launch and run a paid community - platform choice (Telegram vs Discord vs Whop), pricing gate, structure, onboarding, automated upsells, support, and retention metrics - plus the payment and platform mechanics around it. Use when the user asks "should I start a Discord/Telegram/Whop community", "free vs paid group", "how do I reduce churn", "how do I upsell members", "Stripe froze my account / which payment processor", "should I list on Whop Discover", "can I post Telegram links on X/TikTok", "how do I launch my community", "how much for X Premium/verified org", or wants to add AI tools to a coaching/community offer. Also trigger when a user proposes a free group chat as a funnel.
---

# Paid Community Design

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill walks through launching a paid community end to end. Core thesis: never run a free chat (even $1 filters tenfold), choose Telegram or Discord by the offer, hire support before anything else, treat member data as the real product, automate upsells on engagement milestones, and host checkout on infrastructure that won't freeze your money.

## When to use

- The user is planning any group chat, membership, cohort, or subscription community.
- The user runs a free community and wonders why it doesn't convert or is full of time-wasters.
- The user is choosing between Telegram, Discord, Whop, Skool, Circle, etc.
- The user has churn, support, or moderation problems.
- The user is deciding on payment processors, Whop Discover listing, or platform fees.
- The user asks how to share Telegram links on platforms that suppress them.
- The user wants to launch with attention and asks about controversy or promo tactics.
- The user wants to upgrade a service/community with AI tooling.

## Core principles

**Never run a free group chat - charge at least $1.** EP: even $1 filters low-quality members and improves conversation quality roughly tenfold. Free chats fill with unserious members who drive away serious ones; an unmoderated free-chat section in a paid Discord actively costs sales, and a chat full of time-wasters signals a low-level offer to high-intent leads. Price-gating valuable info is a feature: free material learned by 10k people at once loses its edge.

**Telegram vs Discord - choose by offer.** Telegram suits older, higher-IQ, high-ticket audiences (more notifications enabled, ~4x the monthly active users, native advertising, easier high-ticket sales). Discord suits younger, low-ticket, high-engagement communities (far better channel structure, good for finding cheap labor).

**A good customer support rep is the single highest-ROI hire.** Support quality drives retention, and churn (especially in degen niches) is the real killer. Hire this before a marketer or editor.

**Communities make most of their money from member data.** Segment members by situation and goal, then route each segment to the appropriate next offer instead of treating the community as one undifferentiated audience.

**Automate upsells inside the platform.** EP's Whop automations sequence (2025-10): free course/community as top of funnel → engagement milestones trigger automatic DMs → present a problem in a video, DM the solution as an upsell to the paid service → segment engaged vs unengaged → use engagement to predict churn.

**Mundane niches print.** EP cites $38k MRR teaching pickleball, $60k MRR teaching cycling, a "women empowerment" community past $1M in sales. Stop overthinking niche viability and launch. Review counts are not a quality or revenue signal.

**Info-and-tools model: one affordable subscription, high-ticket reserved for B2B.** EP keeps all info plus most tools in one $75/month subscription and sells high-ticket only as B2B (whitelabeling tools, AI-integration services) rather than high-ticket "mentorship" to individuals (2025-04). Purely info communities are dead: problem-solving + peers + embedded tools.

**Payment-processor lockup is when-not-if.** Stripe froze EP's account with $100k pending and then held 25% of his balance; PayPal is worse. He now hosts his own landing page and processes through Whop (responsive support, lower fees, high-ticket checkout links, BNPL, clipping programs built in). Don't concentrate all revenue in one processor.

**Whop Discover costs 30% on buyers who find you there - opt out if you bring your own traffic** (2024-12). Whop's referral program is a durable side play: refer businesses and pocket a percentage of their fees and ad spend (2026-08).

**X is unusually friendly to off-platform links - put the Telegram link under your tweets.** Where a platform suppresses Telegram links, use YouTube as a link cloak: Telegram link in the video description, share the YouTube link.

**Faceless scales; controversy launches.** EP's PDF (traffic methods + community access) did $10k in 2 hours and ~$35k on day one via an X lead-magnet funnel into Telegram, with most sales from Telegram, not the timeline. Deliberately provoking a tribe that hates your offer earns outraged quote-tweets worth $1,000-$5,000 each as promos, for free - and the haters become witnesses to later success stories.

## Workflow

Gather: niche, audience age/sophistication, price tier planned, what tools/content exist, existing traffic sources, team size.

1. **Set the gate.** Minimum $1; realistically the front-end price band ($15-$50/month or one-off) or an info-and-tools subscription (EP: $75/month). No free tier chat. If a free community is used as top of funnel, keep it a course/feed with automations, not an open chat.

2. **Choose the platform.** Older / higher-ticket / operator audience → Telegram. Younger / low-ticket / high-engagement → Discord. Either way, run checkout, membership gating, affiliates, and upsell automations through Whop (or Gumroad for simple products). Host your own landing page. Do not put all revenue on one processor.

3. **Decide on Whop Discover.** Bringing your own traffic → opt out and keep the 30%. No traffic yet → listing is a paid acquisition channel; reassess once organic works.

4. **Design the structure.** Stack: core product + moderated chat (team keeps it on topic) + educational material + embedded tools (each its own Whop app; coding agents + Whop CLI can one-shot custom apps, 2026-07). Optional AI layer: a coach app trained on your material, or an AI assistant analyzing client check-ins (EP's trainer example: Gemini API daily trend reports + form analysis, paired with weekly calls and an accountability community).

5. **Build onboarding for segmentation.** Use a short Tally form at join (situation, goal, budget/level). Tag members. This is the "member data" asset that routes each segment to its next offer.

6. **Install upsell automations.** Engagement milestones → automatic DM. Video presents a problem → DM the solution as the paid upsell. Segment engaged vs unengaged; treat falling engagement as a churn signal and intervene (support outreach, re-onboarding).

7. **Hire support first.** One good support rep before any other hire. Define response-time targets and a moderation standard for the chat.

8. **Plan the launch traffic.** X: link under tweets (link-friendly). Shorts/TikTok → Telegram via YouTube link cloak if needed. High-intent YouTube search VSLs (use vidIQ to find low-competition keywords). Optional: a controversy angle that provokes the tribe that hates the offer (only if you can later flip the script with real results).

9. **Instrument and review retention metrics** (PostHog for funnel/session replay; Whop engagement data). Review weekly.

## Checklists / templates

### Platform decision

| Signal | Telegram | Discord |
|---|---|---|
| Audience | older, higher-IQ, operators | younger, high-engagement |
| Ticket | high | low |
| Structure needs | simple channel/feed | many channels, roles |
| Bonus | native ads, ~4x MAU, notifications on | cheap labor pool |

### Onboarding form (Tally) - fields for segmentation

- What's your current situation? (level / role / stage)
- What outcome do you want from this community in 90 days?
- What have you already tried?
- Budget/commitment level (or "are you running a business or employed?")
- What would make you cancel?

### Upsell automation sequence (EP, 2025-10)

1. Free course/community = top of funnel.
2. Engagement milestone (e.g., finished module N, X days active) → automatic DM.
3. Video presents a problem → DM the solution as the paid-service upsell.
4. Segment engaged vs unengaged.
5. Engagement metrics → churn prediction → support intervention.

### Retention metrics checklist

- [ ] Monthly churn (by segment; degen niches highest risk).
- [ ] Support response time and resolution rate.
- [ ] % of members tagged/segmented at onboarding.
- [ ] Engagement milestone completion rate.
- [ ] Upsell DM → conversion rate per segment.
- [ ] Chat on-topic ratio (moderation working?).
- [ ] Revenue by processor (no single point of failure).
- [ ] Discover-attributed vs own-traffic sales (is the 30% worth it?).

## Anti-patterns

- Free group chats, or an open free-chat section inside a paid community.
- Choosing Discord for a high-ticket operator audience (or Telegram for a teen gaming crowd).
- Treating all members as one audience with one next offer.
- Hiring marketers/editors before a support rep.
- All revenue on Stripe/PayPal.
- Listing on Whop Discover while bringing your own traffic (paying 30% needlessly).
- Judging a community by review count.
- Purely info-based communities with no tools or peer problem-solving.
- Selling high-ticket "mentorship" to individuals when the info-and-tools subscription plus B2B is the cleaner model (EP's preference, 2025-04).

## Dated / volatile notes

- Whop Discover 30% affiliate commission on Discover-sourced buyers (2024-12); Whop referral fee-share program (2026-08).
- Whop automations app upsell sequence (2025-10); AI coach apps in Whop app store (2025-10); Whop CLI custom apps (2026-07).
- Info-and-tools subscription $75/month; high-ticket reserved for B2B (2025-04).
- X platform pricing: ~$200/month gold checkmark on a business account; $1,000/month to grant affiliate badges to associated accounts (2025-04).
- AI-made promo benchmarks: ~1 sale of a $20 product per 1,000 views on a fully AI-made promo; VSL-style AI videos ranked for high-intent trading keywords pulled $300-$500 per 1,000 views.
- Telegram ~4x Discord MAU and native advertising - platform stats shift.
- Stripe/PayPal lockup anecdotes and Whop fee/support claims are EP's experience at time of writing.
- Tools: Whop (checkout/membership/affiliates/upsells), Tally (forms), PostHog (funnel analytics, session replay), vidIQ (YouTube keyword research).

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with: `info-products-sell-transformation` (the ladder the community sits in), `funnels-and-owned-channels` (feeding the community), `selling-without-sales-calls` (checkout), `monetization-playbooks` (Telegram channel plays), `ethical-selling-and-grifter-detection`, `partnerships-hiring-delegation`.
