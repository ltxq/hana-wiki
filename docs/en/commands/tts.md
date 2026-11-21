# Text-to-Speech (TTS)

Hana's Text-to-Speech (TTS) feature allows the bot to join your voice channel and read text messages aloud in real time.

---

## Commands

| Command | Description | Availability |
| :--- | :--- | :--- |
| `/tts` | Makes Hana join the voice channel you are currently in and binds it to read messages from this text channel | Available to everyone |
| `/leave` | Makes Hana disconnect from the voice channel immediately | Available to everyone |

---

## Key Features & Sanitization

### 1. Intelligent Text Cleansing
To ensure pleasant and uninterrupted listening, Hana cleans incoming messages before reading:
- **Mention Stripping**: User mentions (`<@123456789>`) and role mentions (`<@&987654321>`) are stripped rather than reading raw IDs.
- **Channel Mentions**: Channel links (`<#channel>`) are omitted.
- **URL Filtering**: Web links starting with `http://` or `https://` are ignored to prevent long noisy URL reading.
- **Custom Emojis**: Formats like `<:smile:12345>` are spoken simply as `smile`.

### 2. 1.5s Anti-Spam Cooldown
A 1.5-second cooldown buffer ensures sentences finish gracefully and prevents voice audio stuttering or overlapping when users type rapidly.

### 3. Automatic Disconnect (Auto-Leave)
When all members leave the voice channel, Hana automatically detects the empty room and leaves to preserve bandwidth and resources.

---

## Required Discord Permissions

For Hana to connect and speak in voice channels, ensure the bot has:
- `Connect`
- `Speak`
