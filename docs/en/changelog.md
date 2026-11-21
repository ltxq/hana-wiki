# Changelog

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
