---                                                                                                                                                                                                                                             
  name: screenshot                                                                                                                                                                                                                                
  description: Read the most recent screenshot from the Desktop into the conversation. Use this when the user says "screenshot", "look at this", "see this image", or wants to share their screen visually. Supports optional countdown:          
  /screenshot 5, /screenshot 10, /screenshot 15, /screenshot 30.
  ---                                                                                                                                                                                                                                             

  Check if the user provided a number of seconds as an argument (e.g. `/screenshot 10`).

  **If a delay was requested (5, 10, 15, or 30 seconds):**
  1. Tell the user: "Starting [N]-second countdown — get your screen ready! 🕐"
  2. Run: `sleep [N]`
  3. Then continue below.

  **If no delay, load immediately.**

  Load the most recent screenshot from the Desktop:
  1. Run: `ls -t ~/Desktop/Screenshot*.png 2>/dev/null | head -1`
  2. If a file is found, read it using the Read tool
  3. Describe what you see and ask how you can help

  If no screenshots exist, tell the user they can take one with:
  - **Cmd+Shift+4** — select an area
  - **Cmd+Shift+3** — full screen
  - **Cmd+Shift+5** — advanced options (record, window, etc.)

  Then use `/screenshot` or `/screenshot 10` to load it with a countdown.
