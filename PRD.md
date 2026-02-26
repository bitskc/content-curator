# Product Requirements Document: Content Curator

**Version:** 1.0  
**Date:** 2026-02-26  
**Author:** Climb (AI Business Partner)  
**Status:** Draft for MVP Development

---

## Executive Summary

**Product Name:** TBD (working titles: Distill, Clipper, ContentFeed)

**One-liner:** AI-powered content curation that monitors podcasts, YouTube channels, and blogs you already follow — extracts shareable snippets relevant to YOUR audience — serves them in a daily feed for one-tap social posting.

**Market Gap:** Every existing tool (OpusClip, Podsqueeze, Flowjin, ClipGen) helps creators repurpose THEIR OWN content. No one helps you curate and share OTHER people's content strategically. Snipd is for personal learning (INPUT). We're for audience building (OUTPUT).

**Target User:** Entrepreneurs, consultants, solopreneurs, coaches, and small business owners who:
- Know they should post consistently on social media
- Already consume podcasts/YouTube/blogs
- Don't have time or energy to manually extract and format shareable content
- Want to position themselves as thought leaders by sharing curated insights

**Business Model:** SaaS subscription, $19-29/month for early access, scaling to $39-49/month post-beta.

**Success Metric:** Get 50+ users actively using the product daily within 90 days of launch. $10K MRR within 6 months.

---

## Problem Statement

### The Pain

1. **Consumption without extraction:** People consume hours of podcasts, YouTube, and blogs each week but don't leverage that content for their own audience building.

2. **Social media posting is a chore:** Entrepreneurs know they "should" post regularly but struggle with:
   - Coming up with ideas
   - Finding time to write
   - Staying consistent

3. **Manual curation is time-intensive:** Manually capturing quotes, reformatting for platforms, and posting takes 15-30 minutes per post.

4. **Context switching kills flow:** Listening to a podcast → stopping to take notes → opening social apps → formatting → posting breaks focus and rarely happens.

### Current Workarounds (All Inadequate)

- **Snipd:** Great for personal notes, not designed for social sharing
- **Manual screenshot + caption:** Time-consuming, inconsistent formatting
- **Hire a VA:** Expensive ($500-2000/month), requires management, hard to convey your "voice"
- **Content curation tools (Taplio, Buffer):** Still require you to find and input content manually

### The Opportunity

Build a tool that sits between consumption and sharing — automatically extracting shareable moments from the content you're already consuming, formatted for your audience, ready to post in seconds.

---

## Target Users & Personas

### Primary Persona: "Busy Builder Andy"

**Demographics:**
- Age: 30-50
- Role: Entrepreneur, consultant, agency owner, coach
- Tech-savvy, uses multiple SaaS tools
- Time-poor, high agency

**Goals:**
- Build personal brand and thought leadership
- Stay top-of-mind with clients and prospects
- Share valuable content without spending hours on social media
- Maintain 3-5 posts per week minimum

**Pain Points:**
- Hates social media but knows it's necessary
- Consumes lots of content (podcasts during commutes, YouTube during work breaks) but doesn't do anything with it
- Wants to post but never has ideas "in the moment"
- Needs content for multiple contexts (business, personal, spiritual)

**Usage Pattern:**
- Checks app 1-2x daily (morning routine, waiting in car)
- Spends 5-10 minutes reviewing snippets
- Schedules 3-5 posts per session
- Primary platforms: LinkedIn, X (Twitter)

### Secondary Persona: "Multi-Hat Maria"

**Demographics:**
- Age: 25-45
- Role: Freelancer, solopreneur, side-hustler
- Juggles multiple projects and clients
- Active on 3+ social platforms

**Goals:**
- Grow multiple audiences (personal brand + business brand)
- Repurpose learning into content
- Engage with communities authentically

**Pain Points:**
- Overwhelmed by content consumption across platforms
- Struggles to maintain consistency across multiple accounts
- Feels like she's "always working" on social media

**Usage Pattern:**
- Wants separate feeds for different personas/brands
- Posts 5-10x per week across platforms
- Values automation and batching

---

## Competitive Analysis

### Direct Competitors (Repurposing YOUR OWN Content)

| Tool | Focus | Pricing | Why They're Not Competitors |
|------|-------|---------|----------------------------|
| **OpusClip** | Video → short clips | $29-79/mo | Only works with YOUR videos |
| **Podsqueeze** | Podcast → snippets | $19-49/mo | Only works with YOUR podcasts |
| **Flowjin** | Video → reels | $29/mo | Only works with YOUR content |
| **ClipGen** | Video → clips | $19/mo | Only works with YOUR content |

### Adjacent Competitors (Personal Learning)

| Tool | Focus | Pricing | Why They're Not Competitors |
|------|-------|---------|----------------------------|
| **Snipd** | Podcast highlights | Free-$9/mo | Personal notes, not social sharing |
| **Readwise** | Reading highlights | $8/mo | Cross-app highlights, not content curation |

### Adjacent Competitors (Social Scheduling)

| Tool | Focus | Pricing | Why They're Not Competitors |
|------|-------|---------|----------------------------|
| **Taplio** | LinkedIn posting | $39/mo | You bring the content, they schedule |
| **Typefully** | X/Twitter threads | $12.50/mo | You write, they format and schedule |
| **Buffer** | Multi-platform scheduling | $6-12/mo | Generic scheduler, no content generation |

### Adjacent Competitors (AI Content Generation)

| Tool | Focus | Pricing | Why They're Not Competitors |
|------|-------|---------|----------------------------|
| **Lately.ai** | Repurpose long content | $49-249/mo | Enterprise pricing, YOUR content only |
| **Copy.ai / Jasper** | AI writing | $49+/mo | General writing, not curation-based |

### Key Insight: We Own a Blue Ocean

**No one is doing:** Monitor OTHER people's content → Extract snippets relevant to YOUR audience → Daily feed for social sharing.

---

## Product Vision & Value Proposition

### Vision Statement

"Make every entrepreneur a thought leader by turning passive content consumption into active audience building."

### Value Propositions (by persona)

**For Busy Entrepreneurs:**
> "You're already listening to podcasts and watching YouTube. We turn that time into your social media strategy — automatically."

**For Multi-Platform Creators:**
> "One feed, multiple audiences. We extract and format content for each of your brands — business, personal, passion projects."

**For Consistency Seekers:**
> "Never run out of things to post. Wake up to 15-20 ready-to-share snippets every morning."

---

## Feature Requirements

### MVP (Must-Have for Launch)

#### 1. Source Management
- **Add sources:** YouTube channels, podcast RSS feeds (Spotify, Apple Podcasts, RSS URLs)
- **Categorize sources:** Tag sources by feed type (Business, Personal, etc.)
- **Manage sources:** Edit, pause, delete sources
- **Limit:** Up to 50 sources per user

#### 2. Feed Configuration
- **Create feeds:** User defines 2-4 feed profiles with context
  - Feed name (e.g., "Business Thought Leadership")
  - Audience description (e.g., "CEOs and startup founders")
  - Tone (professional, casual, inspirational)
  - Topics to prioritize
- **Assign sources to feeds:** Each source can contribute to 1+ feeds

#### 3. AI Extraction Pipeline
- **Automatic monitoring:** Check sources daily for new content
- **Transcript extraction:** Pull text from YouTube, podcasts (via existing transcripts or Whisper API)
- **AI snippet extraction:** For each new episode/video:
  - Extract 2-3 shareable quotes (30-150 words each)
  - Match to user's feed contexts
  - Include attribution (speaker name, episode title, timestamp)
- **Quality filter:** Only save snippets scoring 7/10+ on shareability

#### 4. Daily Feed View
- **Morning digest:** Show all new snippets since last check
- **Filter by feed:** Switch between Business, Personal, etc.
- **Snippet cards:** Display:
  - Quote text
  - Source attribution (name, episode, timestamp)
  - Suggested caption
  - Platform formatting preview (LinkedIn vs X)
  - Action buttons: Copy, Edit, Schedule, Dismiss
- **Pagination:** Infinite scroll or 20 per page

#### 5. One-Tap Sharing
- **Copy formatted post:** One-click copy to clipboard formatted for:
  - LinkedIn (paragraph style with source attribution)
  - X/Twitter (thread format if needed)
  - Instagram caption (hashtags included)
- **Edit before sharing:** Modal to tweak the post
- **Mark as used:** Track which snippets have been posted

#### 6. Basic Scheduling
- **Queue posts:** Add snippets to a posting queue
- **Set date/time:** Simple scheduler (date + time picker)
- **Calendar view:** See scheduled posts by day
- **Note:** MVP does NOT auto-post to platforms (clipboard only)

#### 7. User Onboarding
- **Sign up:** Email + password (Supabase auth)
- **Guided setup:**
  1. "What do you want to post about?" (create first feed)
  2. "Add 3-5 sources to get started"
  3. "We'll process your sources and have snippets ready tomorrow morning"
- **First-run experience:** Show sample snippets with tutorial tooltips

#### 8. Basic Settings
- **Account:** Email, password, billing
- **Preferences:**
  - Notification time for daily digest (email or push)
  - Number of snippets per source per week
  - Tone preferences (formal vs casual)

---

### V2 Features (Post-MVP, Next 3 Months)

#### 1. Direct Social Posting
- **LinkedIn API integration:** Post directly to LinkedIn
- **X/Twitter API integration:** Post directly to X (if API cost is manageable)
- **Multi-account support:** Manage 2-3 social accounts per platform

#### 2. Enhanced AI Features
- **Voice customization:** Learn user's writing style over time
- **Thread generation:** Auto-create multi-tweet threads from longer snippets
- **Image generation:** Create simple quote cards with Canva-style templates

#### 3. Collaboration Features
- **Team workspaces:** Share feeds with team members or VAs
- **Approval workflows:** VA queues posts, user approves before posting

#### 4. Analytics
- **Engagement tracking:** If posting directly, show performance per snippet/source
- **Source quality scoring:** Which sources generate the most-shared snippets?

#### 5. Content Library
- **Save favorites:** Bookmark snippets for later
- **Search/filter:** Find snippets by keyword, source, date

---

### V3 Features (Future Vision)

#### 1. Blog RSS Support
- Add blogs and newsletters to sources
- Extract key takeaways and quotes

#### 2. Video Clip Export
- Generate short video clips with captions (like OpusClip but for OTHER people's content)
- Note: Complex copyright considerations — likely need explicit permission model

#### 3. Mobile App (Native)
- iOS and Android native apps for faster, richer experience
- Push notifications for daily digest

#### 4. Community Feed
- Public feed of popular snippets across all users (opt-in)
- Discover new sources based on what others are curating

#### 5. AI-Generated Commentary
- Not just the quote, but AI writes a short reaction/commentary in user's voice
- "This resonates because..." or "Here's what this means for..."

---

## User Stories & Flows

### User Story 1: Andy's Morning Routine

**As** a busy entrepreneur,  
**I want** to review and schedule social posts in 5 minutes while waiting for my wife,  
**So that** I stay consistent on social media without it feeling like work.

**Flow:**
1. Andy opens app on phone at 8:45 AM
2. App shows "15 new snippets since yesterday"
3. Andy taps "Business" feed filter
4. Scrolls through 8 business-relevant snippets
5. Taps "Copy for LinkedIn" on 3 snippets
6. Opens LinkedIn app, pastes, posts
7. Switches to "Personal" feed
8. Schedules 2 entrepreneurial quotes for later in the week
9. Done in 6 minutes

---

### User Story 2: First-Time User Setup

**As** a new user,  
**I want** to set up my feeds and sources quickly,  
**So that** I can start getting value without a steep learning curve.

**Flow:**
1. User signs up with email
2. Onboarding: "What do you want to post about?"
   - Pre-filled options: "Business & Leadership", "Personal Development", "Health & Wellness", "Tech & Innovation", "Custom"
3. User selects "Business & Leadership" and "Personal Development"
4. Onboarding: "Add sources to your Business feed"
   - Search: "Tim Ferriss podcast" → add
   - Search: "Y Combinator YouTube" → add
   - Paste RSS URL
5. Repeat for Personal feed
6. Confirmation: "We're processing your sources now. Check back tomorrow morning for your first batch of snippets!"
7. Email next morning: "Your daily feed is ready"

---

### User Story 3: Scheduling a Week's Content

**As** a content-conscious user,  
**I want** to batch-schedule a week of posts at once,  
**So that** I don't have to think about social media every day.

**Flow:**
1. User opens app on Sunday evening
2. Views all snippets from the past week (50+ items)
3. Filters by "Business" feed
4. Selects 5 snippets
5. For each snippet:
   - Clicks "Schedule"
   - Picks day/time from calendar view
   - Clicks "Add to queue"
6. Reviews calendar view showing 5 posts scheduled Mon-Fri
7. Clicks "Done" — receives confirmation

---

## Technical Architecture

### System Components

```
┌─────────────────────────────────────────────────────────────────┐
│                         FRONTEND (Next.js PWA)                  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│  │  Dashboard   │  │  Feed View   │  │  Settings    │         │
│  └──────────────┘  └──────────────┘  └──────────────┘         │
└─────────────────────────────────────────────────────────────────┘
                              │
                              │ (API calls)
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      BACKEND (Supabase)                         │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  PostgreSQL Database                                      │  │
│  │  - users, sources, feeds, episodes, snippets, schedules   │  │
│  └──────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  Auth (Supabase Auth)                                     │  │
│  └──────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  Edge Functions                                            │  │
│  │  - /api/monitor-sources (cron: daily)                     │  │
│  │  - /api/extract-snippets                                  │  │
│  │  - /api/send-digest (cron: user-defined)                  │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              │ (calls external APIs)
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      EXTERNAL SERVICES                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│  │  YouTube     │  │  Podcast     │  │  OpenAI API  │         │
│  │  (RSS/API)   │  │  RSS Feeds   │  │  (GPT-4o)    │         │
│  └──────────────┘  └──────────────┘  └──────────────┘         │
└─────────────────────────────────────────────────────────────────┘
```

### Tech Stack

**Frontend:**
- **Next.js 14+** (App Router)
- **TypeScript**
- **Tailwind CSS**
- **Shadcn/ui** (component library)
- **PWA** (for mobile-first experience)
- **Deployment:** Vercel (free tier initially)

**Backend:**
- **Supabase** (PostgreSQL, Auth, Edge Functions, Storage)
- **Supabase Edge Functions** (Deno runtime for serverless)
- **Supabase Cron Jobs** (pg_cron for scheduled tasks)

**AI/ML:**
- **OpenAI API** (GPT-4o or GPT-4o-mini for cost optimization)
- **Prompt chain:**
  1. Extract 3-5 candidate quotes
  2. Score each quote on shareability (0-10)
  3. Keep top 2-3 scoring 7+
  4. Format for each platform

**Content Ingestion:**
- **YouTube:**
  - RSS feeds: `https://www.youtube.com/feeds/videos.xml?channel_id={id}`
  - Transcripts: `youtube-transcript-api` (Python) or Supadata API
- **Podcasts:**
  - RSS feeds (Apple Podcasts, Spotify, direct URLs)
  - Transcripts: Check RSS for `<podcast:transcript>`, fallback to Whisper API
- **Whisper API:** For podcasts without transcripts (~$0.006/minute)

**Third-Party Services (V2):**
- **LinkedIn API** (OAuth + post creation)
- **X/Twitter API** (if feasible given cost)

---

## Database Schema

### Tables

#### `users`
```sql
id: uuid (PK)
email: text (unique)
created_at: timestamp
subscription_tier: text (free, pro, enterprise)
preferences: jsonb {
  digest_time: "08:00",
  snippets_per_source: 3,
  tone: "professional"
}
```

#### `feeds`
```sql
id: uuid (PK)
user_id: uuid (FK → users)
name: text ("Business Thought Leadership")
audience_description: text ("CEOs and startup founders")
tone: text ("professional", "casual", "inspirational")
topics: text[] (array of keywords)
created_at: timestamp
```

#### `sources`
```sql
id: uuid (PK)
user_id: uuid (FK → users)
feed_id: uuid (FK → feeds, nullable if multi-feed)
type: text ("youtube", "podcast_rss", "blog_rss")
name: text ("Tim Ferriss Show")
url: text (RSS feed or channel URL)
metadata: jsonb {
  channel_id: "...",
  last_checked: "2026-02-26T10:00:00Z",
  total_episodes_processed: 42
}
is_active: boolean
created_at: timestamp
```

#### `episodes`
```sql
id: uuid (PK)
source_id: uuid (FK → sources)
title: text
url: text (YouTube video or podcast episode URL)
published_at: timestamp
transcript: text (full transcript)
processed_at: timestamp (when AI extraction ran)
metadata: jsonb {
  duration: 3600,
  speaker: "Tim Ferriss"
}
```

#### `snippets`
```sql
id: uuid (PK)
episode_id: uuid (FK → episodes)
feed_id: uuid (FK → feeds)
user_id: uuid (FK → users)
quote_text: text (the extracted quote, 30-150 words)
context: text (surrounding context if needed)
timestamp: int (seconds into episode where quote appears)
shareability_score: float (0-10)
suggested_caption: text (AI-generated caption)
formatted_posts: jsonb {
  linkedin: "...",
  twitter: "...",
  instagram: "..."
}
status: text ("pending", "used", "dismissed")
used_at: timestamp
created_at: timestamp
```

#### `scheduled_posts`
```sql
id: uuid (PK)
user_id: uuid (FK → users)
snippet_id: uuid (FK → snippets)
platform: text ("linkedin", "twitter", "instagram")
scheduled_for: timestamp
post_content: text (edited version if user customized)
status: text ("queued", "posted", "failed")
posted_at: timestamp
created_at: timestamp
```

### Indexes

```sql
CREATE INDEX idx_sources_user_id ON sources(user_id);
CREATE INDEX idx_episodes_source_id ON episodes(source_id);
CREATE INDEX idx_snippets_user_feed ON snippets(user_id, feed_id);
CREATE INDEX idx_snippets_status ON snippets(status);
CREATE INDEX idx_scheduled_posts_user_date ON scheduled_posts(user_id, scheduled_for);
```

---

## API Integrations Required

### 1. YouTube

**What we need:**
- New video notifications (RSS feeds)
- Video transcripts

**Approach:**
- **RSS:** `https://www.youtube.com/feeds/videos.xml?channel_id={id}` (no API key needed)
- **Transcripts:** No official API. Options:
  - `youtube-transcript-api` (Python library, scrapes HTML)
  - Supadata API ($29/mo for 10K requests)
  - Fallback: Download audio via `yt-dlp`, transcribe with Whisper

**Rate Limits:** RSS has no rate limits. Transcript scraping may be unstable.

**Mitigation:** Cache transcripts aggressively. If scraping fails, fallback to Whisper.

---

### 2. Podcast RSS Feeds

**What we need:**
- New episode notifications
- Episode audio or transcripts

**Approach:**
- **RSS:** Most podcasts publish standard RSS feeds (Apple Podcasts, Spotify, direct URLs)
- **Transcripts:** Some podcasts include `<podcast:transcript>` tags in RSS
- **Fallback:** Download audio, transcribe with Whisper API

**Rate Limits:** None for RSS fetching.

**Cost Estimate:** Whisper API at $0.006/minute. Average podcast = 60 minutes = $0.36 per episode. For 50 sources publishing weekly = $18/week = $72/month per user. **This is not sustainable.**

**Mitigation:**
- Prioritize podcasts with existing transcripts
- Limit free tier users to 10 sources
- Only transcribe episodes user explicitly requests
- Consider partnerships with podcast networks for transcript access

---

### 3. OpenAI API (GPT-4o / GPT-4o-mini)

**What we need:**
- Extract 2-3 shareable quotes per transcript
- Generate platform-specific captions
- Score quotes on shareability

**Approach:**
- Single prompt per transcript:
  ```
  Context: The user is [audience description] interested in [topics].
  Tone: [professional/casual/inspirational].
  
  From the following transcript, extract 3 shareable quotes (30-150 words each) that would resonate with this audience. For each quote:
  1. Extract the exact text
  2. Score shareability (0-10)
  3. Write a suggested caption
  4. Format for LinkedIn and X/Twitter
  
  Only return quotes scoring 7+.
  ```

**Cost Estimate:**
- GPT-4o: $5 per 1M input tokens, $15 per 1M output tokens
- Average transcript: 15K tokens input, 2K tokens output
- Cost per episode: $0.075 input + $0.03 output = **$0.11 per episode**
- For 50 sources, weekly episodes: 50 × $0.11 = **$5.50/week = $22/month per user**

**More manageable with GPT-4o-mini:** ~$0.02 per episode = $4/month per user.

**Mitigation:** Start with GPT-4o-mini, offer GPT-4o as "Pro" tier feature.

---

### 4. LinkedIn API (V2 Feature)

**What we need:**
- OAuth for user authentication
- Post creation (`POST /v2/ugcPosts`)

**Approach:**
- Request `w_member_social` scope
- User authorizes app via OAuth
- Store access token (expires after 60 days, requires refresh)

**Rate Limits:**
- 100 API calls per user per day
- Plenty for our use case (1-5 posts per day)

**Considerations:**
- LinkedIn API access requires app review (can take 2-4 weeks)
- Must comply with LinkedIn's API Terms (no spammy behavior)

**MVP Plan:** Skip for MVP. V2 feature only.

---

### 5. X/Twitter API (V2 Feature)

**What we need:**
- OAuth for user authentication
- Post creation (`POST /2/tweets`)

**Approach:**
- Request access to Twitter API (currently $100/month for Basic tier)
- User authorizes app via OAuth
- Create tweets via API

**Rate Limits:**
- 100 tweets per 24 hours per user (Basic tier)
- 1,500 tweets per 24 hours (Pro tier $5,000/month — not feasible for small SaaS)

**Considerations:**
- **Cost:** $100/month just for API access + per-user subscription cost
- **Feasibility:** Probably not worth it unless we charge $50+/month or have 100+ users to spread cost

**MVP Plan:** Skip entirely for MVP. Clipboard copy only. Reevaluate at scale.

---

## Roadblocks & Mitigations

### 1. Copyright & Fair Use Concerns

**Roadblock:** Sharing quotes from others' content — is this legal?

**Analysis:**
- **Fair Use Doctrine (US Law):** Allows limited use of copyrighted material for commentary, criticism, education, or news reporting.
- **Transformative Use:** Adding our own commentary or curating for a specific audience makes it more defensible.
- **Attribution:** Always link back to original source, include creator name and episode title.

**Best Practices:**
- Keep quotes short (30-150 words)
- Always attribute and link back
- Encourage users to add their own commentary (not just quote + caption)
- Include disclaimer in Terms of Service: "Users are responsible for ensuring their use of shared content complies with copyright law."

**Mitigation:**
- Launch with clear attribution features baked in
- Offer opt-out mechanism for creators who don't want their content shared
- Consult with IP lawyer before scaling

**Risk Level:** Medium. Unlikely to face legal issues if we're diligent about attribution, but could face pushback from creators.

---

### 2. YouTube Transcript Access Reliability

**Roadblock:** YouTube doesn't have an official transcript API. Scraping is brittle and could break.

**Options:**
1. **youtube-transcript-api (Python):** Free, scrapes HTML. Works today, could break tomorrow.
2. **Supadata API:** Third-party service, $29/mo for 10K requests. More stable but adds cost and dependency.
3. **Whisper API fallback:** Download audio via `yt-dlp`, transcribe. Slow and costly ($0.006/min).

**Mitigation:**
- Start with `youtube-transcript-api`
- Monitor error rates daily
- If error rate >10%, switch to Supadata or Whisper
- Cache transcripts aggressively (store in `episodes.transcript` column)
- Allow users to manually paste transcript if auto-fetch fails

**Risk Level:** High. This is a critical dependency with no perfect solution.

---

### 3. AI Cost at Scale

**Roadblock:** Processing 50 sources per user with OpenAI API gets expensive fast.

**Cost Breakdown (per user per month):**
- Whisper transcription: $72/month (if all 50 sources need transcription)
- GPT-4o snippet extraction: $22/month
- **Total: $94/month per user**

If we charge $29/month, we're losing money.

**Mitigation:**
1. **Prioritize existing transcripts:** Only use Whisper as fallback → reduces cost to ~$30/month per user
2. **Use GPT-4o-mini:** Reduces extraction cost to $4/month per user → total: $34/month per user
3. **Tiered limits:**
   - Free tier: 5 sources, no transcription (existing transcripts only)
   - Basic ($29/mo): 20 sources, 10 transcriptions/month
   - Pro ($59/mo): 50 sources, unlimited transcriptions
4. **Batch processing:** Process all new episodes once daily (not real-time) to optimize API calls

**With mitigations:** Cost per user on Basic tier = ~$10-15/month. Acceptable unit economics.

**Risk Level:** High. Must monitor costs closely and adjust pricing or limits quickly.

---

### 4. Social Media API Restrictions

**Roadblock:** LinkedIn and X/Twitter APIs have access restrictions, costs, and rate limits.

**LinkedIn:**
- Requires app review (2-4 weeks)
- Must demonstrate legitimate use case
- Risk of denial if they view us as "automation tool"

**X/Twitter:**
- Requires $100/month minimum for API access
- Not economically feasible unless we have 100+ paying users
- Could price us out of direct posting feature

**Mitigation:**
- **MVP:** Clipboard copy only. No direct posting. 80% of value is in the curation, not the posting.
- **V2:** Apply for LinkedIn API access, skip Twitter API entirely unless we hit scale.
- **Alternative:** Partner with existing social management tools (Buffer, Hootsuite) via their APIs — but adds complexity.

**Risk Level:** Medium. Not a blocker for MVP, but limits V2 features.

---

### 5. Content Quality & User Trust

**Roadblock:** AI-generated snippets might be generic, off-brand, or low-quality. Users won't share content that makes them look bad.

**Mitigation:**
1. **High shareability threshold:** Only show snippets scoring 7/10+
2. **Edit before sharing:** Always allow user to edit before posting (never auto-post without review)
3. **Learn user preferences:** Track which snippets user actually posts. Adjust extraction to match their style over time.
4. **Manual curation option:** Allow users to mark specific episodes to prioritize or ignore
5. **Feedback loop:** "Was this snippet helpful?" → thumbs up/down → improve AI prompts

**Risk Level:** Medium. Can mitigate with good UX and iteration, but quality is subjective.

---

### 6. Onboarding Friction

**Roadblock:** Asking users to add 5-10 sources and configure feeds might be too much work upfront. Users might bounce before seeing value.

**Mitigation:**
1. **Faster onboarding:**
   - "What topics do you care about?" → suggest popular sources automatically
   - "Choose 3 to start" → pre-populate with top podcasts/channels in their niche
2. **Demo mode:** Show sample snippets immediately so users see value before adding sources
3. **Progressive onboarding:** Let users skip setup and explore → prompt to add sources after they browse
4. **Templates:** "Start with the 'Tech Startup Founder' pack" → pre-configured feed + 10 sources

**Risk Level:** High for conversion. Good onboarding is critical.

---

### 7. Platform Risk: What if Podcasts or YouTube Change Policies?

**Roadblock:** YouTube could block transcript scraping. Podcasts could adopt DRM. Platforms could update ToS to ban third-party curation tools.

**Mitigation:**
- **Diversify sources:** Don't rely 100% on YouTube or podcasts. Add blog RSS support early.
- **User-owned content:** Emphasize that users are sharing with attribution, not stealing.
- **Pivot plan:** If one platform blocks us, focus on others. Core value (AI-powered curation) is platform-agnostic.

**Risk Level:** Medium. Out of our control, but not likely in near term.

---

## Business Model & Pricing

### Pricing Tiers

| Tier | Price | Features | Target User |
|------|-------|----------|-------------|
| **Free** | $0 | • 5 sources<br>• 1 feed<br>• 10 snippets/week<br>• Clipboard copy only | Casual users, trial |
| **Basic** | $29/mo | • 20 sources<br>• 3 feeds<br>• Unlimited snippets<br>• Scheduling<br>• Email digest | Solo entrepreneurs |
| **Pro** | $59/mo | • 50 sources<br>• Unlimited feeds<br>• Priority AI (GPT-4o)<br>• LinkedIn posting (V2)<br>• Analytics (V2) | Power users, agencies |
| **Team** | $99/mo | • Everything in Pro<br>• 3 team seats<br>• Shared feeds<br>• Approval workflows (V2) | Small agencies, teams |

### Early Access Pricing

- **First 100 users:** $19/mo for Basic (50% off forever)
- **Rationale:** Validate product-market fit, get testimonials, build community

### Revenue Projections (Optimistic)

**Month 1-3 (MVP Launch):**
- 100 early access users @ $19/mo = **$1,900 MRR**

**Month 4-6 (Public Launch):**
- 50 new Basic @ $29/mo = $1,450
- 20 new Pro @ $59/mo = $1,180
- Total: **$4,530 MRR** (with early access users: $6,430 MRR)

**Month 7-12 (Growth):**
- 200 Basic @ $29/mo = $5,800
- 50 Pro @ $59/mo = $2,950
- 5 Team @ $99/mo = $495
- Total: **$9,245 MRR**

**Goal:** $10K MRR within 6-9 months.

### Unit Economics (Basic Tier @ $29/mo)

**Costs per user per month:**
- AI processing (GPT-4o-mini): $4
- Whisper transcription (limited): $6
- Supabase hosting: $1
- Total COGS: **$11/user/month**

**Gross margin:** 62%

**Break-even:** ~350 users to cover $10K/mo in fixed costs (founder salary, tools, marketing).

---

## Success Metrics

### North Star Metric
**Daily Active Snippet Sharers (DASS):** Number of users who share at least 1 snippet per day.

### Key Metrics by Phase

**MVP (First 3 Months):**
- 100 sign-ups
- 50 active users (used product 3+ times per week)
- 20 paying users ($19 early access)
- 5+ testimonials / case studies
- **Target:** 30% activation rate (sign-up → active user)

**Growth (Months 4-6):**
- 500 sign-ups
- 200 active users
- 100 paying users
- $6K MRR
- 3-5 snippets shared per user per week
- **Target:** $10 CAC or less

**Scale (Months 7-12):**
- 2,000 sign-ups
- 800 active users
- 300 paying users
- $10K MRR
- 10+ snippets shared per user per week
- NPS score of 40+

### Key Performance Indicators (KPIs)

| Metric | Target (Month 3) | Target (Month 6) | Target (Month 12) |
|--------|------------------|------------------|-------------------|
| Sign-ups | 100 | 500 | 2,000 |
| Activation rate | 30% | 40% | 50% |
| Paying users | 20 | 100 | 300 |
| MRR | $1,900 | $6K | $10K |
| Churn rate | <10% | <5% | <5% |
| Avg snippets shared per user per week | 3 | 5 | 10 |
| NPS | 30+ | 40+ | 50+ |

---

## 4-Week MVP Build Plan

### Week 1: Core Infrastructure

**Goal:** Get the basic app structure running with auth and database.

**Tasks:**
1. **Day 1-2: Project Setup**
   - Initialize Next.js project with TypeScript and Tailwind
   - Set up Supabase project (database, auth)
   - Create database schema (users, feeds, sources, episodes, snippets tables)
   - Set up GitHub repo, deploy to Vercel

2. **Day 3-4: Authentication & Onboarding**
   - Implement Supabase auth (email + password)
   - Build sign-up/login pages
   - Create onboarding flow:
     - Step 1: "Create your first feed"
     - Step 2: "Add 3-5 sources"
     - Step 3: "We're processing your sources..."
   - Save user data to database

3. **Day 5-7: Source Management UI**
   - Build "Add Source" form (YouTube channel or podcast RSS URL)
   - Validate URLs, store in database
   - Build "My Sources" page (list, edit, delete)
   - Basic error handling

**Deliverable:** Users can sign up, create a feed, and add sources.

---

### Week 2: Content Ingestion & Processing

**Goal:** Fetch new content from sources and store in database.

**Tasks:**
1. **Day 8-9: YouTube RSS Monitoring**
   - Write Supabase Edge Function: `/api/monitor-youtube`
   - Fetch YouTube RSS feeds for all active sources
   - Parse XML, extract new videos since last check
   - Save new episodes to `episodes` table
   - Set up daily cron job to run this function

2. **Day 10-11: YouTube Transcript Fetching**
   - Integrate `youtube-transcript-api` (Python) or Supadata API
   - Write function: `fetchYouTubeTranscript(videoId)`
   - Save transcript to `episodes.transcript`
   - Handle errors gracefully (log and skip if transcript unavailable)

3. **Day 12-13: Podcast RSS Monitoring**
   - Write Supabase Edge Function: `/api/monitor-podcasts`
   - Fetch podcast RSS feeds
   - Parse XML, extract new episodes
   - Check for `<podcast:transcript>` tag, download if available
   - If no transcript, download audio and queue for Whisper transcription (deprioritize for MVP)

4. **Day 14: Testing & Debugging**
   - Test with 5-10 real YouTube channels and podcasts
   - Verify data is correctly saved to database
   - Check error handling

**Deliverable:** System automatically monitors sources and fetches transcripts daily.

---

### Week 3: AI Snippet Extraction & Feed View

**Goal:** Extract snippets with AI and display them in the feed.

**Tasks:**
1. **Day 15-16: AI Snippet Extraction**
   - Write Supabase Edge Function: `/api/extract-snippets`
   - For each new episode with transcript:
     - Call OpenAI API with prompt (see "API Integrations" section)
     - Parse response, extract 2-3 quotes
     - Score each quote, keep only 7+
     - Save to `snippets` table with `formatted_posts` JSON (LinkedIn, X formatting)
   - Set up cron job to run after monitoring functions

2. **Day 17-18: Feed View UI**
   - Build "Daily Feed" page (list of snippets)
   - Display snippet cards:
     - Quote text
     - Source attribution (name, episode, link)
     - Suggested caption
     - Buttons: "Copy for LinkedIn", "Copy for X", "Dismiss"
   - Implement filter by feed (Business, Personal, etc.)
   - Implement "Copy to clipboard" functionality

3. **Day 19-20: Snippet Detail & Edit Modal**
   - Clicking a snippet opens modal with:
     - Full quote + context
     - Platform-specific previews (LinkedIn vs X formatting)
     - Editable text area
     - "Copy" or "Save edits" buttons
   - Mark snippet as "used" when copied

4. **Day 21: Polish & Testing**
   - Test with real users (Andy + 2-3 friends)
   - Fix bugs, improve UX
   - Add loading states, error messages

**Deliverable:** Users can view and copy AI-extracted snippets.

---

### Week 4: Scheduling & Launch Prep

**Goal:** Add basic scheduling feature, polish UI, prepare for launch.

**Tasks:**
1. **Day 22-23: Scheduling Feature**
   - Build "Schedule Post" modal:
     - Date + time picker
     - Platform selector (LinkedIn, X, etc.)
     - "Add to queue" button
   - Save to `scheduled_posts` table
   - Build "Scheduled Posts" calendar view
   - Allow users to edit or delete scheduled posts

2. **Day 24-25: Email Digest**
   - Write Supabase Edge Function: `/api/send-digest`
   - Query new snippets since last digest
   - Format as HTML email
   - Send via Supabase (or integrate SendGrid/Resend)
   - Allow users to set digest time in settings

3. **Day 26-27: UI Polish & Testing**
   - Refine design (Tailwind styling, responsive layout)
   - Add empty states ("No snippets yet — check back tomorrow!")
   - Add tutorial tooltips for first-time users
   - Test on mobile (PWA experience)
   - Performance optimization (lazy loading, caching)

4. **Day 28: Launch Prep**
   - Write landing page copy
   - Set up Stripe (or Lemon Squeezy) for payments
   - Create "Early Access" sign-up flow
   - Soft launch to personal network (Twitter, LinkedIn, ProductHunt teaser)

**Deliverable:** MVP is live, users can sign up and pay.

---

## Risk Register

| Risk | Probability | Impact | Mitigation | Owner |
|------|-------------|--------|------------|-------|
| YouTube transcript scraping breaks | High | High | Use Supadata API as fallback, cache aggressively | Eng |
| AI costs exceed revenue | Medium | High | Implement tiered limits, optimize prompts, use GPT-4o-mini | Ops |
| Users find snippets low-quality | Medium | High | High shareability threshold (7+), allow editing, feedback loop | Product |
| Slow onboarding (users bounce) | High | Medium | Faster onboarding, demo mode, pre-populate sources | Product |
| LinkedIn API rejected | Medium | Medium | Launch with clipboard copy only, apply early, have backup plan | Eng |
| Legal issues with copyright | Low | High | Clear attribution, consult IP lawyer, opt-out mechanism | Legal |
| Platform changes block us (YouTube, podcasts) | Low | High | Diversify sources, pivot plan | Strategy |
| Not enough early users | Medium | Medium | Launch on ProductHunt, Twitter, leverage personal network | Marketing |

---

## Open Questions

1. **Product Name:** "Distill", "Clipper", "ContentFeed", something else? Need to check domain availability and trademark.

2. **Free tier or not?** Free tier drives growth but increases costs. Alternative: 14-day trial, then paid only.

3. **Which AI model for MVP?** GPT-4o-mini is cheaper but might produce lower-quality snippets. Test both and compare.

4. **Should we support Instagram?** Instagram doesn't allow text-only posts (requires image). Adds complexity. Punt to V2?

5. **How do we handle multiple languages?** If a user follows Spanish podcasts, do we translate snippets or assume user is bilingual? Localization strategy TBD.

6. **Do we need video clips (not just text)?** Some users might want short video clips to post (like OpusClip). Big feature, probably V3.

7. **Should we build native mobile apps?** PWA is cheaper and faster for MVP, but native apps (iOS/Android) offer better UX. Revisit at $10K MRR.

8. **Partnerships with podcast networks?** Could we partner with podcast networks or YouTubers for official transcript access + revenue share? Long-term play.

9. **Community features?** Should users be able to see what others are sharing (public feed)? Could drive discovery, but privacy concerns.

10. **Enterprise tier?** Should we target agencies/brands who manage multiple social accounts? Different product, probably V3+.

---

## Next Steps

1. **Validate product name & domain:** Check availability, secure domain + Twitter/LinkedIn handles
2. **Build MVP (4 weeks):** Follow build plan above
3. **Soft launch to personal network:** Get 10-20 beta users, gather feedback
4. **Iterate based on feedback:** Focus on snippet quality and onboarding UX
5. **Public launch (Week 6):** ProductHunt, Twitter, LinkedIn, relevant subreddits
6. **Drive to 100 early access users:** $1,900 MRR
7. **Content marketing:** Write blog posts, create YouTube tutorials, engage in communities
8. **Apply for LinkedIn API access (Week 8):** Prepare for V2 direct posting feature
9. **Reach $10K MRR (6-9 months):** Scale user acquisition, optimize unit economics

---

**End of PRD**

*This document is a living artifact. Update as we learn and iterate.*
