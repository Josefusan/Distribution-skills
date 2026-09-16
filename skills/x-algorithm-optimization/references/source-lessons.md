Source: https://www.eptwts.com/growing-an-audience — EP (@eptwts), chapter "Growing an Audience". Verbatim excerpts.

## How the X Algorithm Works

**The algorithm is open-source - interrogate it.**
The X recommendation algorithm repository is public: feed it to an LLM and ask how ranking works, what signals are weighted, and how to design posts around them. There is no secret sauce to going viral on any platform. Algorithms are learnable rules; reverse engineer what gets pushed and produce that.

**The core ranking model predicts user actions and scores your post per viewer.**
An AI model predicts the odds that each viewer takes roughly 20 specific actions on your post, each with a weight (as of early-mid 2026).
Heaviest positive signals: retweets and quotes (takes people want to argue with or co-sign), follows of the author (triggered by demonstrated expertise: "if this is their random tweet, imagine the rest"), dwell time (threads, articles, lists that stop the scroll), and video views past a minimum watch-time threshold.
Strong signals: replies (questions, relatable experiences, controversial takes), profile clicks, external shares (DM shares especially), and visual hooks that prevent a fast scroll-past.
Supporting signals: click-to-expand, photo expands (detailed infographics, small-text screenshots), quoted-tweet clicks, bookmarks.
Likes matter less than assumed - a cheap signal.
Negative weights collapse reach: "not interested" (irrelevant content, undelivered clickbait), mutes (posting too much, repetitive topics), blocks (toxicity), and reports.

**Distribution runs on a personalized relationship graph.**
The algorithm profiles every viewer from their last ~127-128 engagements, follows, and mutes, and scores your post against that taste pattern, so hyper-specific content finds exactly its audience.
Posts reach people two ways: in-network (followers, whose feeds multiply your score) or out-of-network AI matching to strangers with similar taste, which is why 1,000 real followers beat 10,000 random impressions.
Reaching strangers requires early positive engagement from your immediate network, which the algorithm uses for taste-matching ("simclusters": content popular within your community gets amplified, and bridging multiple communities enables viral spread).
Spammy engagement - engagement groups, mass follow-backs - dilutes your graph signal and hurts future distribution.
Every post also carries silent metadata (video length, language, media type, brand safety) that shapes reach, posts older than 7 days are filtered out entirely, and cheap filters penalize muted keywords and spammy reused formats.

**Author reputation compounds.**
Accounts carry a reputation score ("tweepcred") built from how people react to your content; a high-authority small account can out-reach a 100k-follower account.
Consistency, topic-specific authority, and a text-quality score that rewards readability, line breaks, and clear structure (and penalizes ALL-CAPS) all feed it.
Toxicity scores and detected inauthentic engagement patterns nerf reach.

**Engagement velocity was king; content scoring now leads (as of late 2025).**
For most of 2024-2025 the dominant mechanic was the first 30 minutes: if a tweet out-engaged your usual baseline early, the algorithm pushed it wider, so posting time, hooks, and engagement circles mattered most.
A late-2025 algorithm change shifted this: posts are now scored more on their actual content, via AI/LLM classification (Grok analyzing the text), than on raw engagement ratios.
Posts with amazing engagement ratios stalled at 3k views, and "reply for X" lead-magnet posts that would have gone viral three months earlier stopped working.
Quote tweets are slightly favored, video/media heavily favored, and by January 2026 non-followers began seeing tweets within the first 1-2 hours, making follower-external reach much better for quality content.
Practical takeaway: optimize the substance and media of each post rather than engagement-bait mechanics.

**Dwell time is a core ranking input - engineer for it.**
The longer people spend on your post, the bigger the push.
This is why prompt-sharing posts go viral (viewers stop, read, and copy the prompt), why long well-formatted posts that trigger "show more" outperform short ones, why screenshots can beat quote-tweets (readers must stop and read), and why X articles were heavily favored.
I posted a text sales letter as an article and got 100k views with strong conversion (as of early 2026; expect the format to saturate).
Write posts that hold attention and get saved, not posts skimmed in one second.

**Profile clicks are heavily weighted.**
Content that makes people click into your profile boosts distribution - the same signal that makes accounts provoking instinctive profile checks go viral more easily. Optimize for authority and intrigue.

**Quote tweets outperform standalone tweets.**
Despite getting less engagement, quote tweets almost always out-reach cold posts, and the boost scales with how well the quoted tweet itself is performing (as of mid 2026). Quote strong posts rather than posting cold.

**Space posts out - the diversity decay changed the volume math (as of 2026).**
The algorithm penalizes your 2nd, 3rd, and 4th post shown to the same viewer (roughly 70%, then 50% score), so one banger now beats five mid posts.
Note this is a change: in 2024 there was no observable posting-frequency penalty on X, and extreme volume was a viable cold-start strategy.

**Platform quirks worth knowing.**
Follower totals mean little - dead followers don't hurt, because what pushes a post is engagement from the people who actually see it.
Creator payouts are driven by engagement from X Premium accounts, but Premium itself gives only a slight ranking boost and is not necessary (I grew to 4,000 followers before buying it).
Replies to replies barely boost a tweet. Starting a tweet with an @ makes it act like a private mention that skips the For You feed.
Low-effort agreement replies that restate the original tweet add nothing and do not build an audience.

