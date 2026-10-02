# 🎤 Voice Commands Documentation

## Overview
The OneTab Discord Bot now includes 24/7 voice connection commands that allow the bot owner to connect to voice channels and maintain a persistent presence.

## Owner-Only Commands

### `.t vjoin` or `.t vj`
**Description:** Join a voice channel and maintain 24/7 connection

**Usage:**
- `.t vjoin` - Join the voice channel you're currently in
- `.t vjoin [channel name]` - Join a specific voice channel by name

**Examples:**
```
.t vjoin
.t vjoin General
.t vjoin Music Room
.t vjoin Study Hall
```

**Features:**
- ✅ Automatic reconnection if disconnected
- ✅ Channel name matching (exact and partial)
- ✅ Move between channels seamlessly
- ✅ Real-time member count display
- ✅ Professional embed responses

### `.t vleave` or `.t vl`
**Description:** Disconnect from current voice channel

**Usage:**
- `.t vleave` - Leave the current voice channel

**Example:**
```
.t vleave
```

### `.t vstatus` or `.t vs`
**Description:** Check current voice connection status

**Usage:**
- `.t vstatus` - Display detailed connection information

**Example:**
```
.t vstatus
```

**Status Information:**
- 🔊 Current channel
- 👥 Connected users count
- 🤖 Connected bots count
- 🌐 Server information
- 🔍 Connection quality and latency
- 📋 List of active users

## Requirements

### Discord Permissions
The bot needs the following permissions:
- `Connect` - To join voice channels
- `Speak` - To maintain voice connection
- `View Channel` - To see available voice channels

### Python Dependencies
```
discord.py[voice]>=2.3.0
PyNaCl>=1.5.0
```

## Security Features

### Owner-Only Access
- Only the bot owner (ID: [IDENTIFIER REDACTED]) can use these commands
- All other users receive access denied messages
- Secure decorator implementation prevents bypass

### Error Handling
- Professional error messages for all scenarios
- Graceful handling of connection failures
- Automatic reconnection attempts
- Safe disconnection procedures

## Technical Features

### 24/7 Connection Maintenance
- Background task monitors connection every 30 seconds
- Automatic reconnection if unexpectedly disconnected
- Persistent connection state tracking
- Clean disconnection handling

### Smart Channel Finding
- Exact name matching first
- Partial name matching as fallback
- Case-insensitive searching
- Clear error messages with available channels list

### Professional UI/UX
- Rich embed responses for all commands
- Color-coded messages (success=green, error=red, info=blue)
- User avatar integration in embeds
- Timestamp tracking for all actions
- Member count and status indicators

## Voice State Monitoring

The bot includes a voice state listener that:
- Detects when the bot is disconnected
- Resets connection variables appropriately
- Logs disconnection events
- Prepares for clean reconnection

## Example Workflow

1. **Join Voice Channel:**
   ```
   User: .t vjoin Music Room
   Bot: ✅ Successfully joined Music Room! Status: Connected 24/7
   ```

2. **Check Status:**
   ```
   User: .t vstatus
   Bot: 📊 Connected to Music Room with 5 users online
   ```

3. **Move Channels:**
   ```
   User: .t vjoin General
   Bot: 🎤 Successfully moved to General!
   ```

4. **Disconnect:**
   ```
   User: .t vleave
   Bot: 🔇 Successfully left General. Status: Disconnected
   ```

## Error Scenarios

### Not in Voice Channel
```
User: .t vjoin
Bot: ❌ You must be in a voice channel or specify a channel name.
```

### Channel Not Found
```
User: .t vjoin NonExistentChannel
Bot: ❌ Voice channel 'NonExistentChannel' not found.
Available channels: • General • Music Room • Study Hall
```

### Already Connected
```
User: .t vjoin General (when already in General)
Bot: 🎤 I'm already connected to General!
```

### Connection Failed
```
Bot: ❌ Failed to connect to Music Room. Error: [detailed error]
Please check bot permissions and try again.
```

---

**Note:** These commands are designed for bot owners who need persistent voice presence for moderation, music bots, or community management purposes.
