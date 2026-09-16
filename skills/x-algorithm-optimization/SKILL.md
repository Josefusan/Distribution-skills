---
name: x-algorithm-optimization
description: Audit and optimize an X (Twitter) post or account against the ranking signals the open-source X algorithm actually weights (retweets/quotes, follows, dwell time, profile clicks, replies, negative signals, tweepcred, author-diversity decay). Trigger when the user asks why a tweet flopped or stalled, how the X/Twitter algorithm works, how to get more impressions/reach/views on X, whether to post as a thread/article/screenshot/quote tweet, how often to post, or asks you to review/score a draft tweet before posting. Also trigger on "my engagement is good but views are capped", "should I buy X Premium for reach", "does posting time matter", or any request to reverse-engineer the For You feed.
---

# X Algorithm Optimization

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are opinionated operator heuristics, not official X documentation.

Core thesis: the X recommendation algorithm is public code with learnable rules. It scores every post per viewer by predicting roughly 20 actions, weights them, and multiplies by author reputation and viewer taste-match. There is no secret sauce. Reverse-engineer which signals get pushed, design each post to trigger them, and stop wasting effort on cheap signals (likes) and dead mechanics (early-engagement bait, "reply for X").

## When to use

- The user shares a draft tweet/thread/article and wants it scored or improved before posting.
- A post got strong engagement but stalled at a low view count (EP's example: great ratios, stuck at 3k views).
- The user asks how X ranking works, what signals matter, or wants to feed the algorithm repo to an LLM.
- Choosing a format: thread vs article vs screenshot vs quote tweet vs cold post vs video.
- Deciding posting frequency, spacing, or whether volume still works.
- Account-level audit: reach is declining, or the user suspects mutes/"not interested"/toxicity penalties.
- The user asks whether X Premium, follower count, or replying to replies helps reach.

## Core principles

**The algorithm is open-source; interrogate it, don't guess.** EP's instruction: feed the public X recommendation repo to an LLM and ask how ranking works and what is weighted. Algorithms are learnable rules; produce what gets pushed.

**Score is a weighted sum of predicted actions per viewer, and likes are cheap.** Per EP (early-mid 2026): heaviest positives are retweets and quotes, follows of the author, dwell time, and video views past a minimum watch threshold. Strong: replies, profile clicks, external shares (DMs especially), visual hooks that stop the scroll. Supporting: click-to-expand, photo expands, quoted-tweet clicks, bookmarks. Likes matter less than assumed. Design for the top of that list.

**Negative signals collapse reach and are the first thing to audit.** "Not interested" (irrelevant content, undelivered clickbait), mutes (posting too much or repetitively), blocks (toxicity), and reports. A post that earns these poisons future distribution, not just this one.

**Distribution runs on a personalized relationship graph, so specificity wins.** The algorithm profiles each viewer from their last ~127-128 engagements, follows, and mutes. Hyper-specific content finds exactly its audience through simclusters (content popular within a community gets amplified there; bridging communities enables viral spread). This is why EP says 1,000 real followers beat 10,000 random impressions: followers' feeds multiply your score and seed out-of-network matching.

**Author reputation ("tweepcred") compounds; a small authoritative account can out-reach a 100k account.** Reputation is built from how people react to your content, consistency, topic-specific authority, and a text-quality score rewarding readability, line breaks, clear structure (ALL-CAPS penalized). Toxicity and inauthentic engagement patterns nerf it. Engagement groups and mass follow-backs dilute your graph signal.

**Engagement velocity was king; content scoring now leads (late 2025).** For most of 2024-2025 the first 30 minutes decided reach. EP reports a late-2025 change: posts are scored more on actual content via AI/LLM classification (Grok reading the text) than on engagement ratios. "Reply for X" lead-magnet posts stopped working; by January 2026 non-followers see tweets within 1-2 hours. Takeaway: optimize substance and media, not engagement-bait mechanics.

**Dwell time is a core input; engineer posts that hold attention.** Prompt-share posts, long well-formatted posts that trigger "show more", screenshots readers must stop and read, and X articles all win on dwell. EP posted a text sales letter as an article and got 100k views with strong conversion (early 2026; expect saturation). Write posts that get read and saved, not skimmed in one second.

**Profile clicks are heavily weighted; optimize for authority and intrigue.** Content that provokes an instinctive profile check ("if this is their random tweet, imagine the rest") goes viral more easily and triggers follows, another heavy signal.

**Quote tweets out-reach cold posts, scaled by how well the quoted post is performing (mid 2026).** Even with less engagement, quotes almost always beat standalone tweets. Quote strong posts rather than posting cold.

**Author-diversity decay changed the volume math (2026): one banger beats five mid posts.** Your 2nd, 3rd, and 4th posts shown to the same viewer are penalized (roughly 70%, then 50% score). In 2024 there was no observable frequency penalty and extreme volume worked as a cold start; that is no longer true. Space posts out.

**Follower totals and Premium barely matter; engagement from actual viewers does.** Dead followers don't hurt. Premium gives only a slight ranking boost (EP reached 4,000 followers before buying it); payouts, not reach, are what Premium engagement drives.

## Workflow

Use this to audit a single post or an account. Ask for the draft (or the account handle plus recent analytics) if not provided.

1. **Establish the baseline.** Ask what the account's normal impressions per post are. If there is no steady baseline (small account), say so: the algorithm is only predictable once impressions are consistent. Route small accounts to `x-growth-from-zero` and keep this audit lightweight.

2. **Classify the goal of the post.** Reach, follows, profile clicks, DMs/leads, or off-platform clicks. Each goal maps to different heavy signals (follows and profile clicks want demonstrated expertise; reach wants quotes/retweets; leads want dwell plus a reason to DM).

3. **Run the negative-signal audit first.** Check: Is the topic relevant to the account's established cluster? Does the hook promise something the body delivers (undelivered clickbait earns "not interested")? Is the account posting the same format/topic repeatedly (mutes)? Any toxicity (blocks)? Any muted keywords, spammy reused formats, or ALL-CAPS? Does it start with an @ (acts as a private mention and skips For You)? Fix these before anything else; nothing downstream compensates for them.

4. **Score against the positive signals.** Use the pre-post scoring checklist below. For each heavy/strong signal, ask concretely how this post triggers it. If the honest answer for retweets/quotes, follows, dwell, and profile clicks is "it doesn't", the post is a mid post and the diversity decay means it costs future reach. Decision: rewrite it or cut it.

5. **Pick the format for dwell time.** If the content is a list, prompt, or step-by-step: format as a long post with clean line breaks so it triggers "show more", or as an X article. If it is a reaction to someone else's strong post: quote-tweet it (scales with the quoted post's performance) or screenshot it if the reader needs to stop and read. If there is any relevant video or image, attach it; media is heavily favored. One idea per line, scannable structure.

6. **Check the content-scoring layer.** Since late 2025 the text itself is classified. Ask: would an LLM reading only this text classify it as substantive, topic-specific value from someone with authority? Strip engagement bait ("reply X for the doc", "like if you agree"); these no longer carry the post and read as low-quality.

7. **Decide spacing.** With the 2026 diversity decay, plan one strong post before the next rather than a burst. If the user has several drafts, rank them and schedule the best; drop the rest or merge them.

8. **Post-hoc diagnosis (if auditing a stalled post).** Distinguish: high engagement but capped views (content-scoring or cluster mismatch: the text was classified as low value or reached the wrong simcluster) versus low engagement everywhere (hook/format problem) versus sudden account-wide decline (negative-signal accumulation, inauthentic engagement, or over-posting). Prescribe accordingly: rewrite substance; fix hook/media; or pause, reduce frequency, and cut engagement groups.

9. **Account-level pass (optional).** Review the last 20 posts for topic consistency (topic-specific authority feeds tweepcred), readability, and whether the account quote-tweets strong posts or only posts cold. Recommend the mix shift.

## Checklists / templates

### Pre-post scoring checklist

Score each line 0-2 (0 = no, 1 = weak, 2 = clearly yes). Heavy signals count double.

Heavy (x2):
- [ ] Will people want to retweet or quote this (to co-sign or argue)?
- [ ] Does it demonstrate expertise strong enough to trigger a follow?
- [ ] Will readers stop and read for more than a few seconds (list, prompt, screenshot, "show more", article)?
- [ ] If video: does it hold viewers past the minimum watch threshold?

Strong (x1):
- [ ] Does it invite a substantive reply (question, relatable experience, defensible controversial take)?
- [ ] Does it make readers curious enough to click the profile?
- [ ] Would someone DM this to a friend or colleague?
- [ ] Is there a visual hook that stops a fast scroll?

Supporting (x1):
- [ ] Is it worth bookmarking ("will they need this later")?
- [ ] Is there a photo/infographic/screenshot worth expanding?

Hard fails (any one = rewrite):
- [ ] Hook over-promises what the body delivers.
- [ ] Starts with @.
- [ ] ALL-CAPS, wall of text, no line breaks.
- [ ] Repeats a topic/format the account has posted many times recently.
- [ ] Relies on "reply/like for X" bait to carry it.
- [ ] Toxic, or targets a group in a way that invites blocks/reports.

Interpretation: a post scoring mostly 0s on the heavy section is a mid post; with the diversity decay, it costs the next post's reach. Rewrite or drop.

### Format decision table

| Content type | Best format | Why (EP) |
|---|---|---|
| Reaction to a strong post | Quote tweet | Out-reaches cold posts; scales with quoted post's performance |
| Something readers must read closely | Screenshot | Forces a stop-and-read; can beat quote tweets |
| Prompt, framework, list | Long post with line breaks or article | Triggers "show more"; dwell time |
| Long-form sales letter | X article | 100k views with strong conversion (early 2026) |
| Anything with relevant footage | Native video | Heavily favored; watch time is a heavy signal |
| Reply to a reply | Skip | Barely boosts the tweet |

## Anti-patterns

- Chasing likes. They are the cheapest signal; a post optimized for likes is not optimized for reach.
- Engagement groups, mass follow-backs, bought engagement: they dilute the graph signal and register as inauthentic patterns, nerfing tweepcred.
- Posting 5 mid posts in a burst. The diversity decay means the 2nd-4th impressions to the same viewer are scored down; one banger beats five.
- "Reply for X" lead-magnet bait as a reach mechanic. EP reports it stopped working after the late-2025 content-scoring shift.
- Clickbait hooks that under-deliver. They earn "not interested", which suppresses future posts.
- Starting a post with @ and expecting For You distribution.
- Low-effort agreement replies that restate the original tweet: add nothing, build nothing.
- Treating follower count or Premium as the lever. Neither moves reach much.
- Optimizing posting time and hooks for a 30-minute velocity window. That mechanic is largely superseded.

## Dated / volatile notes

- Early-mid 2026: ~20 predicted actions with weights; the signal tiers above reflect that snapshot.
- Late 2025: shift from engagement-velocity ranking to content scoring via AI/LLM classification (Grok). "Reply for X" posts nerfed.
- January 2026: non-followers begin seeing tweets within the first 1-2 hours.
- Early 2026: X articles heavily favored; EP's sales-letter article hit 100k views. Expect the format to saturate.
- Mid 2026: quote tweets favored, boost scales with the quoted post's performance.
- 2026: author-diversity decay (roughly 70%, then 50% score for 2nd-4th posts per viewer). In 2024 there was no frequency penalty.
- Viewer profile uses last ~127-128 engagements; posts older than 7 days are filtered out entirely.
- Premium: slight ranking boost only; EP grew to 4,000 followers without it.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `x-growth-from-zero` (cold-start before the algorithm is predictable), `content-principles-and-audience-quality` (what to say so the signals fire honestly), and `platform-strategy-and-youtube-mechanics` (where X sits in the platform mix).
