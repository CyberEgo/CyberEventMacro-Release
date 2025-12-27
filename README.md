# CyberEvent Macro

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11-blue" alt="Platform">
  <img src="https://img.shields.io/badge/Framework-.NET%208.0-purple" alt="Framework">
  <img src="https://img.shields.io/github/v/release/CyberEgo/CyberEventMacro-Release" alt="Release">
</p>

A Windows automation tool that monitors Microsoft Teams events and triggers custom actions automatically. Perfect for streamlining your workflow during meetings, calls, and status changes.

## 📥 Download

Go to [**Releases**](https://github.com/CyberEgo/CyberEventMacro-Release/releases/latest) and download:
- **CyberEventMacro-x64.exe** - For 64-bit Windows (recommended for most systems)
- **CyberEventMacro-x86.exe** - For 32-bit Windows

> **Note:** This is a self-contained executable. No installation or .NET runtime required - just download and run!

## ✨ Features

### 🔍 Teams Event Monitoring
Automatically detects Microsoft Teams events in real-time:
- **Presence Changes**: Available, Busy, Do Not Disturb, Away, Be Right Back, Offline
- **Call Events**: Call started, Call ended
- **Meeting Events**: Meeting joined, Meeting left
- **Screen Sharing**: Started/stopped presenting
- **Microphone**: Muted/Unmuted detection
- **Camera**: Camera on/off detection
- **Messages**: New messages and @mentions

### ⚡ Automated Actions
When events are detected, execute powerful actions:

| Action Type | Description | Example |
|-------------|-------------|---------|
| **Run Application** | Launch any program or file | Open Spotify, Start a script |
| **Keyboard Hotkey** | Simulate key combinations | Ctrl+Shift+M, Win+D |
| **Shell Command** | Execute PowerShell/CMD commands | Mute volume, Control smart devices |
| **Play Sound** | Play audio notification | Alert sound on mentions |

### 🎨 Additional Features
- **Dark Theme UI** - Modern, eye-friendly interface
- **System Tray** - Runs quietly in background
- **Rule Templates** - Pre-configured common automations
- **Import/Export** - Share rules between machines
- **File Logging** - Debug and troubleshoot easily

## 🚀 Quick Start

1. **Download** the appropriate version from [Releases](https://github.com/CyberEgo/CyberEventMacro-Release/releases/latest)
2. **Run** `CyberEventMacro-x64.exe` (no installation needed)
3. **Start Monitoring** - Click the button in the header
4. **Add Rules** - Use templates or create custom rules

## 📋 Creating Rules

### Using Quick Templates
The app includes pre-built templates for common scenarios:
- 🔇 **Mute on Meeting** - Mute system volume when meeting starts
- 🔊 **Unmute on Meeting End** - Restore volume when meeting ends  
- 💡 **DND Lighting** - Trigger smart home actions on Do Not Disturb
- 🔔 **Sound on Mention** - Play alert when you're @mentioned
- 🚀 **Launch on Available** - Start an app when status becomes Available

### Custom Rules
1. Click **Add Rule**
2. Enter a **Name** for your rule
3. Select the **Event Type** (e.g., "Call Started")
4. Add one or more **Actions**:
   - Choose action type (Run File, Hotkey, Command, Sound)
   - Configure the action parameters
5. Click **Save**

### Example Rules

**Turn on "On Air" light when in a call:**
```
Event: Call Started
Action: Shell Command → curl http://192.168.1.100/api/light/on
```

**Mute Spotify during meetings:**
```
Event: Meeting Started  
Action: Keyboard Hotkey → Ctrl+Shift+P (Spotify pause)
```

**Lock workstation when going Away:**
```
Event: Presence Changed to Away
Action: Shell Command → rundll32.exe user32.dll,LockWorkStation
```

## ⚙️ Settings

| Setting | Description |
|---------|-------------|
| **Polling Interval** | How often to check for events (default: 1000ms) |
| **Teams Log Path** | Custom path to Teams logs (auto-detected) |
| **Start with Windows** | Launch app on system startup |
| **Minimize to Tray** | Hide to system tray when minimized |
| **Log Events** | Record events in the Event Log tab |
| **File Logging** | Write detailed logs to file for debugging |

## 🔧 How It Works

CyberEvent Macro monitors Microsoft Teams through multiple methods:

1. **Log File Monitoring** - Reads Teams log files for presence and call state changes
2. **UI Automation** - Uses Windows Accessibility APIs to detect mute/camera states
3. **Window Monitoring** - Tracks Teams window titles for additional context

The app supports both:
- **New Teams** (MSIX/Store version)
- **Classic Teams** (MSI installer version)

## 💡 Common Actions Library

The app includes a library of copy-paste ready actions:

**Audio Control:**
- Mute/Unmute system volume
- Set volume to specific level

**Display Control:**
- Turn off monitor
- Lock workstation
- Start screensaver

**Smart Home (HTTP):**
- Send GET/POST requests to IoT devices
- Control Philips Hue, Home Assistant, etc.

**System:**
- Show Windows notifications
- Run PowerShell scripts
- Toggle Focus Assist

## 📝 Requirements

- Windows 10 or Windows 11
- Microsoft Teams (New Teams or Classic)
- No admin rights required for basic usage

## 🐛 Troubleshooting

**App doesn't detect Teams events:**
1. Make sure Teams is running
2. Check the "Teams Status" indicator in the app header
3. Try setting a custom Teams log path in Settings
4. Enable File Logging and check the logs folder

**Rules not triggering:**
1. Verify the rule is enabled (toggle switch is ON)
2. Check the Event Log tab for detected events
3. Test the rule using the "Test" button

**App won't start:**
- Try running as Administrator
- Check Windows Defender/Antivirus isn't blocking it
- Ensure you downloaded the correct architecture (x64 vs x86)

## 📄 License

Copyright © 2025 CyberEgo. All rights reserved.

This is proprietary software. Unauthorized copying, modification, distribution, or use of this software is strictly prohibited.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/CyberEgo">CyberEgo</a>
</p>
