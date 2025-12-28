# Linux-Bazzite-Rust-Tweaks-and-Optimization
Launch option commands for higher FPS and a tutorial for how to actually play Rust on Linux (specifically in my case Bazzite)

### 1. Actual launch options

```gamescope -w 1280 -h 960 -r 320 -S stretch -- %command% -screen-width 1280 -screen-height 960 -rate 320 -window-mode exclusive -nolog -high -force-feature-level-11-0 +gc.buffer 2048```

  -This line will set Rust to 1280 by 960 resolution without black bars and set the refresh rate to 320 (-w 1280 -h 960 and -rate 320)

### 2. What servers to play on

  -You cannot play on Official Facepunch servers or any community server that enforces strict EAC. If you try, you will likely be kicked after a minute or two with an "EAC Disconnected" error. So you have to play on servers specifically configured for Linux/No-EAC
   
  -How to find servers that work:
    -In the server browser, search for terms like "Linux", "No EAC", or "Proton".
    
  -Known working servers: "Deadlock" (often play.deadlock.com) and "Protobit" are historically the most reliable servers for Linux players.
   
  -Connection Method: If the server doesn't show in the browser, press F1 to open the console and type: connect [server_ip_address] (e.g., connect play.deadlock.com)

### 3. Proton version setting
  -Rust can be picky about which translation layer it uses.

  -Recommendation: Use Proton Experimental or GE-Proton (latest version).
    -How to set it:
      -Right-click Rust in Steam.
      -Go to Properties > Compatibility.
      -Check "Force the use of a specific Steam Play compatibility tool".
      -Select Proton Experimental.

### 4. Launch option commands summary (what does what do)
  -Resolution: -screen-width 1280 -screen-height 960 forces the engine to render at this res.
  -Refresh Rate: -rate 320 attempts to force the engine to sync to your high refresh rate (ensure your monitor is set to 320Hz in display settings first).
  -Performance:
    -high: Sets high CPU priority for the game process.
    -force-feature-level-11-0: Forces DirectX 11.0 feature set, which is often more stable and higher FPS on Proton than newer feature sets.
    -nolog: Disables writing output logs, saving tiny bits of I/O overhead.
    +gc.buffer 2048: Increases the Garbage Collection buffer. This is critical for Rust; it reduces the frequency of those massive "stutter" spikes.

### yap
  -In the tutorial txt file is a more complex explanation of all this and also a step-by-step walkthrough
