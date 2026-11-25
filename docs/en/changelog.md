# Changelog

## HanaBot v1.5.2 — 25 November 2026

- **⚙️ Command cleanup (beta)**:
  - `/settingai` was renamed to **`/settings`**; the language picker is now on the **first page**, and the "view memory" button was removed because memory is short-term.
  - `/premium` was removed — every feature is free during beta. Premium lock text and links were also removed from `/statusai`, `/hanainsights` and the secretary desk.
  - Removed "(ฟรี)" from command descriptions.
  - `/statusai` now shows only the essentials: Japanese time, current activity, location, weather, outfit, mood, health, interest and today's event. Personality, summary, energy, Discord status and university calendar were dropped.
  - Fixed a display bug where some panels showed raw keys such as `common.status:` and `settings.memory.title:` instead of translated text.
  - Secretary setup now has a **model picker menu** (no provider/model typing) and no API key field — set the server keys once in `/admin`.
  - Gemini 503 errors now show a short Thai "system is busy, try again in a moment" message instead of raw error JSON (secretary, NPCs and RoomAI).
- **🎭 `/npc` is now a single button panel**:
  - The five subcommands (`create` / `list` / `move` / `edit` / `delete`) were merged into one `/npc` command that opens an easy button hub, like the secretary desk.
  - Create, filter (all / mine), pick a character from a select menu, change its model, edit its profile/keys/channel, and delete it — all without typing IDs or command names.
  - The whole panel renders in Thai / English / Japanese, and clearing a character's key now really falls back to the server vault.
- **🔒 Memory is now scoped per server**:
  - Memory and relationship state are kept per **Discord User ID + Server ID**, so a conversation in one server does not bleed into another.
  - Older global memory is kept aside in state; the old move button disappeared together with the memory panel.
  - Memory summarisation jobs are keyed per user and server, so one server can no longer overwrite another.
- **🌐 The settings panels follow your language**:
  - The language picker is on the **first page of `/settings`** (Thai / English / Japanese, or automatic based on what you chat in).
  - The settings, memory, personal data, and profile panels all render in the language you chose.
- **🔑 Per-feature API keys**:
  - The server secretary can now take its own API key through the `sec_keys` field in the setup form (leave it empty to use the server's central keys).
  - An NPC can take its own key from the **Set API key** button in the NPC management panel.
  - The NPC panel is split across two button rows so both the per-NPC key and the central vault are reachable.
- **Documentation and policy updates**: the privacy policy now describes the per-server memory scoping to match the code.

---

## HanaBot v1.5.1 — 25 November 2026

- **Three-language support (Thai / English / Japanese)**:
  - Moved UI and settings-panel text into `locales/` so each language can be edited independently.
  - AI quota and queue-full messages now reply in the user's own language instead of always Thai.
  - The server secretary's off-topic refusal is written **in the speaker's language** instead of always Thai.
  - Japanese is now supported in memory retrieval and Splatoon lookups.
  - `/travelphoto` autocomplete matches Japanese, Thai, and English prefecture names.
- **NPCs and the secretary now remember conversations**:
  - An NPC keeps up to 12 turns of your conversation (separately per character and per user) instead of forgetting every reply.
  - The server secretary does the same, so you can ask a follow-up without repeating the topic.
- **Bug fixes**:
  - The drawing prompt in `/hanagame` now actually calls the AI, and **counts against your quota** correctly. That code path was dead and never ran.
  - Removed dead files that no code used (GIF cache, Private AI database, backup modules).
- **Documentation and policy updates**:
  - Privacy Policy and Terms of Service rewritten to match the features that actually exist (dropping the removed Private AI and `/dmpanel` sections).
  - Now states clearly that **memory is shared across servers (per User ID)** while **relationship state is scoped per server**, matching the code.
  - Added coverage of NPCs, the server secretary, and the `/admin` command to the guide.

---

## HanaBot v1.5.0 — November 2026

- **Custom Roleplay NPCs (`/npc`)**:
  - Replaced legacy Private AI with the new Discord Webhook NPC architecture.
  - Streamlined 3-field modal creation (`/npc create`): Name, Personality/System Prompt, and Opening Greeting.
  - Realistic webhook speech with custom avatar and display name for each character.
  - Natural multi-turn interaction via **Direct Reply** to NPC messages or **Name Mentions**.
  - Complete lifecycle commands: `/npc list`, `/npc move`, `/npc edit`, `/npc delete`.
  - Independent API keys (Gemini / OpenRouter) with key rotation, preventing bot host quota exhaustion.
- **Dedicated Server Secretary Desk (`/hanacontext`)**:
  - Clean separation between server administration and Hana's casual persona.
  - 1-click room assignment using Discord `ChannelSelectMenu`.
  - Modal setup for Secretary Name, Server Context rules, and Administrator API keys.
  - **Strict Server-Only Boundary Guardrail**: Enforces strict focus on server guidelines, roles, announcements, and navigation, while gracefully redirecting off-topic casual chat.
- **Decoupled Hana Roleplay**:
  - Hana in `/setroomai` chat rooms stays focused on her cheerful high-school persona without server rule clutter.
- **Text-to-Speech (TTS) Voice System**:
  - Added `/tts` to bind Hana into voice channels for real-time chat narration, and `/leave` to disconnect.
  - Automatic message sanitization: strips user mentions, role mentions, channel tags, and URLs for seamless audio.
  - 1.5s anti-spam cooldown buffer to prevent audio stutter and overlapping.
  - Automatic disconnection when the voice channel becomes empty.

---

## HanaBot v1.4.1 (beta) — September 28, 2026

- Migrated to local SQLite database storage with AES-256-GCM encryption for stored API keys and rolling backups.
- Removed proactive unsolicited tags to minimize member disruption.
- Improved contextual history reading for ambiguous user messages.
- Prevented unverified photo attachment claims.
- Added `/travelphoto` and User Install/DM support.
- Added new actions: `shrug`, `welcome`, `givegift`, `fistbump`, and `dance`.
- Live remote Anime GIF fetching for every `/act` and `/actwith`.

---

Follow latest news and join the discussion on [Hana Discord](https://discord.gg/qWbQEABAPA).
