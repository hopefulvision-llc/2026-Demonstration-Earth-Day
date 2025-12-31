# Testing and Rehearsal Guide - Earth Day 2026 Event

Comprehensive testing schedule and procedures to ensure event success.

---

## 🗓️ Testing Timeline

### 4 Weeks Before (March 25, 2026)
**Focus: Equipment and Basic Setup**

### 3 Weeks Before (April 1, 2026)
**Focus: Software Configuration**

### 2 Weeks Before (April 8, 2026)
**Focus: Integration Testing**

### 1 Week Before (April 15, 2026)
**Focus: Full Rehearsal**

### 2 Days Before (April 20, 2026)
**Focus: Final Dress Rehearsal**

### 1 Day Before (April 21, 2026)
**Focus: Final Checks**

---

## Week 4: Equipment Testing (March 25-31)

### Camera Testing
- [ ] **Positioning Test**:
  - Set up camera at eye level
  - Test different distances (2-4 feet optimal)
  - Verify field of view captures you properly
  - Check background appears as intended
  - Take test photos at different times of day

- [ ] **Video Quality Test**:
  - Record 5-minute test video
  - Review for focus, clarity, color
  - Test in different lighting conditions
  - Verify 1080p resolution
  - Check frame rate (30fps)

- [ ] **Backup Camera Test**:
  - Set up secondary camera or phone
  - Test as backup option
  - Verify can switch quickly if needed

### Microphone Testing
- [ ] **Audio Quality Test**:
  - Record 5-minute audio test
  - Speak at normal volume
  - Test at different distances (6", 8", 10", 12")
  - Listen for background noise
  - Check for plosives (pop sounds on P, B, T)

- [ ] **Levels Test**:
  - Record speaking at different volumes
  - Ensure no clipping (red in meters)
  - Target -20 to -10 dB range
  - Test with pop filter vs without

- [ ] **Background Noise Test**:
  - Record 1 minute of silence
  - Identify noise sources (AC, computer fan, etc.)
  - Plan noise reduction strategies

### Lighting Testing
- [ ] **Exposure Test**:
  - Test lighting at different times of day
  - Verify even lighting on face
  - Check for harsh shadows
  - Test with ring light, natural light, mixed

- [ ] **Color Temperature Test**:
  - Adjust lighting color (warm vs cool)
  - Verify skin tones look natural
  - Match lighting to background

### Network Testing
- [ ] **Speed Tests**:
  - Run tests at multiple times of day
  - Document results (see NETWORK_CONNECTIVITY.md)
  - Test on event day/time if possible
  - Average upload speed should be >15 Mbps

- [ ] **Ethernet Connection**:
  - Connect via Ethernet cable
  - Disable WiFi
  - Verify connection in system settings
  - Run speed test on Ethernet only

- [ ] **Mobile Hotspot Test**:
  - Enable hotspot on phone
  - Connect computer via USB tethering
  - Run speed test
  - Document hotspot upload speed
  - Verify adequate for streaming (>10 Mbps)

---

## Week 3: Software Configuration (April 1-7)

### OBS Testing
- [ ] **Initial Setup Test**:
  - Complete OBS configuration (see SOFTWARE_CONFIGURATION.md)
  - Verify all settings correct
  - Test each scene individually
  - Check sources load properly

- [ ] **Scene Transition Test**:
  - Practice switching between all scenes
  - Set up hotkeys (F1-F6)
  - Test transition smoothness
  - Verify audio continues properly

- [ ] **Audio Mixer Test**:
  - Test microphone levels
  - Add noise suppression filter
  - Add noise gate and compressor
  - Test desktop audio capture
  - Test 528 Hz tone playback
  - Verify all levels appropriate

- [ ] **10-Minute Test Recording**:
  - Record 10-minute test with scene changes
  - Review recording for issues
  - Check video quality
  - Check audio quality and sync
  - Verify file size and format

### YouTube Setup Test
- [ ] **Create Test Stream**:
  - Set up unlisted test stream event
  - Get stream key
  - Add stream key to OBS
  - Verify connection to YouTube

- [ ] **5-Minute Test Stream**:
  - Stream to unlisted YouTube event
  - Monitor stream on phone/tablet
  - Check video quality
  - Check audio quality
  - Verify latency (10-20 seconds normal)
  - Test chat functionality

### Discord Testing
- [ ] **Server Setup**:
  - Create all channels
  - Set up roles and permissions
  - Add bots (MEE6, Poll bot)
  - Test permissions for each role

- [ ] **Voice Channel Test**:
  - Join voice channel
  - Test audio quality
  - Verify others can join
  - Test screen share in Discord (optional)

- [ ] **Moderation Test**:
  - Test bot commands
  - Test timeout/mute functions
  - Verify moderator permissions work

### Graphics and Overlays Test
- [ ] **Import Graphics to OBS**:
  - Add lower thirds to scenes
  - Add transition slides
  - Test graphics display properly
  - Verify transparent backgrounds work

- [ ] **B-Roll Test**:
  - Import all B-roll clips
  - Create media sources in OBS
  - Test playback
  - Verify audio levels on clips

---

## Week 2: Integration Testing (April 8-14)

### 30-Minute Integrated Test
**Date: April 8-10**

**Test Stream Setup:**
1. Set up unlisted YouTube test stream
2. Complete full technical setup
3. Stream for 30 minutes minimum
4. Follow abbreviated event flow

**What to Test:**
- [ ] Opening with 528 Hz tone (1 minute, not full 2)
- [ ] Welcome and introduction (5 minutes)
- [ ] Switch to presentation mode
- [ ] Screen share demonstration (5 minutes)
- [ ] Switch to full screen demo (5 minutes)
- [ ] Use transition slide between segments
- [ ] Community showcase with B-roll (3 minutes)
- [ ] Q&A simulation (5 minutes)
- [ ] Closing with 528 Hz tone (1 minute)

**Monitor During Test:**
- [ ] OBS Stats window (CPU, dropped frames, bitrate)
- [ ] YouTube stream health
- [ ] Recording file creation
- [ ] Audio levels throughout
- [ ] Chat functionality
- [ ] Discord simultaneous monitoring

**After Test Review:**
- [ ] Watch recording completely
- [ ] Note all issues or improvements
- [ ] Check file size and quality
- [ ] Review YouTube analytics
- [ ] Document any glitches or problems

### 60-Minute Stress Test
**Date: April 11-13**

**Purpose:** Test extended streaming stability

**Setup:**
1. Full technical setup
2. Unlisted YouTube stream
3. Run for 60+ minutes
4. Simulate event conditions

**Activities:**
- [ ] Stream continuously for 60 minutes
- [ ] Change scenes every 5-10 minutes
- [ ] Use all scene types
- [ ] Play B-roll clips
- [ ] Use screen share
- [ ] Monitor all systems

**What to Monitor:**
- [ ] CPU usage over time
- [ ] Temperature (computer cooling)
- [ ] Dropped frames accumulation
- [ ] Network stability
- [ ] Recording file growth
- [ ] No memory leaks

**Document:**
- Average CPU usage: ______%
- Total dropped frames: ______
- Average bitrate: ______ Kbps
- Any issues: _______________

### Backup System Test
**Date: April 12-14**

**Test Internet Failover:**
1. Start test stream with primary internet
2. After 5 minutes, disconnect Ethernet
3. Switch to mobile hotspot
4. Verify OBS reconnects
5. Continue streaming on hotspot for 10 minutes
6. Monitor quality and stability
7. Switch back to primary
8. Verify smooth transition

**Document:**
- Time to reconnect: ______ seconds
- Quality on hotspot: Good / Fair / Poor
- Any issues: _______________

**Test Backup Equipment:**
- [ ] Test backup camera (phone or secondary webcam)
- [ ] Test backup microphone
- [ ] Practice switching quickly
- [ ] Time the switch process

---

## Week 1: Full Rehearsal (April 15-21)

### Full 4-Hour Rehearsal
**Date: April 18-19 (2-3 days before event)**

**Setup:**
- [ ] Complete technical setup as if event day
- [ ] Unlisted YouTube stream (or just local recording if preferred)
- [ ] Full 4-hour run-through
- [ ] Follow complete event schedule
- [ ] Practice all segments

**Hour 1: Philosophy & Vision (60 minutes)**
- [ ] Opening ceremony with 528 Hz tone (2 minutes)
- [ ] Welcome and land acknowledgment
- [ ] Personal introduction
- [ ] Philosophical foundation (20 minutes)
- [ ] Problem we're solving (15 minutes)
- [ ] Sacred technology vision (10 minutes)
- [ ] Transition to Hour 2

**Hour 2: Prototype Demonstrations (60 minutes)**
- [ ] Magnifier Bubble demo (20 minutes)
  - Screen share, browser demo
  - Key features walkthrough
- [ ] Whisper Agent demo (20 minutes)
  - Mobile/desktop demonstration
- [ ] Earth Interface demo (20 minutes)
  - Web application walkthrough
- [ ] Transition to Hour 3

**Hour 3: Community Showcase (60 minutes)**
- [ ] Guild introduction (10 minutes)
- [ ] Technical development guild (15 minutes)
- [ ] Creative arts guild (10 minutes)
- [ ] Philosophy guild (10 minutes)
- [ ] Digital shamanism guild (10 minutes)
- [ ] Transformation stories (5 minutes - B-roll)
- [ ] Transition to Hour 4

**Hour 4: Open Forum & Vision (60 minutes)**
- [ ] Live Q&A practice (30 minutes)
  - Use pre-written questions
  - Practice answering naturally
- [ ] Partnership exploration (15 minutes)
- [ ] Vision sharing (10 minutes)
- [ ] Closing ceremony (5 minutes)
  - Gratitude acknowledgments
  - 528 Hz tone (90 seconds)
  - Namasté

**During Rehearsal:**
- [ ] Record everything
- [ ] Take notes on timing
- [ ] Note what feels rushed or slow
- [ ] Practice transitions
- [ ] Test all demos thoroughly
- [ ] Monitor technical stats throughout

**After Rehearsal:**
- [ ] Watch recording (at least highlights)
- [ ] Review timing for each segment
- [ ] Adjust schedule if needed
- [ ] Note all technical issues
- [ ] Plan improvements for event day
- [ ] Rest and integrate feedback

**Timing Adjustments:**
```
Segment                     | Planned | Actual  | Adjust
─────────────────────────── ─────────┼─────────┼────────
Opening Ceremony            | 15 min  | __ min  | ±__ min
Philosophical Foundation    | 20 min  | __ min  | ±__ min
Problem We're Solving       | 15 min  | __ min  | ±__ min
Sacred Tech Vision          | 10 min  | __ min  | ±__ min
Magnifier Bubble Demo       | 20 min  | __ min  | ±__ min
Whisper Agent Demo          | 20 min  | __ min  | ±__ min
Earth Interface Demo        | 20 min  | __ min  | ±__ min
[etc...]
```

---

## 2 Days Before: Dress Rehearsal (April 20)

### Final Complete Run-Through

**Purpose:** 
- Final practice with all elements
- Test any adjustments from previous rehearsal
- Build confidence and familiarity

**Setup:**
- [ ] Complete technical setup
- [ ] All equipment in final positions
- [ ] All graphics and B-roll ready
- [ ] All demo materials prepared

**Abbreviated Rehearsal (2 hours):**
- [ ] Run through opening (full)
- [ ] Sample from each hour (10-15 min each)
- [ ] Run through closing (full)
- [ ] Practice critical transitions
- [ ] Test all demos one more time

**Focus On:**
- [ ] Smooth transitions
- [ ] Clear speaking pace
- [ ] Managing time
- [ ] Technical confidence
- [ ] Mental preparation

**Final Checklist:**
- [ ] All scenes work perfectly
- [ ] All audio sources correct
- [ ] All graphics display properly
- [ ] All demos function correctly
- [ ] Backup systems ready
- [ ] Confident with material
- [ ] Questions prepared for Q&A

---

## 1 Day Before: Final Checks (April 21)

### Equipment Check (30 minutes)
- [ ] All hardware connected and working
- [ ] Camera focused and positioned
- [ ] Microphone positioned and tested
- [ ] Lighting on and adjusted
- [ ] Headphones working
- [ ] All cables secure

### Software Check (30 minutes)
- [ ] OBS opens and loads scenes properly
- [ ] YouTube event scheduled and ready
- [ ] Stream key correct
- [ ] Discord server ready
- [ ] All graphics and media imported
- [ ] 528 Hz tones ready to play

### Network Check (15 minutes)
- [ ] Speed test shows adequate speed
- [ ] Ethernet connected
- [ ] WiFi disabled
- [ ] Mobile hotspot charged
- [ ] QoS configured on router

### Content Review (30 minutes)
- [ ] Review questions prepared for Q&A
- [ ] Review demonstration steps
- [ ] Review timing for each segment
- [ ] Review key talking points
- [ ] Prepare any notes needed

### Personal Preparation
- [ ] Plan early bedtime (8+ hours sleep)
- [ ] Prepare meals for event day
- [ ] Clear schedule for entire day
- [ ] Meditation/grounding practice
- [ ] Set intentions for event
- [ ] Trust in preparation

---

## Testing Checklist Summary

### ✅ Completed Tests Record

**Equipment:**
- [ ] Camera quality and positioning
- [ ] Microphone audio quality
- [ ] Lighting exposure and color
- [ ] Backup equipment functional

**Software:**
- [ ] OBS scenes configured and tested
- [ ] YouTube test stream successful
- [ ] Discord server set up
- [ ] Graphics and overlays working

**Network:**
- [ ] Speed tests documented (>15 Mbps upload)
- [ ] Ethernet connection tested
- [ ] Mobile hotspot backup tested
- [ ] Failover process practiced

**Integration:**
- [ ] 30-minute test stream completed
- [ ] 60-minute stress test completed
- [ ] Backup system switch tested
- [ ] All issues documented and resolved

**Rehearsals:**
- [ ] Full 4-hour rehearsal completed
- [ ] Timing adjustments made
- [ ] Dress rehearsal completed
- [ ] Final checks completed

---

## Common Issues and Solutions

### Issue: OBS High CPU During Test

**Solutions:**
- Lower encoder preset (fast → veryfast → ultrafast)
- Reduce resolution (1080p → 720p)
- Close unnecessary applications
- Update graphics drivers
- Check for background processes

### Issue: Audio/Video Desync

**Solutions:**
- Check audio offset in OBS source settings
- Restart OBS
- Verify CPU is not overloaded
- Check for dropped frames

### Issue: Stream Buffering for Viewers

**Solutions:**
- Lower bitrate (5000 → 4000 Kbps)
- Lower resolution to 720p
- Check upload speed
- Verify network stability
- Test with different viewer devices

### Issue: Background Noise in Audio

**Solutions:**
- Add noise suppression filter (RNNoise)
- Add noise gate (threshold: -40 dB)
- Position microphone closer
- Reduce gain if too high
- Eliminate noise sources (AC, fans)

### Issue: Timing Too Long/Short

**Solutions:**
- Adjust segment lengths
- Have flexible content (can extend or shorten)
- Build in buffer time
- Mark "optional" sections that can be skipped

---

## Documentation Template

**Test Log:**
```
Date: _______________
Test Type: _______________
Duration: _______________

Equipment Used:
- Camera: _______________
- Microphone: _______________
- Lighting: _______________
- Internet Speed: ___ Mbps upload

Software Configuration:
- OBS Version: _______________
- Resolution: _______________
- Bitrate: _______________
- Encoder: _______________

Results:
✅ Success Areas:
- ___________________________
- ___________________________

⚠️ Issues Found:
- ___________________________
- ___________________________

🔧 Actions Needed:
- ___________________________
- ___________________________

Notes:
___________________________
___________________________
```

---

## Final Pre-Event Checklist

**All tests completed and documented:**
- [ ] Equipment tests successful
- [ ] Software tests successful
- [ ] Network tests successful
- [ ] Integration tests successful
- [ ] Full rehearsal completed
- [ ] All issues resolved
- [ ] Backup systems tested
- [ ] Confident and prepared

**You are ready!** ✨

---

*Thorough testing builds confidence. Trust your preparation and enjoy the event!*
