# Server Owner Guide & Secretary Desk

This guide covers setting up Hana AI chat rooms, configuring the Dedicated Server Secretary Desk via `/hanacontext`, and granting the required Discord permissions.

---

## 1. Hana AI Chat Rooms (`/setroomai`)

Commands for server managers to open or close casual Hana AI chat channels:

| Command | Purpose | Required Permissions |
| :--- | :--- | :--- |
| `/setroomai` | Enable Hana AI in the current channel | `Manage Channels` |
| `/unsetroomai` | Disable Hana AI in the current channel | `Manage Channels` |
| `/guildbook` | Open the interactive guide in Discord | Everyone |

> **Note:** In AI rooms, Hana acts purely as a cheerful high-school student who loves Splatoon, Japanese culture, and casual chatter. She is decoupled from administrative server rules.

---

## 2. Dedicated Server Secretary Desk (`/hanacontext`)

The `/hanacontext` command sets up a **Dedicated Server Secretary** responsible for answering server inquiries, navigating channels, explaining server roles, and clarifying community rules.

### Setup Instructions

1. Run `/hanacontext` (requires `Manage Guild` or Administrator permissions) and click **Set up secretary / Update desk**.
2. **Pick the room** from the `ChannelSelectMenu` — no channel names or IDs to type.
3. **Pick the model from the menu** — just press one of the ready-made options (Gemini 3.1 Flash Lite recommended, Gemini 2.5 Flash/Pro, or OpenRouter models). You never have to type a provider/model string.
4. The final modal only asks for the **Secretary Name** (e.g. `Secretary Saki`), an optional **avatar URL**, and the **opening greeting**.
5. Save. The Secretary is immediately activated in that room.

> API keys are no longer entered during secretary setup. Add the server's central keys once with `/admin`; the secretary uses them automatically. Server context (rules and info) is configured with the separate buttons in `/hanacontext`.

### Strict Server-Only Boundary Guardrail

The Server Secretary is engineered with strict prompt guardrails:
- **Exclusively Server Topics**: Answers only questions concerning server guidelines, rules, roles, announcements, and channel directories.
- **Graceful Off-Topic Refusal**: When asked off-topic questions, casual chat, weather, or jokes, the Secretary politely declines and directs members to server matters or Hana's casual room (`/setroomai`).
- **Always Answers in Your Language**: The Secretary replies in Thai, English, or Japanese depending on how you write to it, including the off-topic refusal itself.

### Conversation Memory

The Secretary remembers up to 12 turns of your conversation (kept separately per server and per member), so you can ask a follow-up without repeating the topic, for example "and which channel is that?". This history is deleted automatically after six hours without use.

### Context Management & Reset
Inside `/hanacontext`, administrators can:
- Clear server context or rules.
- Reset the Secretary setup.
- Check the server central API key status in `/admin`.

---

## 3. Recommended Discord Permissions

Hana does not require full Administrator privileges. You can grant only the necessary permissions:

| Permission | Purpose |
| :--- | :--- |
| `View Channel` | View text channels and voice rooms |
| `Send Messages` | Reply to chat messages |
| `Read Message History` | Read previous message context |
| `Embed Links` | Send rich embeds (essential for `/travelphoto`, profile cards, and guides) |
| `Attach Files` | Attach travel photos |
| `Use Application Commands` | Allow slash commands |
| `Manage Webhooks` | **Required for NPCs** (`/npc`) to create and send webhook messages |
| `Connect` & `Speak` | **Required for TTS** (`/tts`) to join voice and read messages |
| `Send Messages in Threads` | Respond inside active threads |

---

## 4. Troubleshooting

1. **Hana does not reply in chat**:
   - Check if `/setroomai` was activated in the channel.
   - Confirm Hana has `View Channel`, `Send Messages`, and `Read Message History`.
   - Check channel permission overrides for explicit role denies.
2. **Server Secretary does not respond**:
   - Verify that the designated channel was selected in `/hanacontext`.
   - Confirm that the administrator's API key (Gemini/OpenRouter) has valid quota.
3. **NPCs do not reply**:
   - Ensure the bot has `Manage Webhooks` in that channel.
   - Confirm users are **Replying** directly to the NPC message or mentioning the NPC's name.
4. **Photos do not appear in `/travelphoto`**:
   - Verify that `Embed Links` is enabled for Hana in that channel.
