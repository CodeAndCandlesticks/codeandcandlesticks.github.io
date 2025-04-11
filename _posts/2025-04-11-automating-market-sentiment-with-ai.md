---
layout: post
title: "Automating Market Sentiment with AI: How I Use Claude and GPT to Size My Trades"
date: 2025-04-11
categories: [trading, ai, automation]
tags: [AI, trading bot, Claude, GPT, automation, sentiment]
---

Every morning before the market opens, I like to check in with Schwab’s **Market Open Update** — their daily summary of macro conditions, economic data, and big-picture sentiment.

But let’s be honest: most days, I don’t want to read another macro recap.

So I built a script.

## Why I Built It

As a systematic trader and developer, I look for ways to simplify edge detection and automate the decision-making process. I’m particularly interested in how **market tone** affects my position sizing — whether I should go in heavy, stay light, or skip the day entirely.

Rather than relying on my own mood while reading the headlines, I decided to let a large language model do the reading and decide:  
**Is the sentiment today bullish, bearish, or mixed?**

## How It Works

The script pulls the latest update from Schwab’s site and feeds it to a language model — either **Claude 3.5 Sonnet** from Anthropic or **GPT-4** from OpenAI.

From there, it distills the article into one word:  
**Bullish**, **Bearish**, or **Mixed**.

That value is logged in a `.csv`-style file (`market_sentiment.log`) alongside the date and the model used. The log gets referenced by my trading bot, which adjusts **entry size and aggression** based on that day’s sentiment.

Here’s an actual log output from today:

```
date,sentiment,model
2025-04-11,Mixed,anthropic,claude-3-5-sonnet-20241022
```

Simple. Reliable. Non-emotional.

## Why Use AI for This?

Language models are particularly good at tasks like:
- Summarizing macro narratives
- Detecting optimism or caution in tone
- Cutting through jargon and filler to highlight risk sentiment

It turns out that what I was doing manually — skimming a few paragraphs and making a gut call — is exactly the kind of repetitive judgment task that AI can handle well.

Soon, I won't make sizing decisions based on "how I feel about the open." I'll let the model read it, log it, and move on.

## Want to Try It?

If you're curious to see it in action or want to integrate it into your own workflow, you can **clone the full repo from GitHub**. It's lightweight, local, and easy to plug into any script-based system.

👉 **[GitHub Repo: Market Sentiment Logger](https://github.com/CodeAndCandlesticks/market-sentiment)**

---

In a future post, I’ll show how I use this sentiment signal as a core input in my **trading bot's engine**, and explain how it dynamically adjusts entry size and aggressiveness based on the broader market tone.

Until then, feel free to fork, tweak, or use it as-is — and keep your decision-making clean and data-backed.
