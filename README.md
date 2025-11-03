<p align="center">
  <img height="120" src="https://raw.githubusercontent.com/primer/octicons/main/icons/speaker-24.svg" />
</p>

<h1 align="center">LAN Sync Audio Player</h1>
<p align="center">play **the same** audio on multiple phones — perfectly synced — no internet required 🎧🔊</p>

---

<div align="center">
  
**Sync accuracy:** ± 2–5ms  
**Transport:** WebRTC DataChannel / LAN websocket  
**Clocking:** Web Audio internal DSP time  
**Mode:** OFFLINE only (hotspot / local wifi)  

</div>

---

## ⭐ What this project is

This is a local-network group audio player.

One phone becomes **Host**.  
Others join over hotspot wifi.  
Everyone loads the same audio file.  
Host says **“play at timestamp = T”** → all devices fire at the same exact moment.

No cloud. No streaming. No user accounts.

Just pure local sync like early LAN games (mini militia vibe).

---

## 🧠 Why it works so well

We don’t sync *audio*.  
We sync **time**.

- every phone loads the mp3 locally
- we run a tiny JS **mini-NTP** clock alignment
- playback is scheduled using `AudioContext.start(absoluteTime)`
- drift becomes microscopic

---

## 🚀 Quick mental model (animation)

