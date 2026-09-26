# wa2agent skills

Agent skills for [wa2agent](https://wa2agent.link), which gives your AI agent
read-only access to the WhatsApp chats you choose.

## wa2agent-whatsapp

Teaches your agent to connect to wa2agent and read your shared WhatsApp chats:
school, family and work groups become events, tasks, follow-ups and a daily
brief.

- Read-only: your agent cannot send WhatsApp messages through it.
- You choose which chats to share and can change them anytime.
- Stored messages are encrypted with a key only your agent holds. wa2agent
  can't read them.
- Works over MCP, or with new messages delivered to your agent by email.

Tested with fresh Claude Code and Codex agents: set up a vault, then read a
message and an export email in new sessions.

## Install

With the [skills](https://skills.sh) CLI:

```bash
npx skills add rosroyros/wa2agent-skills
```

Or copy `skills/wa2agent-whatsapp/` into your agent's skills folder, for
example `.claude/skills/` (Claude Code) or `.agents/skills/` (Codex) in your
project.

Then ask your agent: "Connect my WhatsApp with wa2agent so you can read my
school and family groups."

## About

wa2agent is currently invite-only; without an invite you can join the waitlist
at https://wa2agent.link/login. Setup guide: https://wa2agent.link/docs.
Questions: info@wa2agent.link.

Built and operated by Roy Rosenfeld.
