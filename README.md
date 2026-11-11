# ClickRuntime plugin for Cursor

Build and run automations that connect your apps, from Cursor. Describe what should happen and when. Cursor's agent writes a Python script, deploys and tests it, and ClickRuntime runs it on a schedule or when a webhook arrives, calling any app with an API.

ClickRuntime builds and runs automations from your AI assistant. Describe what should happen, when, and where the result should go. The assistant writes the automation as a Python script, deploys it to ClickRuntime, runs a test and fixes errors until a run succeeds. ClickRuntime then runs it on its own servers after the chat ends.

Use it when the person wants work to keep happening without them:
- Connect apps: when something happens in one app, update others. For example, a form submission becomes a row in Airtable and a Slack message.
- Run on a schedule: every few minutes, hourly, daily, or at set times such as weekdays at 9am in a chosen time zone.
- React to webhooks from Stripe, Shopify, GitHub, Tally, Typeform or any service that can send one.
- Call any app or API, including internal APIs, web pages and RSS feeds. Slack, Google Sheets, Gmail and Calendar connect with sign-in; other apps use a key saved in the ClickRuntime dashboard.
- Run multi-step logic in code: fetch, filter, branch, transform, and write to several apps in one run.
- Use a built-in AI model to classify, summarize or extract from text, with no AI key.
- Keep state between runs, to handle only new items, alert only on change or keep running totals.

Each automation is managed from the chat: check runs, get a failed run explained and fixed, change, pause or delete it. Scripts run in isolated runners. Keys are encrypted, write-only and masked in logs, and never pass through the chat. Every run is logged, and failures send an email alert.

It does not move money, place trades or make purchases, and it is not needed for reminders that only appear in the chat.

Example automations:
- When a Tally form is submitted, classify the message as spam or not with AI and add a row to Airtable.
- When a Stripe payment succeeds, add a row to a Google Sheet and post the amount to Slack.
- When a Shopify order arrives, look up the customer in HubSpot, tag VIPs and notify the team.
- Every hour, check a pricing page and email me only if the price changed.
- Every morning, summarize new GitHub issues I have not seen and send a digest to Slack.
- Label each new support email as billing, bug or other, and post the billing ones to Slack.

This plugin adds ClickRuntime's skills to Cursor and connects the ClickRuntime MCP server at `https://clickruntime.com/api/mcp`. The skills tell Cursor's agent how to draft an automation, set up its connections, then deploy it, test it and fix it until a run succeeds. Cursor asks your permission before each tool call; you connect accounts and add keys yourself.

## Setup

**From the Cursor Marketplace**

Install ClickRuntime from the Marketplace in Cursor. Then open Cursor Settings → MCP, select Connect next to `clickruntime`, and sign in to ClickRuntime in the browser window that opens.

**MCP server only**

Select Add to Cursor at https://clickruntime.com/assistants/cursor, or open this link in a browser on the machine where Cursor is installed:

```text
cursor://anysphere.cursor-deeplink/mcp/install?name=clickruntime&config=eyJ1cmwiOiJodHRwczovL2NsaWNrcnVudGltZS5jb20vYXBpL21jcCJ9
```

Or add this to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "clickruntime": {
      "url": "https://clickruntime.com/api/mcp"
    }
  }
}
```

Then select Connect next to `clickruntime` in Cursor's MCP settings and sign in. Sign-in uses OAuth; there is no API key to copy.

Documentation, including setup for every assistant: https://clickruntime.com/docs

## What it can do

- Build automations that connect apps and sync data between them
- Run automations on a schedule or when a webhook arrives
- Call any app or API, with keys stored outside the chat
- Classify, summarize or extract text with built-in AI
- Keep state between runs for new-item handling and change alerts
- Test, fix, pause and monitor automations from the chat

## Example prompts

- "When my form gets a submission, classify it as spam or not and add it to Airtable."
- "When a Stripe payment succeeds, add a row to my sheet and post it to Slack."
- "Every hour, check my competitor's pricing page and email me if they change their price."

## Privacy Policy

ClickRuntime receives only the tool requests Cursor sends it, such as a draft automation or a request to list runs. It does not receive or store your conversations or your code. Saved keys are encrypted and are never returned to Cursor. Read the full policy at https://clickruntime.com/privacy.

## Support

Help and contact: https://clickruntime.com/support or hello@clickruntime.com. Terms: https://clickruntime.com/terms.

## License

MIT. See [LICENSE](LICENSE).
