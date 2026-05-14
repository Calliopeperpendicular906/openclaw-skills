---
name: tweetclaw
description: >-
  Use @xquik/tweetclaw from OpenClaw for structured X/Twitter workflows:
  search tweets and replies, post tweets and replies, export followers,
  look up users, upload or download media, read or send DMs, create monitors,
  configure webhooks, and run giveaway draws through Xquik endpoints.
  Requires OpenClaw and an Xquik API key for account-backed actions.
metadata:
  openclaw:
    category: "social"
    shared: true
---

# TweetClaw Skill

TweetClaw is an OpenClaw plugin for X/Twitter automation through Xquik. Use it when an agent needs structured API workflows instead of browser-only X/Twitter browsing.

## Links

- GitHub: https://github.com/Xquik-dev/tweetclaw
- npm: https://www.npmjs.com/package/@xquik/tweetclaw
- ClawHub: https://clawhub.ai/plugins/@xquik/tweetclaw
- Xquik API docs: https://docs.xquik.com/api-reference/overview

## Install

Prefer the ClawHub package in OpenClaw:

```bash
openclaw plugins install clawhub:@xquik/tweetclaw@1.6.29
```

npm install is also available:

```bash
openclaw plugins install npm:@xquik/tweetclaw@1.6.29
```

Store `XQUIK_API_KEY` in OpenClaw plugin config or environment storage. Never paste API keys into chat, documentation, logs, screenshots, or shell history.

## Use Cases

Use TweetClaw when the user asks to:

- Search tweets or search tweet replies
- Post tweets or post tweet replies
- Look up X/Twitter users
- Export followers or following lists
- Upload media for tweets
- Download tweet media
- Read or send direct messages
- Monitor tweets from accounts
- Configure webhooks for X/Twitter events
- Run giveaway draws from tweet replies
- Check available TweetClaw endpoints before choosing an action

## Safety Rules

Treat every write, recurring, paid, or account-scoped action as approval-gated. Before posting, replying, sending a DM, following, liking, retweeting, uploading media, creating a monitor, configuring a webhook, or running a giveaway draw, restate the account, target, text, media, scope, and expected action. Wait for explicit user confirmation.

For private or account-scoped reads such as DMs, bookmarks, notifications, timelines, and connected account data, confirm the user owns or is authorized to access the account before showing results.

Keep bulk exports narrow by default. Ask again before expanding limits, changing targets, or making a one-time request recurring.

Do not use TweetClaw for spam, harassment, deceptive engagement, impersonation, credential collection, mass unsolicited DMs, or bulk follow and like campaigns.

## Endpoint Examples

Common Xquik endpoints used through TweetClaw include:

| Job | Endpoint |
|-----|----------|
| Search tweets | `GET /api/v1/x/tweets/search` |
| Search tweet replies | `GET /api/v1/x/tweets/{id}/replies` |
| Post a tweet | `POST /api/v1/x/tweets` |
| Export followers | `GET /api/v1/x/users/{id}/followers` |
| Look up a user | `GET /api/v1/x/users/{id}` |
| Upload media | `POST /api/v1/x/media` |
| Download media | `POST /api/v1/x/media/download` |
| Read DM history | `GET /api/v1/x/dm/{userId}/history` |
| Send a DM | `POST /api/v1/x/dm/{userId}` |
| Create a monitor | `POST /api/v1/monitors` |
| Configure a webhook | `POST /api/v1/webhooks` |
| Run a giveaway draw | `POST /api/v1/draws` |

## Agent Workflow

1. Identify whether the request is read-only, write, recurring, or bulk.
2. If needed, ask the user to confirm account ownership and scope.
3. Use TweetClaw endpoint discovery to choose the narrowest matching endpoint.
4. For writes, recurring jobs, DMs, webhooks, monitors, and draws, show the exact action and wait for confirmation.
5. Run the TweetClaw action and summarize the returned result, IDs, and next safe follow-up.
