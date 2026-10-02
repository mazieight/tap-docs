# 🎤 OneTab Discord Voice Bot

Professional Discord bot for creating temporary voice channels with modern UI/UX and automatic management.

## ✨ Features

- **🎤 Temporary Voice Channels**: Users join "Join to Create" to get their own voice room
- **🗑️ Auto-Delete**: Channels are automatically deleted when empty
- **👑 Owner Control**: Only bot owner can set up the system
- **📁 Per-Server Data**: Each guild has its own JSON data structure
- **🎨 Professional UI**: Modern embeds and user experience
- **⚡ Fast & Reliable**: Built with discord.py for optimal performance

## 🚀 Quick Start

1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Configure Bot**:
   - Edit `.env` file with your bot token
   - Your Discord ID is already set as owner: `[IDENTIFIER REDACTED]`

3. **Run Bot**:
   ```bash
   python src/bot.py
   ```

4. **Setup Server**:
   - Use `.t setup` command in your Discord server
   - Only you (bot owner) can run this command

## 🔧 Commands

### Basic Commands
- `.t setup` - Set up voice system (Owner only)
- `.t info` - Display bot information

### Owner Management
- `.t addowner @user` - Add room owner
- `.t addadmin @user` - Add room admin
- `.t listowner` - List all owners

### Bot Profile Customization
- `.t setbotavatar <file/url>` - Change bot's Discord avatar
- `.t setbotbanner <file/url>` - Change bot's Discord banner
- `.t setavatar <file/url>` - Set room embed avatar
- `.t setbanner <file/url>` - Set room embed banner

### Voice Control
- `.t join <channel>` - Connect bot to voice channel
- `.t leave` - Disconnect bot from voice

### Special Features
- `.t ice <category>` - Get icebreaker questions
- `.t setstatus <channel> <status>` - Set channel status

## 📁 Project Structure

```
OneTab-Discord-Bot/
├── src/
│   ├── commands/
│   │   └── setup.py          # Setup command
│   ├── events/
│   │   ├── on_ready.py       # Bot ready event
│   │   ├── on_guild_join.py  # Auto-setup for new guilds
│   │   └── voice_state_update.py  # Voice channel management
│   ├── utils/
│   │   ├── database.py       # JSON database handler
│   │   └── embeds.py         # Professional embed builder
│   └── bot.py               # Main bot file
├── assets/
│   ├── avatars/             # Bot avatar files
│   └── banners/             # Bot banner files
├── data/
│   └── guilds.json          # Per-guild data storage
├── requirements.txt         # Python dependencies
├── .env                     # Bot configuration
└── README.md               # This file
```

## 🛡️ Permissions Required

- **Manage Channels** - Create/delete voice channels
- **Move Members** - Move users to new channels
- **Connect** - Access voice channels

## 📊 How It Works

1. **Setup**: Owner runs `.t setup` to create category and "Join to Create" channel
2. **Create**: User joins "Join to Create" → Bot creates personal voice room
3. **Manage**: Channel owner gets full permissions (manage, mute, move, etc.)
4. **Cleanup**: When channel becomes empty → Bot automatically deletes it

## 🔒 Security

- Only bot owner (ID: [IDENTIFIER REDACTED]) can run setup commands
- Each guild has isolated data storage
- Automatic cleanup prevents channel spam

## 💾 Database Structure

```json
{
  "guild_id": {
    "setup_complete": true,
    "category_id": 123456789,
    "join_to_create_id": 987654321,
    "active_channels": [
      {
        "channel_id": 111222333,
        "owner_id": 444555666
      }
    ],
    "settings": {
      "category_name": "🎤 Voice Rooms",
      "join_channel_name": "➕ Join to Create",
      "auto_delete": true,
      "channel_limit": 99
    }
  }
}
```

## 🎯 Bot Owner

- **Discord ID**: [IDENTIFIER REDACTED]
- **Commands**: All setup and management commands
- **Access**: Cross-server administrative control

---

**OneTab Voice Bot** - Professional Discord voice channel management system.
