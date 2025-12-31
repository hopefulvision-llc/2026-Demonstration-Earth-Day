# Software Configuration Guide - Earth Day 2026 Event

Step-by-step instructions for installing and configuring all necessary software for the virtual event.

---

## 📋 Table of Contents

1. [OBS Studio Setup](#obs-studio-setup)
2. [YouTube Live Configuration](#youtube-live-configuration)
3. [Discord Server Setup](#discord-server-setup)
4. [Design Tools Setup](#design-tools-setup)
5. [Audio Production](#audio-production)
6. [Forms and Surveys](#forms-and-surveys)
7. [Website/Landing Page](#websitelanding-page)
8. [System Optimization](#system-optimization)

---

## 🎥 OBS Studio Setup

### Installation

#### Windows
1. Visit https://obsproject.com/
2. Click "Download OBS Studio"
3. Download the Windows installer
4. Run the installer
5. Follow installation wizard (accept defaults)
6. Launch OBS Studio

#### macOS
1. Visit https://obsproject.com/
2. Click "Download OBS Studio"
3. Download the macOS installer (.dmg)
4. Open the .dmg file
5. Drag OBS to Applications folder
6. Launch OBS from Applications
7. **Important**: Grant screen recording permissions in System Preferences → Security & Privacy → Privacy → Screen Recording

#### Linux
```bash
sudo apt install obs-studio
# or
sudo snap install obs-studio
```

### Initial Configuration Wizard

**On first launch:**
1. Click "Yes" to run Auto-Configuration Wizard
2. Select "Optimize for streaming, recording is secondary"
3. **Video Settings**:
   - Base Resolution: 1920x1080
   - FPS: 30
4. **Stream Information**:
   - Service: YouTube - RTMPS
   - Leave Stream Key blank for now
5. Click "Apply Settings"

### Manual Settings Configuration

**Settings → Output:**
```
Output Mode: Advanced
Streaming:
  - Audio Track: 1
  - Encoder: x264 (or NVENC if you have NVIDIA GPU)
  - Rate Control: CBR
  - Bitrate: 5000 Kbps (adjust based on your upload speed)
  - Keyframe Interval: 2
  - CPU Usage Preset: veryfast (or faster if CPU struggles)
  - Profile: high
  - Tune: (none)

Recording:
  - Type: Standard
  - Recording Path: [Choose location with 50GB+ free space]
  - Recording Format: mp4
  - Audio Track: 1
  - Encoder: Same as stream
```

**Settings → Video:**
```
Base (Canvas) Resolution: 1920x1080
Output (Scaled) Resolution: 1920x1080
Downscale Filter: Lanczos
Common FPS Values: 30
```

**Settings → Audio:**
```
Sample Rate: 48 kHz
Channels: Stereo

Desktop Audio Device: [Your system audio output]
Mic/Auxiliary Audio Device: [Your USB microphone]
```

**Settings → Stream:**
```
Service: YouTube - RTMPS
Server: Primary YouTube ingest server
Stream Key: [Will add later from YouTube Studio]
```

**Settings → Advanced:**
```
Process Priority: High
Renderer: Direct3D 11 (Windows) / Metal (macOS)
Color Format: NV12
Color Space: 709
Color Range: Partial

Stream Delay: Disabled (unless you need moderation delay)
Automatically Reconnect: Enabled
  - Retry Delay: 10 seconds
  - Maximum Retries: 20
```

### Scene Creation

#### Scene 1: Opening/Closing Ceremony
1. Click "+" in Scenes panel
2. Name: "Opening/Closing Ceremony"
3. Add Sources:
   - **Background**: Image (sacred geometry)
     - Right-click scene → Add → Image
     - Select sacred geometry image file
     - Transform → Stretch to screen
   - **Camera**: Video Capture Device
     - Right-click scene → Add → Video Capture Device
     - Select your webcam
     - Position: Centered, sized appropriately
   - **Lower Third**: Image or Text
     - Add → Image (if you have pre-made graphic)
     - OR Add → Text (for simple name display)
     - Position: Bottom third of screen
   - **Audio Visualization**: Audio Source (for 528 Hz tone)
     - Add → Media Source
     - Browse for 528Hz.mp3 file
     - Check "Loop"

#### Scene 2: Presentation Mode
1. Create new scene: "Presentation Mode"
2. Add Sources:
   - **Screen Capture**: Display Capture
     - Add → Display Capture
     - Select your display
     - Transform → Stretch to screen
   - **Camera**: Copy from Scene 1
     - In Sources, right-click camera from Scene 1
     - Select "Copy"
     - In Scene 2, right-click → Paste (Reference)
     - Position: Corner (small), 20% size
   - **Lower Third**: Copy from Scene 1
     - Update text for current segment

#### Scene 3: Full Screen Demo
1. Create new scene: "Full Screen Demo"
2. Add Sources:
   - **Screen Capture**: Display Capture (full screen)
   - **Camera (Optional)**: Small picture-in-picture
     - 10-15% size, corner position

#### Scene 4: Community Showcase
1. Create new scene: "Community Showcase"
2. Add Sources:
   - **Video Playback**: Media Source
     - For pre-recorded testimonials
     - Add → Media Source
     - Browse for video file
   - **Lower Third**: Presenter name/info

#### Scene 5: Transition Slide
1. Create new scene: "Transition Slide"
2. Add Sources:
   - **Background**: Sacred geometry animation
     - Add → Media Source
     - Load animation file (video or gif)
   - **Text**: "Next: [Segment Name]"
     - Add → Text
     - Style with readable font, centered

#### Scene 6: Technical Difficulties
1. Create new scene: "Technical Difficulties"
2. Add Sources:
   - **Background**: Calming image
   - **Text**: "Brief pause - returning shortly"
   - **Audio**: 528 Hz tone or soft music
     - Media Source, looping

### Audio Mixer Setup

**In Audio Mixer panel:**
1. **Mic/Aux (Your Microphone)**:
   - Target level: -20 to -10 dB (yellow zone)
   - Add Filters:
     - Right-click → Filters
     - Add → Noise Suppression (Speex or RNNoise)
     - Add → Noise Gate (Threshold: -40 dB)
     - Add → Compressor (Ratio: 3:1, Threshold: -20 dB)
     - Add → Gain (adjust if too quiet)

2. **Desktop Audio**:
   - Target level: -30 to -20 dB (green zone)
   - Lower than microphone (so voice is primary)

3. **528 Hz Tone (Media Source)**:
   - Target level: -20 to -10 dB (yellow zone)
   - Create separate audio track if desired

### Hotkeys Configuration

**Settings → Hotkeys:**
```
Start Streaming: F9
Stop Streaming: F10
Start Recording: F11
Stop Recording: F12

Switch to Scene:
  - Opening/Closing Ceremony: F1
  - Presentation Mode: F2
  - Full Screen Demo: F3
  - Community Showcase: F4
  - Transition Slide: F5
  - Technical Difficulties: F6

Mute/Unmute:
  - Mic/Aux: M
  - Desktop Audio: N
```

### Studio Mode (Optional)
- Enable Studio Mode (button at bottom right)
- Allows preview before switching scenes
- Useful for verifying scene looks correct before going live

---

## 📺 YouTube Live Configuration

### Enable Live Streaming

1. **Go to YouTube Studio**: https://studio.youtube.com/
2. **Navigate to Live Streaming**:
   - Click "Create" (top right)
   - Select "Go Live"
3. **Enable Live Streaming** (if not already enabled):
   - May require phone verification
   - Takes 24 hours to activate (do this early!)
4. **Choose "Stream" method** (not "Webcam")

### Create Scheduled Event

1. **In YouTube Studio → Live:**
   - Click "Schedule Stream"
2. **Event Details:**
   ```
   Title: Earth Day 2026: Sacred Technology Activation
   
   Description:
   Join us for a 4-hour virtual demonstration of consciousness-first technology on Earth Day 2026.
   
   🕐 Schedule:
   12:00-1:00 PM PT - Philosophy & Vision
   1:00-2:00 PM PT - Prototype Demonstrations
   2:00-3:00 PM PT - Community Showcase
   3:00-4:00 PM PT - Open Forum & Vision
   
   🔗 Links:
   Website: hopefulvision.llc
   Discord: [Your Discord invite]
   Beta Signups: [Links]
   
   📋 Timestamps:
   [Will be added during/after event]
   
   🎯 What You'll Experience:
   - Live demonstrations of sacred technology prototypes
   - Community member showcases
   - Q&A with Cosimos and team
   - Vision for consciousness-first computing
   
   #EarthDay2026 #SacredTechnology #ConsciousComputing #HopefulVision
   ```

3. **Schedule:**
   - Date: April 22, 2026
   - Time: 12:00 PM Pacific Time
   - Duration: 4 hours

4. **Visibility:** Public

5. **Category:** Science & Technology (or Education)

6. **Advanced Settings:**
   - Enable Live Chat: Yes
   - Age Restriction: No
   - Enable Auto-Start: No (manual start is safer)
   - Enable Auto-Stop: No
   - Enable DVR: Yes (allows viewers to rewind)
   - 360° Video: No
   - Enable Monetization: Your choice (likely No for this event)

### Get Stream Key

1. **In the stream setup:**
   - Click "Stream Settings"
   - Copy "Stream key"
2. **In OBS:**
   - Settings → Stream
   - Paste Stream Key
   - Click "Apply" and "OK"

### Configure Stream Quality

**YouTube Studio → Stream:**
```
Stream Latency: Normal (10-20 seconds)
  - Ultra-low latency not recommended for stability

Backup Stream: Optional
  - Can set up redundant stream for failover
  - Requires duplicate OBS setup
```

### Live Chat Moderation

1. **Add Moderators:**
   - YouTube Studio → Settings → Community
   - Add trusted community members as moderators

2. **Chat Settings:**
   - Enable/Disable:
     - Slow mode: 1-5 seconds (recommended)
     - Members-only chat: No
     - Emoji/stickers: Yes
   - Block words/phrases: Add inappropriate terms

---

## 💬 Discord Server Setup

### Create Server

1. **Open Discord**: https://discord.com/
2. **Create Server:**
   - Click "+" in server list
   - Select "Create My Own"
   - Choose "For a community"
   - Name: "HopefulVision - Earth Day 2026"
   - Upload server icon (HopefulVision logo)

### Server Settings

**Server Settings → Overview:**
```
Server Name: HopefulVision - Earth Day 2026
Server Icon: [Upload logo]
Server Banner: [Optional, requires boosted server]
Description: Community space for Earth Day 2026 Sacred Technology Demonstration
```

**Server Settings → Moderation:**
```
Verification Level: Medium (verified email)
Explicit Content Filter: Scan messages from all members
2FA Requirement: Recommended for moderators
```

**Server Settings → Roles:**

Create roles:
1. **@Admin**
   - All permissions
   - Color: Red
   - Assign to: Cosimos, core team

2. **@Moderator**
   - Manage Messages, Timeout Members, Kick Members
   - Color: Blue
   - Assign to: Trusted community members

3. **@Speaker**
   - Priority Speaker in voice channels
   - Color: Purple
   - Assign to: Guild presenters

4. **@Participant**
   - Default member role
   - Can read, send messages, join voice
   - Color: Green

5. **@New**
   - Limited role for unverified members
   - Can only see welcome and rules
   - Color: Gray

### Channel Structure

**Text Channels:**

**📢 ANNOUNCEMENTS**
- `#welcome` - Welcome message, server rules
- `#event-schedule` - Full 4-hour schedule
- `#tech-support` - Technical help during event

**💬 EARTH DAY EVENT**
- `#general-chat` - General discussion
- `#questions-for-qa` - Submit questions for Q&A session
- `#guild-discussions` - Talk about joining guilds

**📚 RESOURCES**
- `#links-and-resources` - Important links (read-only)
- `#beta-signups` - Links to beta access (read-only)
- `#earth-interface-interpretations` - Share glyph interpretations

**Voice Channels:**
- 🎙️ Community Audio 1
- 🎙️ Community Audio 2 (Overflow)
- 🎙️ Guild Discussions

### Welcome Message

In `#welcome`:
```
🙏 Welcome to HopefulVision - Earth Day 2026! 

This Discord server is our community space for the Earth Day 2026 Sacred Technology Activation event happening on **April 22, 2026, 12:00-4:00 PM Pacific Time**.

📺 **Where to Watch:**
YouTube Live: [Link]
Twitch Backup: [Link]

📋 **Server Rules:**
1. Treat all members with respect and kindness
2. No spam, harassment, or offensive content
3. Stay on topic in designated channels
4. Use #questions-for-qa for Q&A submissions
5. Follow Discord Terms of Service

🎯 **How to Participate:**
- Watch the YouTube live stream
- Chat here in Discord during event
- Submit questions in #questions-for-qa
- Join voice channels to discuss with others
- Share your thoughts and interpretations

💫 **After the Event:**
This server will remain active as our ongoing community space.

Namasté 🙏
```

### Bots Configuration

**MEE6 or Dyno (Moderation):**
1. Visit https://mee6.xyz/ or https://dyno.gg/
2. "Add to Discord"
3. Select your server
4. Configure:
   - Welcome messages
   - Auto-moderation rules
   - Logging (messages deleted, etc.)
   - Custom commands

**Poll Bot:**
1. Add Pollbot: https://pollbot.top/
2. Use for quick polls during event
3. Example: `/poll "Which prototype interested you most?" "Magnifier Bubble" "Whisper Agent" "Earth Interface"`

---

## 🎨 Design Tools Setup

### Canva Pro

1. **Sign Up**: https://www.canva.com/pro/
2. **Free Trial**: Start 30-day free trial
3. **Cost**: $13/month after trial

**What to Create:**

**Lower Thirds:**
1. In Canva, search "Lower Third" templates
2. Customize with:
   - Name: "Cosimos"
   - Title: "Founder, HopefulVision LLC"
   - Colors: Indigo, gold, green, violet
   - Transparent background (Canva Pro feature)
3. Download as PNG (transparent background)
4. Create multiple versions for different segments

**Transition Slides:**
1. Create 1920x1080 slides
2. Design with sacred geometry patterns
3. Text: "Next: [Segment Name]"
4. Export as PNG or short video (MP4)

**Social Media Graphics:**
1. Instagram Post (1080x1080)
2. Twitter Header (1500x500)
3. YouTube Thumbnail (1280x720)

---

## 🎵 Audio Production

### Audacity Setup

1. **Download**: https://www.audacityteam.org/
2. Install and launch

### Create 528 Hz Tone

1. **Generate Tone:**
   - Generate → Tone
   - Waveform: Sine
   - Frequency: 528 Hz
   - Amplitude: 0.8
   - Duration: 2 minutes (opening) or 90 seconds (closing)
2. **Apply Fade In/Out:**
   - Select first 2 seconds
   - Effect → Fade In
   - Select last 2 seconds
   - Effect → Fade Out
3. **Export:**
   - File → Export → Export as MP3
   - Name: "528Hz_Opening_2min.mp3"
   - Bitrate: 320 kbps

### Verify Audio Quality

- Play on different devices (computer, phone, headphones)
- Verify no distortion or clipping
- Ensure smooth fade in/out

---

## 📝 Forms and Surveys

### Google Forms Setup

1. **Create Form**: https://forms.google.com/
2. **Title**: "Earth Day 2026 - Q&A Submissions"
3. **Description**: 
   ```
   Submit your questions for the live Q&A session during the Earth Day 2026 event.
   Questions will be organized by category and answered during Hour 4 (3:00-4:00 PM PT).
   ```

4. **Questions:**
   - Name (Short answer, optional)
   - Email (Short answer, optional)
   - Discord Username (Short answer, optional)
   - **Question Category** (Multiple choice, required):
     - Technical
     - Philosophical
     - Practical
     - Partnership
     - Ethical
     - Other
   - Your Question (Paragraph, required)

5. **Settings:**
   - Limit to 1 response: No
   - Collect email addresses: Optional
   - Response receipts: If requested

6. **Responses:**
   - Link to Google Sheets for organization
   - Create columns: Timestamp | Name | Email | Discord | Category | Question | Priority | Status

---

## 🌐 Website/Landing Page

### Option 1: Carrd.co

1. **Sign Up**: https://carrd.co/
2. **Choose Plan**: Pro Standard ($19/year)
3. **Create Site:**
   - Choose "Landing" template
   - Customize with event information
4. **Sections:**
   - Hero: Event title, date, time
   - About: What is this event?
   - Schedule: 4-hour breakdown
   - How to Participate: Links to YouTube, Discord
   - Beta Signups: Links to signup forms
   - Contact: Social media links
5. **Domain:** Connect to earthday2026.hopefulvision.llc
6. **Publish**

### Option 2: WordPress Page

1. **Create New Page** in WordPress admin
2. **Use Page Builder** (Elementor, etc.) or blocks
3. **Add Sections:** Same as Carrd option above
4. **Publish** and share link

---

## 💻 System Optimization

### Windows

**Disable Unnecessary Startup Programs:**
1. Task Manager → Startup tab
2. Disable programs you don't need

**Power Settings:**
1. Settings → System → Power & Sleep
2. Set to "High Performance" mode
3. Prevent sleep during event

**Disable Notifications:**
1. Settings → System → Notifications & Actions
2. Turn off "Get notifications from apps and other senders"

**Disable Updates:**
1. Settings → Update & Security
2. Pause Updates for 7 days (day before event)

### macOS

**Disable Notifications:**
1. System Preferences → Notifications
2. Set "Do Not Disturb" schedule for event time
3. Or manually enable Do Not Disturb

**Prevent Sleep:**
1. System Preferences → Energy Saver
2. "Prevent computer from sleeping automatically when display is off"

**Disable Updates:**
1. System Preferences → Software Update
2. Uncheck "Automatically keep my Mac up to date"

### Both Platforms

**Close Unnecessary Apps:**
- Email clients
- Chat applications (except Discord)
- Cloud sync (Dropbox, Google Drive)
- Browser tabs not needed for stream

**Network Optimization:**
- Close apps using bandwidth
- Pause cloud backups
- Disable automatic updates

---

## ✅ Final Software Checklist

Week before event:
- [ ] All software installed and tested
- [ ] OBS scenes configured and tested
- [ ] YouTube event scheduled and stream key connected
- [ ] Discord server set up and populated
- [ ] Graphics created and imported to OBS
- [ ] Audio files created and tested
- [ ] Forms created and embedded on website
- [ ] Website/landing page published
- [ ] System optimization completed

Day before event:
- [ ] Final test of all software
- [ ] All software up to date (updated at least 24 hours before)
- [ ] No pending system updates
- [ ] All files backed up
- [ ] OBS profile saved and backed up

---

*With all software properly configured, you're ready to deliver a professional virtual event!* ✨
