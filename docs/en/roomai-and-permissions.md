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

1. Run `/hanacontext` (requires `Manage Guild` or Administrator permissions).
2. **1-Click Channel Selection (`ChannelSelectMenu`)**: Select the secretary's designated room directly from the dropdown menu without typing channel names or IDs.
3. Click **Setup Secretary / Edit Details** to open the modal:
   - **Secretary Name**: The display name used in responses (e.g. `Secretary Saki`, `Server Concierge`).
   - **Server Context**: Community guidelines, rules, role explanations, FAQs, and important links.
   - **API Key (Gemini or OpenRouter)**: Use the administrator's own API key. This ensures high throughput without consuming bot host shared quotas.
   - **AI Model**: Choose your preferred AI model.
4. Save the configuration. The Secretary is immediately activated in that room!

### Strict Server-Only Boundary Guardrail

The Server Secretary is engineered with strict prompt guardrails:
- **Exclusively Server Topics**: Answers only questions concerning server guidelines, rules, roles, announcements, and channel directories.
- **Graceful Off-Topic Refusal**: When asked off-topic questions, casual chat, weather, or jokes, the Secretary politely declines and directs members to server matters or Hana's casual room (`/setroomai`).

### Context Management & Reset
Inside `/hanacontext`, administrators can:
- Clear server context or rules.
- Reset the Secretary setup.
- Verify API key connection status.

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
