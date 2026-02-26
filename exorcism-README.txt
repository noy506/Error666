EXORCISM GAME - SETUP GUIDE
==========================

WHAT I'VE CREATED FOR YOU:
--------------------------
✓ Complete working game in a single HTML file: exorcism-game.html
✓ Microphone volume detection (affects ripple size - IT'S WORKING!)
✓ Speech recognition for blessing words
✓ Swirling code animation effect
✓ Blessing ripple effects (white text + gradient waves)
✓ Win condition (bless 100% of code OR say the instant win spell)
✓ Keyboard controls (Enter/R/Esc)
✓ Audio playback hooks for your sound files

HOW TO PLAY:
------------
1. Open exorcism-game.html in Chrome or Edge (required for speech recognition)
2. Press ENTER to start
3. Allow microphone access when prompted
4. Speak blessing words (holy, divine, blessed, light, etc.)
5. Watch the code turn white as you bless it
6. Louder voice = bigger ripple effect
7. Keep blessing until 100% coverage to win!

INSTANT WIN SPELL:
Say this phrase: "Lorem ipsum dolor sit amet consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua"

BLESSING WORDS LIST (50+ words):
--------------------------------
holy, divine, sacred, blessed, pure, light, grace, faith, hope, love, peace,
truth, righteous, sanctified, hallowed, angel, heaven, prayer, amen, hallelujah,
spirit, holy spirit, salvation, redemption, mercy, forgiveness, glory, praise,
worship, jesus, christ, god, lord, almighty, creator, savior, redeemer, heal,
cleanse, purify, protect, shield, guard, deliver, save, rescue, restore, renew, revive

AUDIO FILES YOU NEED TO ADD:
----------------------------
The game will work WITHOUT audio files, but to add your sounds:

1. Create folder structure:
   Desktop/
     └─ exorcism-assets/
          └─ sounds/
               ├─ error-laugh.mp3      (error sound that morphs to laugh)
               ├─ evil-1.mp3           (evil commentary #1)
               ├─ evil-2.mp3           (evil commentary #2)
               ├─ ... (up to evil-17.mp3)
               └─ nooo.mp3             (big "NOOO" for win)

2. Update the file paths in the HTML:
   - Open exorcism-game.html in a text editor
   - Find line ~262: this.audioFiles = {
   - Change the paths to match where you put your audio files

   Example:
   errorLaugh: 'exorcism-assets/sounds/error-laugh.mp3',
   evilCommentary: Array.from({length: 17}, (_, i) => `exorcism-assets/sounds/evil-${i+1}.mp3`),
   winScream: 'exorcism-assets/sounds/nooo.mp3'

CURRENT AUDIO SETUP:
--------------------
- Error/laugh sound: Plays at corruption start (NOT IMPLEMENTED YET - you can add it)
- Evil commentary: Plays randomly every 5-10 seconds during gameplay
- Win scream: Plays when you complete the exorcism

VOLUME RECOGNITION:
-------------------
✓ WORKING! Don't worry, it's not complicated.
- Quiet voice = small ripple (3-4 character radius)
- Normal voice = medium ripple (6-7 character radius)
- Loud voice = big ripple (10 character radius max)

The volume affects:
1. How big the white gradient ripple spreads
2. How many surrounding characters get blessed

GAME MECHANICS:
---------------
1. Code starts dark (almost black)
2. When you say a blessing word:
   - The word appears in white in the code
   - A ripple effect spreads from the word
   - Surrounding characters get lighter (gradient effect)
3. If you stop blessing, the white areas FADE BACK to dark (decay system)
4. You must keep blessing to maintain coverage
5. Win when 100% of code is white

VISUAL EFFECTS:
---------------
✓ Swirling animation - code rotates and moves organically
✓ Blessing ripples - white gradient waves from blessed words
✓ Color interpolation - smooth transition from dark to white
✓ Decay effect - blessed areas fade if you're silent
✓ Win animation - white flash + completion time

CUSTOMIZATION IDEAS:
--------------------
1. Change code text: Edit CODE_TEXT variable (line ~40)
2. Add more blessing words: Edit BLESSINGS array (line ~26)
3. Adjust swirl speed: Change CONFIG.swirlSpeed (line ~17)
4. Change decay rate: Adjust CONFIG.decayRate (line ~15)
5. Ripple duration: Modify CONFIG.rippleDuration (line ~18)

TESTING CHECKLIST:
------------------
[ ] Open in Chrome/Edge
[ ] Press Enter - microphone permission requested
[ ] Say "holy" - white text appears in code
[ ] Say "divine" - more white text + ripple
[ ] Test volume - speak quietly vs loudly
[ ] Stay silent - watch white areas fade back
[ ] Keep blessing until 100% - win screen appears
[ ] Press R - game restarts
[ ] Test instant win spell

TROUBLESHOOTING:
----------------
Q: No microphone access?
A: Check browser permissions, allow microphone access

Q: Speech recognition not working?
A: Must use Chrome or Edge (Chromium). Firefox/Safari not supported.

Q: Audio files not playing?
A: Check file paths match exactly. Open browser console (F12) for errors.

Q: Game too easy/hard?
A: Adjust CONFIG.decayRate to make it harder (higher) or easier (lower)

Q: Want to skip initial corruption animation?
A: You mentioned creating a video - the game starts in "playing" mode already!
   Just add your video before the game, then the user presses Enter to play.

NEXT STEPS:
-----------
1. Open exorcism-game.html in Chrome
2. Test without audio first
3. Create your audio files
4. Add them to the exorcism-assets/sounds folder
5. Update file paths in the HTML
6. (Optional) Create corruption intro video
7. Enjoy exorcising demons!

INTEGRATION WITH YOUR VIDEO:
-----------------------------
If you create an intro video showing:
- Letters sticking together
- 666 appearing
- Code distortion

Just play it, then when it ends, load exorcism-game.html and the user presses Enter.
The game code already looks realistic and will match whatever aesthetic you choose!

---------------------------
Created with Claude Code
Have fun exorcising! 👻
