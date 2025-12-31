# Network and Connectivity Guide - Earth Day 2026 Event

Comprehensive guide for ensuring stable internet connectivity during the 4-hour live stream event.

---

## 📡 Internet Requirements

### Minimum Requirements

**Upload Speed:**
- **Absolute Minimum**: 10 Mbps
- **Recommended**: 15-20 Mbps
- **Ideal**: 25+ Mbps

**Download Speed:**
- Less critical for streaming
- 5 Mbps minimum for chat/Discord monitoring

**Latency:**
- <50ms preferred
- <100ms acceptable

**Stability:**
- More important than raw speed
- Consistent connection better than fast but unstable

### Bandwidth Calculation

**For 1080p30 Stream:**
```
Video bitrate: 5000 Kbps (5 Mbps)
Audio bitrate: 160 Kbps (0.16 Mbps)
Overhead: ~20% (1 Mbps)
─────────────────────────────────
Total needed: ~6.2 Mbps upload

Recommended buffer: 2x = 12.4 Mbps
Safe target: 15 Mbps upload speed
```

---

## 🧪 Testing Your Connection

### Speed Tests (Run Multiple Times)

**Test Sites:**
1. **Speedtest.net** (Primary): https://www.speedtest.net/
2. **Fast.com** (Netflix): https://fast.com/
3. **Google Speed Test**: Search "speed test" on Google

**When to Test:**
- Test at the same time of day as your event
- Test on multiple days
- Test different days of the week
- Document all results

**What to Record:**
```
Date: _______________
Time: _______________
Download Speed: _______ Mbps
Upload Speed: _______ Mbps
Ping/Latency: _______ ms
Jitter: _______ ms
Connection Type: Ethernet / WiFi (circle one)
```

### Stress Testing

**OBS Test Stream:**
1. Schedule unlisted YouTube stream
2. Stream for 30-60 minutes
3. Monitor OBS stats (View → Stats):
   - Dropped Frames: Should be <1%
   - CPU usage: Should be <80%
   - Rendering lag: Should be minimal
4. Check stream quality on phone/tablet

**What to Watch For:**
- Stream buffering or pixelation
- Dropped frames in OBS
- Connection interruptions
- Quality degradation over time

---

## 🔌 Physical Connection Setup

### Ethernet (Required)

**Why Ethernet is Essential:**
- More stable than WiFi
- Lower latency
- No interference from other devices
- Consistent bandwidth

**Setup Steps:**
1. **Cable Selection:**
   - Use Cat5e or Cat6 cable
   - Length: Appropriate for your setup
   - Check for damage (no kinks or breaks)

2. **Connection:**
   - Connect cable from router to computer
   - Ensure both ends click securely
   - Verify connection in system settings

3. **Disable WiFi:**
   - Windows: Settings → Network & Internet → WiFi → Off
   - Mac: System Preferences → Network → WiFi → Turn WiFi Off
   - This ensures traffic uses Ethernet only

4. **Verify Connection:**
   ```bash
   # Windows
   ipconfig
   
   # Mac/Linux
   ifconfig
   
   # Look for Ethernet adapter with IP address
   ```

### Router Placement

**Optimal Setup:**
- Router within 25 feet of computer
- Minimize cable length (but not too tight)
- Router in open space (not in cabinet)
- Away from heat sources
- Ventilation for cooling

---

## ⚙️ Router Configuration

### Access Router Settings

**Find Router IP:**
- Usually: 192.168.1.1 or 192.168.0.1
- Windows: `ipconfig` → Default Gateway
- Mac: System Preferences → Network → Advanced → TCP/IP → Router

**Login:**
1. Open browser, go to router IP
2. Login with admin credentials
   - Common defaults: admin/admin, admin/password
   - Check router label or manual

### Quality of Service (QoS)

**Why QoS Matters:**
- Prioritizes streaming traffic
- Prevents other devices from affecting stream
- Ensures bandwidth allocation

**Setup QoS:**
1. Find QoS settings in router admin
   - May be under "Advanced Settings"
   - Or "Traffic Management"
2. Enable QoS
3. Add Rule for Streaming Computer:
   ```
   Device: [Your computer's IP or MAC address]
   Priority: Highest
   Ports: 1935 (RTMP)
   Protocol: TCP
   ```
4. Alternative: Set device priority by MAC address
5. Save settings and reboot router

### Firmware Update

**Check for Updates:**
1. In router settings, look for "Firmware" or "System Update"
2. Check for latest firmware version
3. **Update at least 1 week before event** (not day before)
4. Reboot router after update

### Channel Optimization (WiFi)

**Even with Ethernet, optimize WiFi for backup:**
1. Use WiFi analyzer app to check channel congestion
2. Switch to less congested channel:
   - 2.4 GHz: Channels 1, 6, or 11 (non-overlapping)
   - 5 GHz: Any available channel
3. Save settings and test

---

## 🚫 Bandwidth Management

### Disconnect Other Devices

**Day of Event:**
- [ ] Smart TVs disconnected from network
- [ ] Gaming consoles turned off
- [ ] Tablets/phones on cellular (not WiFi)
- [ ] Smart home devices paused (if possible)
- [ ] Other computers shut down
- [ ] Inform household members about internet priority

### Disable Bandwidth-Heavy Services

**On Streaming Computer:**
- [ ] Cloud storage sync (Dropbox, Google Drive, OneDrive)
  - Pause syncing
  - Exit applications
- [ ] Automatic updates (Windows Update, Mac App Store)
  - Pause for 7 days
- [ ] Torrents or P2P applications
  - Close completely
- [ ] Large downloads
  - Cancel or pause
- [ ] Backup software
  - Pause scheduled backups

**Check Background Processes:**

**Windows:**
```
1. Task Manager (Ctrl+Shift+Esc)
2. Go to "Performance" tab
3. Click "Open Resource Monitor"
4. Check "Network" tab for bandwidth usage
5. End any non-essential network activity
```

**Mac:**
```
1. Activity Monitor (Applications → Utilities)
2. Go to "Network" tab
3. Sort by "Sent Bytes" or "Received Bytes"
4. Quit any non-essential network applications
```

---

## 📱 Backup Internet Connection

### Mobile Hotspot Setup

**Requirements:**
- Smartphone with unlimited data (or sufficient data plan)
- 4G LTE or 5G coverage in your location
- USB cable for tethering (most reliable)
- Fully charged phone

**Test Before Event:**

**iPhone:**
1. Settings → Personal Hotspot → Allow Others to Join
2. Connect computer via USB (most stable)
   - Or via WiFi if needed
3. Run speed test
4. Document upload speed

**Android:**
1. Settings → Network & Internet → Hotspot & Tethering
2. Enable "USB tethering" (if connected via USB)
   - Or "WiFi hotspot" if needed
3. Run speed test
4. Document upload speed

**Expected Speeds:**
- 4G LTE: 5-20 Mbps upload (varies by carrier and location)
- 5G: 20-100+ Mbps upload (if available)

### Backup Connection Process

**If Primary Internet Fails:**

1. **In OBS:**
   - Stream will show "Reconnecting..."
   - OBS will automatically retry

2. **Enable Hotspot:**
   - iPhone: Settings → Personal Hotspot → On
   - Android: Settings → Hotspot → On

3. **Connect Computer:**
   - USB tethering (preferred):
     - Connect phone via USB
     - Enable tethering on phone
     - Computer auto-detects, switch network
   - WiFi (alternative):
     - Connect to phone's hotspot network
     - Enter password

4. **Verify Connection:**
   - Check network icon (should show phone connection)
   - OBS will reconnect within 30-60 seconds

5. **Communicate:**
   - Post in Discord: "Brief technical interruption, returning shortly"
   - Continue stream once reconnected

**Practice This Process:**
- Do full test at least 1 week before event
- Time how long it takes to switch
- Verify stream continues with hotspot

---

## 📊 Monitoring Connection During Stream

### OBS Statistics

**View → Stats Window:**

Monitor these metrics:
```
CPU Usage: <80% (ideally <70%)
Rendering Lag: <5% (ideally 0%)
Encoding Lag: <5% (ideally 0%)

Dropped Frames due to rendering lag: <1%
Dropped Frames due to encoding lag: <1%
Dropped Frames (network): <1%

Average time to render frame: <16.7ms (for 30fps)
Frames missed due to rendering lag: <100 total
Output skipped frames: <100 total

Bitrate: Should stay near your target (5000 Kbps)
```

**If Issues Occur:**
- High CPU: Lower encoding preset or resolution
- Dropped frames (network): Internet instability
- Rendering/encoding lag: Close other apps, lower settings

### YouTube Studio Analytics

**Keep open in browser tab:**
- **Stream Health**: Should be "Excellent" or "Good"
  - Excellent: Everything optimal
  - Good: Minor issues but acceptable
  - Poor: Connection problems, may need adjustment
  - Bad: Severe issues, viewers affected
- **Current Viewers**: Track audience size
- **Peak Concurrent Viewers**: Milestone tracking
- **Chat Activity**: Monitor engagement

### Network Monitor (Secondary)

**Windows:**
- Resource Monitor → Network tab
- Watch network activity for spikes

**Mac:**
- Activity Monitor → Network tab
- Watch "Sent Bytes" for consistency

---

## 🔧 Troubleshooting Connection Issues

### Symptom: Stream Keeps Disconnecting

**Causes:**
- Unstable internet connection
- Insufficient upload speed
- ISP throttling
- Network congestion

**Solutions:**
1. **Lower Bitrate:**
   - OBS → Settings → Output
   - Reduce bitrate: 5000 → 4000 → 3500
   - Restart stream

2. **Lower Resolution:**
   - Settings → Video
   - Change output to 1280x720 (720p)
   - Reduces bandwidth requirement

3. **Check for Interference:**
   - Ensure Ethernet cable not damaged
   - Check router logs for errors
   - Restart router (only if stream is down)

4. **Switch to Backup:**
   - Follow mobile hotspot procedure

### Symptom: High Latency/Lag

**Causes:**
- Network congestion
- Other devices using bandwidth
- ISP routing issues

**Solutions:**
1. Disconnect all other devices
2. Check background processes
3. Contact ISP if persistent

### Symptom: Pixelated Video

**Causes:**
- Insufficient bitrate for resolution
- Network instability
- CPU overload

**Solutions:**
1. **Increase Bitrate** (if upload speed allows):
   - 5000 → 6000 Kbps
2. **OR Lower Resolution**:
   - 1080p → 720p
3. **Check CPU Usage**:
   - If >80%, lower encoding preset

### Symptom: Audio/Video Desync

**Causes:**
- Encoder overload
- High CPU usage
- Buffer issues

**Solutions:**
1. Check OBS Stats for CPU usage
2. Close non-essential applications
3. Lower encoder preset
4. Consider dropping to 720p

---

## 🎯 Network Optimization Checklist

### One Week Before Event

- [ ] Run speed tests at event time (multiple days)
- [ ] Document average upload/download speeds
- [ ] Test with OBS streaming to unlisted YouTube video
- [ ] Monitor for 30-60 minutes for stability
- [ ] Test mobile hotspot backup (speed test + OBS test)
- [ ] Update router firmware (if needed)
- [ ] Configure QoS on router
- [ ] Practice switching to backup internet

### One Day Before Event

- [ ] Final speed test at event time
- [ ] Verify Ethernet cable connected and working
- [ ] Charge mobile hotspot phone to 100%
- [ ] Verify unlimited data or sufficient data plan
- [ ] Create list of all devices to disconnect
- [ ] Inform household members of internet priority
- [ ] Test router connection and verify settings

### Day of Event (Morning)

- [ ] Speed test in morning
- [ ] Disconnect all non-essential devices from network
- [ ] Close bandwidth-heavy applications
- [ ] Pause cloud syncing services
- [ ] Pause automatic updates
- [ ] Verify Ethernet connection
- [ ] Disable WiFi on streaming computer
- [ ] Charge mobile hotspot to 100%
- [ ] Have USB cable ready for tethering

### 2 Hours Before Event

- [ ] Final speed test
- [ ] Verify no other devices on network
- [ ] Check no background downloads/uploads
- [ ] Mobile hotspot ready and charged
- [ ] Router positioned for optimal performance
- [ ] All cables secure and connected

---

## 📞 ISP Contact Information

**Prepare for Emergency:**

Document your ISP information:
```
ISP Name: ___________________________
Account Number: ______________________
Support Phone: _______________________
Business Support: ____________________
(Usually faster response)

Known Issues: ________________________
Typical Upload Speed: ________________
Data Cap (if any): ___________________
```

**When to Contact ISP:**
- Persistent connection issues in testing
- Upload speeds significantly below plan
- Need to request priority support during event
- Request business-class support if available

---

## 📈 Best Practices

### Do's

✅ **DO use hardwired Ethernet connection**
✅ **DO test at same time as event (multiple days)**
✅ **DO have mobile hotspot backup ready**
✅ **DO disconnect all other devices**
✅ **DO monitor OBS stats during stream**
✅ **DO practice switching to backup**
✅ **DO have USB cable for phone tethering**
✅ **DO close bandwidth-heavy applications**

### Don'ts

❌ **DON'T rely on WiFi for primary connection**
❌ **DON'T wait until event day to test backup**
❌ **DON'T update router firmware day before event**
❌ **DON'T allow other devices on network during stream**
❌ **DON'T use VPN (adds latency and reduces speed)**
❌ **DON'T stream without testing your setup first**
❌ **DON'T panic if brief disconnection occurs (OBS auto-reconnects)**

---

## 🌟 Pro Tips

### Communicate with ISP
- Consider contacting ISP beforehand
- Inform them of scheduled live stream
- Ask about potential maintenance scheduled
- Request business priority if available

### Redundancy
- Consider two internet connections if possible
  - Primary: Home internet (Ethernet)
  - Backup: Mobile hotspot (4G/5G)
- OBS can be configured with backup stream

### Buffer Time
- Start stream 5-10 minutes before event
- Verify connection stability before going "live"
- Allow time to switch to backup if needed

### Calm Under Pressure
- Brief disconnections (10-30 seconds) are recoverable
- OBS auto-reconnects
- Viewers are usually understanding
- Have a plan but stay flexible

---

## ✅ Connection Day-Of Checklist

**Print and keep near setup:**

- [ ] Ethernet cable connected (click confirmed)
- [ ] WiFi disabled on computer
- [ ] All other devices disconnected from network
- [ ] Router powered on and functioning
- [ ] Mobile hotspot phone charged to 100%
- [ ] USB cable for tethering within reach
- [ ] Speed test shows adequate upload speed (>10 Mbps)
- [ ] OBS Stats window open and monitoring
- [ ] YouTube Studio open in browser
- [ ] No background downloads/uploads
- [ ] Cloud sync services paused
- [ ] Household informed of internet priority
- [ ] Backup plan rehearsed and ready
- [ ] ISP contact info available (if needed)

---

*A stable internet connection is the foundation of a successful live stream. Prepare, test, and trust your backup plan.* ✨
