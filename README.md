# TikTok Ads MCP Starter Kit — Manage TikTok Ads with AI

[![MCP Compatible](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform: TikTok Ads](https://img.shields.io/badge/Platform-TikTok%20Ads-000000)](https://ads.tiktok.com)

**Reach the most engaged audience on the internet with short-form video ads.** Open this repo in Amp, Cursor, or VS Code and manage TikTok ad campaigns with AI — create Spark Ads, target Gen Z and Millennials, and optimize for conversions on a platform where creative is everything.

---

## Why TikTok Ads + AI?

TikTok has 1.5 billion monthly active users spending an average of 95 minutes per day on the app. No other platform commands that level of attention. The algorithm is so good at surfacing relevant content that users don't just scroll — they watch, engage, and buy.

The catch: TikTok creative is fundamentally different from every other platform. Polished, branded content underperforms. The ads that win look like organic TikToks — authentic, creator-style, shot on a phone. The first 3 seconds determine everything. If you don't hook immediately, users swipe.

Managing TikTok Ads also means navigating a complex API with quirks: pixel_id vs pixel_code confusion, platform-specific optimization events (SHOPPING not Purchase), and bid price fields that change based on billing type.

An AI agent handles the API complexity while you focus on what matters — great creative.

**Best for:** Gen Z and Millennial products, ecommerce (especially fashion, beauty, gadgets), app installs, entertainment, D2C brands that can produce UGC-style video.

---

## Quick Start (30 Seconds)

### Amp / Cursor / VS Code (Copilot)

1. **Get a free API key** at [syntermedia.ai/developer](https://syntermedia.ai/developer)
2. **Set the key:**
   ```bash
   export SYNTER_API_KEY=syn_your_key_here
   ```
3. **Open this repo** in your editor
4. **Start chatting** — MCP tools are pre-configured in `.mcp.json`

### Claude Desktop

Copy `claude_desktop_config.json` to your Claude config directory and replace the API key:

- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

---

## What You Can Do

| Capability | Example |
|-----------|---------|
| **Create In-Feed Campaigns** | "Launch a TikTok campaign for our skincare brand targeting 18-34 women" |
| **Spark Ads** | "Turn our viral organic TikTok into a Spark Ad" |
| **Pixel Management** | "Set up the TikTok Pixel with Purchase and AddToCart events" |
| **Interest Targeting** | "Target people interested in fitness, healthy eating, and workout routines" |
| **Ad Group Optimization** | "Optimize for CompletePayment with a $15 target CPA" |
| **Creative Analysis** | "Which video ads have the highest 2-second view rate?" |
| **Budget Management** | "Scale winning ad groups by 20% daily" |
| **Audience Building** | "Create a Custom Audience from website visitors in the last 30 days" |
| **Event Testing** | "Send a test conversion event to verify my pixel is working" |
| **Campaign Reports** | "Show me cost per purchase by ad group for the last 7 days" |

---

## Example Conversations

### 1. First TikTok Campaign for an Ecommerce Brand

> **You:** I sell wireless earbuds. I want to try TikTok Ads. Budget is $100/day.
>
> **Agent:** TikTok is excellent for consumer electronics — the platform loves unboxing, review, and "found this on TikTok" content.
>
> Here's my plan:
>
> **Campaign structure:**
> - **Objective:** Website Conversions (optimize for Purchase)
> - **Budget:** $100/day at the campaign level
> - **Pixel:** I'll set up a TikTok Pixel with Purchase, AddToCart, and ViewContent events
>
> **Ad Group 1 — Interest targeting:**
> - Interests: Technology, Consumer Electronics, Music
> - Age: 18-34
> - Optimization event: CompletePayment (TikTok's enum for Purchase)
> - Bid strategy: Lowest Cost (let TikTok find the cheapest conversions)
>
> **Ad Group 2 — Broad targeting:**
> - No interest targeting (TikTok's algorithm finds buyers)
> - Age: 18-44
> - Same optimization
>
> **Creative guidance:**
> - UGC-style review video (person talking to camera, showing earbuds)
> - Unboxing video with reaction
> - "POV: you find earbuds that actually stay in during workouts"
> - **Critical:** First 3 seconds must hook. Lead with the product benefit, not the logo.
>
> **You:** I have 3 videos from TikTok creators. Can I use those?
>
> **Agent:** Perfect — creator content outperforms brand content 2-3x on TikTok. If you have authorization from the creators, I can set these up as **Spark Ads**, which run from the creator's account. This keeps the organic engagement (likes, comments, shares) and adds a CTA button. Best of both worlds.

### 2. Understanding TikTok's Pixel Quirks

> **You:** I set up the TikTok Pixel but my ad groups say "No optimization events available." What's wrong?
>
> **Agent:** This is a common TikTok quirk. The TikTok API requires your pixel to have **received at least one real event** for each event type before it becomes available for ad group optimization.
>
> Let me check your pixel status...
>
> **Findings:**
> - ✅ `PageView` — 1,247 events (working)
> - ✅ `ViewContent` — 89 events (working)
> - ❌ `AddToCart` — 0 events (not available for optimization)
> - ❌ `CompletePayment` — 0 events (not available for optimization)
>
> Your pixel is installed but `AddToCart` and `CompletePayment` events aren't firing. Either:
> 1. The event code isn't on your checkout/cart pages, or
> 2. No one has added to cart since the pixel was installed
>
> **Quick fix:** I'll send a test event through TikTok's Events API to prime each event type. This registers the event with TikTok so it becomes available for optimization. You'll still need to fix the actual pixel implementation, but this unblocks your campaign launch.
>
> Want me to prime the events now?

### 3. Creative Performance Analysis

> **You:** I have 8 video ads running. Which ones should I keep?
>
> **Agent:** Pulling creative-level metrics for the last 7 days...
>
> | Video | 2s View Rate | 6s View Rate | CTR | CPA | Spend |
> |---|---|---|---|---|---|
> | "POV: Morning Routine" | 68% | 41% | 2.1% | $12.30 | $340 |
> | "Creator Review (Sarah)" | 72% | 48% | 3.4% | $8.90 | $520 |
> | "Unboxing Reaction" | 55% | 29% | 1.8% | $18.40 | $280 |
> | "Product Features" | 31% | 14% | 0.6% | $45.20 | $190 |
> | "Before/After Skin" | 64% | 38% | 2.8% | $11.50 | $410 |
> | "ASMR Unboxing" | 78% | 52% | 1.2% | $14.20 | $310 |
> | "Side-by-Side Compare" | 43% | 22% | 1.4% | $24.60 | $240 |
> | "Street Interviews" | 61% | 35% | 2.5% | $13.80 | $380 |
>
> **Analysis:**
>
> 🏆 **Keep & scale:** "Creator Review (Sarah)" — best CPA ($8.90), highest 6-second view rate (48%), and strongest CTR (3.4%). This is your winner.
>
> ✅ **Keep:** "Before/After Skin" and "POV: Morning Routine" — strong CPAs under $13.
>
> ⚠️ **Test more:** "ASMR Unboxing" has the best hook (78% 2s view) but lower CTR — the hook grabs attention but doesn't drive clicks. Try adding a stronger CTA at the end.
>
> ❌ **Kill:** "Product Features" (31% 2s view = people swipe immediately), "Side-by-Side Compare" ($24.60 CPA). The polished "Product Features" video proves the rule: TikTok punishes corporate-looking content.

### 4. Scaling Winners Without Breaking Performance

> **You:** My best ad group is averaging $10 CPA at $50/day. How do I scale without ruining performance?
>
> **Agent:** TikTok's algorithm is sensitive to sudden budget changes. The rule: **increase budget by no more than 20% per day.** Larger jumps reset the learning phase.
>
> Here's a 2-week scaling plan:
>
> | Day | Daily Budget | Expected CPA |
> |---|---|---|
> | 1-2 | $50 (current) | $10 |
> | 3-4 | $60 (+20%) | $10-12 |
> | 5-6 | $72 (+20%) | $10-12 |
> | 7-8 | $86 (+20%) | $11-13 |
> | 9-10 | $103 (+20%) | $11-14 |
> | 11-14 | $125 (+20%) | $12-15 |
>
> At each step, let it run 48 hours before increasing again. If CPA rises above $15, pause the increase for 3 days.
>
> **Parallel scaling strategy:** Don't just scale the budget — duplicate the winning ad group with different targeting:
> 1. Original: Interest targeting (current winner)
> 2. Duplicate A: Broad targeting (let algorithm find buyers)
> 3. Duplicate B: Lookalike audience based on pixel purchases
>
> This distributes spend across multiple ad groups and reduces the risk of a single ad group hitting audience saturation.

### 5. Spark Ads vs Regular Ads

> **You:** What's a Spark Ad and why should I use it?
>
> **Agent:** Spark Ads are TikTok's most powerful ad format. Instead of creating a new ad post, you promote an **existing organic TikTok** — either from your own account or a creator's account (with their permission).
>
> **Why Spark Ads win:**
>
> | Feature | Regular Ad | Spark Ad |
> |---|---|---|
> | Engagement persists | ❌ (ad engagement disappears) | ✅ (likes, comments stay forever) |
> | Profile link | ❌ | ✅ (drives profile visits + follows) |
> | Duet/Stitch | ❌ | ✅ (users can interact with your ad) |
> | Authenticity | Low (looks like an ad) | High (looks organic) |
> | Avg CPA | Baseline | 30-50% lower |
>
> **How to set up a Spark Ad:**
> 1. Creator generates an "authorization code" in their TikTok app (Settings → Creator Tools → Spark Ads)
> 2. You give me the code, and I link the video to your ad account
> 3. I create a campaign using that video as the creative
> 4. All engagement (views, likes, comments) stays on the creator's original post
>
> This is why TikTok creator partnerships are so valuable. One viral creator video as a Spark Ad can outperform 10 studio-produced ads.

---

## TikTok Ads Tips from the Pros

1. **First 3 seconds are everything.** 50% of ad impact happens in the first 3 seconds. Lead with the hook — "I can't believe this actually works" beats a logo animation every time.
2. **UGC outperforms polished creative.** Content shot on a phone by a real person outperforms studio-produced ads 2-3x. If it looks too professional, TikTok users swipe past it.
3. **Use Spark Ads whenever possible.** Promoting organic content (yours or creators') feels more authentic and typically delivers 30-50% lower CPAs.
4. **TikTok's pixel uses pixel_code AND pixel_id.** The pixel_code (alphanumeric) is for the dashboard. The API needs the numeric pixel_id. The Synter agent auto-resolves between them.
5. **Optimization events have different names than you'd expect.** TikTok uses `SHOPPING` (not Purchase), `ON_WEB_CART` (not AddToCart), `FORM` (not SubmitForm). The agent handles this mapping.
6. **Scale budgets by 20% max per day.** Larger jumps reset TikTok's learning phase. Patience beats aggression.
7. **Vertical video only.** 9:16 aspect ratio. Horizontal or square video performs terribly on TikTok. Fill the entire screen.

---

## FAQ

### Is there an MCP for TikTok Ads?
Yes — this repo. It pre-configures the Synter MCP server for TikTok Ads management. Works with Amp, Cursor, VS Code, and Claude Desktop.

### Can AI create TikTok video ads?
The agent can help with creative strategy, script writing, and managing campaigns. For AI video generation, use the [ai-creative-agent](https://github.com/Synter-Media-AI/ai-creative-agent) which integrates with Veo, Runway, and Luma for video creation.

### What's the minimum budget for TikTok Ads?
$20/day minimum per ad group. But $50-100/day is recommended to exit TikTok's learning phase (which requires ~50 conversions per week). At a $15 CPA, that's $107/day.

### Do TikTok Ads work for B2B?
TikTok skews younger (18-34), so traditional B2B is harder. However, SMB tools, developer products, and startup-focused B2B products can work well. The key is adapting your content to TikTok's style — no talking heads in suits.

### What's the difference between Spark Ads and regular In-Feed Ads?
Spark Ads promote existing organic TikTok videos (from your account or creators). Regular In-Feed Ads are standalone ad posts. Spark Ads feel more authentic, keep engagement metrics, and typically cost 30-50% less.

### How do I track conversions from TikTok?
Install the TikTok Pixel on your website and set up events (Purchase, AddToCart, etc.). For better attribution, also set up the TikTok Events API (server-side). The agent can help configure both.

---

## Related Repos

- [meta-ads-agent](https://github.com/Synter-Media-AI/meta-ads-agent) — Facebook & Instagram (also strong for visual products)
- [ai-creative-agent](https://github.com/Synter-Media-AI/ai-creative-agent) — AI video generation for ads
- [shopify-agent](https://github.com/Synter-Media-AI/shopify-agent) — Sync Shopify products for TikTok Shop
- [conversion-tracking-agent](https://github.com/Synter-Media-AI/conversion-tracking-agent) — Pixel & Events API setup
- [audience-sync-agent](https://github.com/Synter-Media-AI/audience-sync-agent) — Sync customer lists to TikTok
- [cross-platform-ads-agent](https://github.com/Synter-Media-AI/cross-platform-ads-agent) — Multi-channel management

---

## License

MIT — see [LICENSE](LICENSE) for details.

Built by [Synter](https://syntermedia.ai) · [Get API Key](https://syntermedia.ai/developer) · [Documentation](https://syntermedia.ai/docs)
