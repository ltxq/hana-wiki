# Frequently Asked Questions

## What should I do if Hana doesn't respond?

Ensure the channel has been enabled using `/setroomai`, and confirm that Hana has `View Channel`, `Send Messages`, and `Read Message History`. Supported languages are Thai, English, and Japanese.

---

## How do I create and interact with Custom NPCs?

Use `/npc create` in your desired channel and fill out the 3 fields (Name, Personality/Prompt, and Opening Greeting). After creation, members can talk to the NPC by:
1. **Replying directly** to the NPC's message.
2. Or **Mentioning the NPC's name** in the channel.

---

## What is the difference between the Server Secretary (`/hanacontext`) and Hana's AI room?

- **Server Secretary (`/hanacontext`)**: Acts as a dedicated information desk. It exclusively answers questions regarding server rules, announcements, roles, and channel directions. Strict prompt guardrails ensure it politely refuses off-topic casual chat.
- **Hana AI Room (`/setroomai`)**: Hana acts as a friendly high-school friend chatting about life, Splatoon, sweets, and everyday topics, completely free from server administrative duties.

---

## How do I use Text-to-Speech (TTS)?

Join a voice channel, then run `/tts` in the text channel you want read aloud. Hana will join your voice room and start reading incoming messages. Run `/leave` to disconnect her, or simply leave the room; Hana will automatically disconnect when the room is empty.

---

## Is my API Key safe with Hana?

Yes. Any Gemini or OpenRouter API key entered via `/hanacontext` or bot settings is encrypted using **AES-256-GCM** before being stored in the local database. Keys are never logged in system transcripts or shared publicly.

---

## Why does Hana ask clarifying questions instead of answering directly?

When messages are ambiguous, Hana reads recent conversation context. If the intent is still uncertain, she asks a brief clarifying question rather than hallucinating or making incorrect assumptions.

---

## Why did `/travelphoto` fail with Missing Permissions?

`/travelphoto` requires the `Embed Links` permission in Discord so the bot can display rich image embeds from Pexels.

---

## Does Hana remember cross-server conversations?

No, memory is server-isolated by default. You can explicitly enable cross-server memory sharing through your personal `/settingai` panel.

---

## Does Hana proactively tag members?

No, unsolicited proactive tagging was permanently removed to avoid disturbing members. Hana only replies when spoken to.

---

## Where can I get support?

Join the community and ask questions on [Hana Discord](https://discord.gg/qWbQEABAPA).
