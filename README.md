# wa2agent: read-only WhatsApp MCP for Claude, Codex and other AI agents

[wa2agent](https://wa2agent.link) gives your AI agent read-only access to the
WhatsApp chats you choose. It is a hosted WhatsApp MCP server: your agent
connects over MCP (or reads new messages by email), and you do not run
anything on your own computer.

This repo holds the agent skill that sets it up.

## How do I let Claude (or another agent) read my WhatsApp?

1. Create a vault at https://wa2agent.link and link WhatsApp from your phone,
   like adding WhatsApp Web.
2. Choose which chats to share: single groups and DMs, all groups, all DMs, or
   everything.
3. Connect your agent: add your vault's MCP address to Claude, Claude Code,
   Codex or any MCP client, or turn on email delivery to an inbox your agent
   already reads.

Your agent can then turn school, family and work groups into events, tasks,
follow-ups and a daily brief.

## How is this different from lharries/whatsapp-mcp and other free servers?

Self-hosted servers such as
[lharries/whatsapp-mcp](https://github.com/lharries/whatsapp-mcp) are a good
choice if you want full control and can keep a computer running, update the
bridge and repair it when it breaks. wa2agent runs the connection for you, so
your agent can read shared chats while your laptop is closed. It is also
read-only by design: your agent cannot send WhatsApp messages through it.

## Is it safe?

- **Read-only.** Your agent cannot send messages through wa2agent.
- **You choose the chats.** Change or revoke them anytime.
- **Encrypted storage.** Stored messages are encrypted with a key only your
  agent holds, so wa2agent can't read them. New messages pass through the
  service before they are encrypted, and the service handles chat names and
  message times so it can deliver them.
- **Short retention.** Selected text messages are kept for 30 days. Media files
  are not downloaded.
- **Prompt injection.** Anyone in a shared chat can write text your agent will
  read. The skill tells your agent to treat messages as source material, never
  as instructions, and read-only access means a tricked agent still cannot
  message your contacts.
- **WhatsApp account.** wa2agent connects as a linked device, the same way
  WhatsApp Web does. It is not an official WhatsApp product, and WhatsApp
  decides what it allows on linked devices.

Details: [privacy and storage](https://wa2agent.link/privacy).

## Other ways to connect WhatsApp to AI

Comparing options? [Awesome WhatsApp MCP](https://github.com/rosroyros/awesome-whatsapp-mcp) lists self-hosted servers, hosted services, the Business API and the free export route, with their risks. It also has a free skill that reads WhatsApp chat exports, no account needed.

## Install the skill

With the [skills](https://skills.sh) CLI:

```bash
npx skills add rosroyros/wa2agent-skills
```

Or copy `skills/wa2agent-whatsapp/` into your agent's skills folder, for
example `.claude/skills/` (Claude Code) or `.agents/skills/` (Codex).

Then ask your agent: "Connect my WhatsApp with wa2agent so you can read my
school and family groups."

Tested with fresh Claude Code and Codex agents: set up a vault, then read a
message and an export email in new sessions.

## Agent guides

- [Muse](https://wa2agent.link/connect/muse)
- [Instinct](https://wa2agent.link/connect/instinct)
- [Full setup guide](https://wa2agent.link/docs)

## About

wa2agent is invite-only for now; join the waitlist at
https://wa2agent.link/login. Questions: info@wa2agent.link.

Built and operated by Roy Rosenfeld. Built on open-source WhatsApp connection
tools, including wacli and whatsmeow.
