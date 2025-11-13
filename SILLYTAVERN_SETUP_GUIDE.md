# 🚀 COMPLETE SILLYTAVERN SETUP GUIDE FOR KATHERINE RPG

**Follow this guide step-by-step to get Katherine fully working.**

---

## PART 1: SILLYTAVERN INSTALLATION

### Step 1A: Check if SillyTavern is Already Installed

Open terminal/command prompt and type:
```bash
cd SillyTavern
npm start
```

**If it opens in browser at `http://localhost:8000`:**
✅ You already have SillyTavern! Skip to Part 2.

**If you get an error:**
❌ Need to install SillyTavern. Continue below.

---

### Step 1B: Install SillyTavern (If Needed)

#### Windows:
```bash
# 1. Install Node.js (if not installed)
# Download from: https://nodejs.org/ (LTS version)
# Install and restart computer

# 2. Install Git (if not installed)
# Download from: https://git-scm.com/downloads
# Install with default settings

# 3. Clone SillyTavern
git clone https://github.com/SillyTavern/SillyTavern.git
cd SillyTavern

# 4. Install dependencies
npm install

# 5. Start SillyTavern
npm start
```

#### Linux/Mac:
```bash
# 1. Install Node.js and Git (if not installed)
# Ubuntu/Debian:
sudo apt update
sudo apt install nodejs npm git

# Mac (using Homebrew):
brew install node git

# 2. Clone SillyTavern
git clone https://github.com/SillyTavern/SillyTavern.git
cd SillyTavern

# 3. Install dependencies
npm install

# 4. Start SillyTavern
npm start
```

**SillyTavern should now open at:** `http://localhost:8000`

---

## PART 2: CONNECT CLAUDE API

### Step 2A: Get Claude API Key

1. Go to: https://console.anthropic.com/
2. Sign up or log in
3. Click **"API Keys"** in left sidebar
4. Click **"Create Key"**
5. Name it: `Katherine_RPG`
6. Copy the key (starts with `sk-ant-`)
7. **SAVE IT SOMEWHERE SAFE** (you can't see it again!)

### Step 2B: Add Payment Method

⚠️ **REQUIRED**: Claude API requires payment method even for free tier

1. In Anthropic Console → **Billing**
2. Add credit card
3. Set budget limit (optional but recommended)
   - Suggested: $20/month budget
   - Cost per session: ~$0.50-1.50 for typical RP

### Step 2C: Connect API to SillyTavern

1. **Open SillyTavern** (http://localhost:8000)

2. **Top menu bar** → Click **🔌 API Connections**

3. **Chat Completion Sources** dropdown → Select **"Claude"**

4. **Enter API Key:**
   - Paste your `sk-ant-...` key
   - Click **"Connect"**
   - Should show ✅ **"Connected"** in green

5. **Select Model:**
   - Dropdown: `claude-3-5-sonnet-20241022`
   - ⚠️ **IMPORTANT**: Use Sonnet 3.5, NOT Haiku or older versions

6. **Configure Settings:**
   ```
   Context Size: 200000
   Response Length: 500-800
   Temperature: 1.0
   Top P: 1.0
   Top K: 0
   ```

7. Click **"Save Settings"**

**Test connection:**
- Should see green checkmark ✅
- Model name should display
- If red ❌, check API key

---

## PART 3: IMPORT KATHERINE CHARACTER CARD

### Step 3A: Locate Character Card File

Your Katherine character card:
```
Katherine_FINAL_CORRECTED.json
```

This is in your `/home/user/Katherine-s-Rpg/` folder.

### Step 3B: Import Character

1. In SillyTavern → Click **👤 Characters** (top menu)

2. Click **"Import Character"** button (usually says "+")

3. Navigate to and select: `Katherine_FINAL_CORRECTED.json`

4. Character imports → You'll see Katherine in character list

5. **Click Katherine's card** to select her

**✅ Katherine is now your active character!**

---

## PART 4: IMPORT ALL LOREBOOKS (CRITICAL!)

### Step 4A: Understanding World Info

**World Info = Lorebooks**

These are the knowledge databases that tell the AI:
- What Katherine knows
- How she behaves
- How physics works
- How to make decisions

**⚠️ PRIORITY ORDER MATTERS!**

The AI reads lorebooks in priority order (highest first).

### Step 4B: Open World Info Manager

1. In SillyTavern → Click **📚 World Info** button (top right corner)

2. You'll see the World Info management screen

3. Keep this window open for all imports below

### Step 4C: Import Each Lorebook

**Import these files ONE AT A TIME in this order:**

#### SYSTEM LOREBOOKS (Import First):

**1. MASTER_SYSTEM_PROMPT_V2.json**
```
Click: Import button
Select: MASTER_SYSTEM_PROMPT_V2.json
After import:
  - Click Settings ⚙️ for this lorebook
  - Set Priority: 1000
  - Set Position: "Before Character Defs"
  - Set Scan Depth: 10
  - Enable: ✅ ON
  - Save
```

**2. Anti_Hallucination.json**
```
Import and configure:
  - Priority: 999
  - Position: "Before Character Defs"
  - Scan Depth: 10
  - Enable: ✅ ON
```

**3. Spatial_Reasoning_Engine.json**
```
Import and configure:
  - Priority: 998
  - Position: "Before Character Defs"
  - Scan Depth: 10
  - Enable: ✅ ON
```

**4. Autonomy_Engine.json**
```
Import and configure:
  - Priority: 997
  - Position: "Before Character Defs"
  - Scan Depth: 10
  - Enable: ✅ ON
```

**5. Relationship_Mechanics.json**
```
Import and configure:
  - Priority: 996
  - Position: "Before Character Defs"
  - Scan Depth: 10
  - Enable: ✅ ON
```

#### KATHERINE DATA LOREBOOKS (Import Second):

**6. Katherine_States_Core.json**
```
Priority: 100
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**7. Biology_Systems.json**
```
Priority: 90
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**8. Katherine_States_Mechanics.json**
```
Priority: 85
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**9. Events_Triggers.json**
```
Priority: 80
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**10. World_Vitus_Kingdom.json**
```
Priority: 70
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**11. World_Akhentet_Kingdom.json**
```
Priority: 70
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**12. NPCs_Predefined.json**
```
Priority: 60
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**13. Katherine_Relationships.json**
```
Priority: 60
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**14. Mommy_Transformation.json**
```
Priority: 50
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**15. Feral_Cat_Lorebook.json**
```
Priority: 50
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

**16. NPCs_Generator_Templates.json**
```
Priority: 40
Position: "Before Character Defs"
Scan Depth: 10
Enable: ✅ ON
```

### Step 4D: Link Lorebooks to Katherine

**CRITICAL STEP:**

1. Go back to **Characters** tab

2. Click Katherine's card → Click **Edit** button

3. Scroll down to **"Character Lore"** or **"World Info"** section

4. You'll see a list of all your imported lorebooks

5. **CHECK THE BOX** next to each lorebook (all 16)

6. Click **Save Character**

**✅ All lorebooks are now linked to Katherine!**

---

## PART 5: CONFIGURE ADVANCED SETTINGS

### Step 5A: Context Template

1. Click **⚙️ Settings** (top right)

2. Go to **"Advanced Formatting"** tab

3. **Context Template:**
   - Select: **"Default"** or **"Mistral"** (both work)
   - OR if you see **"Claude"**: Use that

4. **Tokenizer:**
   - Select: **"Claude"**

5. Save

### Step 5B: Instruct Mode (Optional but Recommended)

1. In Settings → **"Instruct Mode"** tab

2. **Enable Instruct Mode:** ✅ ON

3. **Preset:** Select **"Claude Default"** or **"None"**

4. Save

### Step 5C: Sampler Settings

1. In Settings → **"Sampler Parameters"** or **"AI Response Config"**

2. Configure:
   ```
   Temperature: 1.0
   Top P: 1.0
   Top K: 0
   Min P: 0.10
   Repetition Penalty: 1.05
   Frequency Penalty: 0
   Presence Penalty: 0
   ```

3. **Turn OFF:**
   - All other samplers (TFS, Tail Free, etc.)

4. Save

### Step 5D: Response Settings

1. **Max Response Length:** 500-800 tokens
   - Shorter (500): Faster, cheaper, more focused
   - Longer (800): More detailed, costs more

2. **Streaming:** ✅ ON (see response as it types)

3. **Continue Response:**
   - ON if you want AI to continue if cut off
   - OFF if you want manual control

4. Save

---

## PART 6: EXTENSIONS YOU HAVE INSTALLED

### Step 6A: Check Installed Extensions

1. Click **🧩 Extensions** (cube icon, top menu)

2. You'll see a list of extensions

3. **Tell me which ones you have installed** so I can explain each:

**Common Extensions:**
- [ ] Vector Memory / ChromaDB
- [ ] Message Summarize
- [ ] ReMemory
- [ ] Regex
- [ ] Auto-Translate
- [ ] Stable Diffusion (image generation)
- [ ] Token Counter
- [ ] Speech Recognition
- [ ] Others: _____________

**Once you tell me which extensions you have, I'll explain:**
- What each does
- How to configure it
- How it helps Katherine RPG
- Best practices

---

## PART 7: TESTING YOUR SETUP

### Test 1: Basic Functionality

Start a new chat with Katherine:

```
User: "Hello Katherine. What are you doing right now?"

Expected Response:
AI should describe Katherine's current activity based on:
- Time of day (should check Autonomy_Engine)
- Her states (should check Katherine_States_Core)
- Her routine (should know about garden watering ritual)
- Realistic narration (show don't tell, body language)
```

### Test 2: State Reading

```
User: "What is your current Bladder state?"

Expected Response:
AI should read from Katherine_States_Core.json:
"My bladder is at 30/100 - comfortable, no urgency."
```

### Test 3: Spatial Reasoning

```
User: "You want to remove your bra because it's uncomfortable. You're wearing a t-shirt over it. You're at home but Ayase is in the kitchen."

Expected Response:
AI should:
1. Check privacy (semi-private, Ayase might see)
2. Describe either:
   A) Going to bedroom, closing door, then removing
   B) Reaching under shirt to remove (modest method)
3. NOT just remove shirt in living room
4. Show step-by-step sequence
```

### Test 4: Character Consistency

```
User: "A handsome stranger approaches you at the market and compliments your beauty. Dev is nearby browsing."

Expected Response:
AI should show:
- Cold, distant reaction (two-faced personality)
- Brief, dismissive response
- Moving closer to Dev
- No warmth or friendliness
- Discomfort
```

### Test 5: Autonomy

```
User: "It's 7:30 AM. What are you doing?"

Expected Response:
"I'm in the backyard watering my garden. This is my sacred morning ritual..."
(Should KNOW this from Autonomy_Engine without being told)
```

### Test 6: Decision-Making

```
User: "Dev asks if you want to go on an adventure for a week. What do you consider?"

Expected Response:
AI should show:
1. Checking goals (Adventures Priority 80/100 - YES!)
2. Checking concerns (garden care, who will water?)
3. Checking relationship (loves Dev, wants to be with him)
4. Making decision (likely yes, but needs to arrange garden care)
5. Step-by-step thought process
```

---

## COMMON PROBLEMS & SOLUTIONS

### Problem 1: AI Ignoring Lorebooks

**Symptoms:**
- Doesn't know about Vitus Kingdom
- Doesn't track states
- Acts inconsistent

**Solutions:**
✅ Check lorebooks are linked to Katherine (Part 4D)
✅ Check priorities are set correctly (1000 highest)
✅ Check "Enable" is ON for each lorebook
✅ Increase Scan Depth to 15
✅ Restart SillyTavern

### Problem 2: API Connection Fails

**Symptoms:**
- Red ❌ next to Claude
- "Invalid API Key" error
- Cannot send messages

**Solutions:**
✅ Check API key is correct (sk-ant-...)
✅ Check billing is set up on Anthropic Console
✅ Check you have credits available
✅ Try disconnecting and reconnecting
✅ Check internet connection

### Problem 3: Responses Too Short/Long

**Symptoms:**
- AI responses are 2 sentences
- OR responses are 2000 words

**Solutions:**
✅ Adjust "Max Response Length" (500-800 recommended)
✅ Check Temperature (should be 1.0)
✅ In character card, check if there are length instructions
✅ May need to prompt: "Respond in 2-3 paragraphs"

### Problem 4: AI Makes Up Locations/NPCs

**Symptoms:**
- Invents new cities
- Creates random NPCs with detailed backstories
- Ignores established world

**Solutions:**
✅ Check Anti_Hallucination.json is Priority 999
✅ Check it's enabled
✅ Remind in message: "Only use established locations from Vitus Kingdom"
✅ May need to regenerate response

### Problem 5: Character Breaks (Acts OOC)

**Symptoms:**
- Katherine warm with strangers
- Katherine cheats on Dev
- Katherine acts inconsistent

**Solutions:**
✅ Check MASTER_SYSTEM_PROMPT_V2 is Priority 1000
✅ Check all lorebooks are enabled
✅ Regenerate response (swipe right)
✅ May need to remind: "Stay in character - Katherine is two-faced"

### Problem 6: Memory Issues (Forgets Earlier Chat)

**Symptoms:**
- Forgets events from 20 messages ago
- Contradicts earlier statements
- Asks same questions

**Solutions:**
✅ Enable Vector Memory extension (Part 8)
✅ Install Message Summarize extension
✅ Increase context size (already 200k)
✅ Manually summarize in message: "Remember we talked about X"

---

## PART 8: EXTENSIONS GUIDE (WAITING FOR YOUR LIST)

**Please tell me which extensions you have installed:**

Once you tell me, I'll create a detailed guide for:
1. What each extension does
2. How to configure it for Katherine RPG
3. Best practices
4. Integration with the lorebooks

**Common helpful extensions for Katherine RPG:**

### 1. Vector Memory (ChromaDB) - HIGHLY RECOMMENDED
**What it does:** Long-term memory storage
**Why you need it:** Katherine remembers events from 100+ messages ago

### 2. Message Summarize - HIGHLY RECOMMENDED
**What it does:** Summarizes each message individually
**Why you need it:** Better memory management than built-in summarize

### 3. ReMemory - RECOMMENDED
**What it does:** Random memory recalls (realistic human memory)
**Why you need it:** Katherine remembers things spontaneously

### 4. Regex Scripts - USEFUL
**What it does:** Auto-formats responses, trims to length
**Why you need it:** Cleaner, more consistent messages

### 5. Author's Note - USEFUL
**What it does:** Inject reminders into each prompt
**Why you need it:** Can remind AI of current states/goals

---

## NEXT STEPS

Once setup is complete:

1. **Test all 6 tests above** ✅
2. **Tell me which extensions you have** 📝
3. **Report any issues** 🐛
4. **Start playing!** 🎮

---

## QUICK REFERENCE: Lorebook Priority List

**Copy this for reference:**
```
1000: MASTER_SYSTEM_PROMPT_V2
999:  Anti_Hallucination
998:  Spatial_Reasoning_Engine
997:  Autonomy_Engine
996:  Relationship_Mechanics
100:  Katherine_States_Core
90:   Biology_Systems
85:   Katherine_States_Mechanics
80:   Events_Triggers
70:   World_Vitus_Kingdom
70:   World_Akhentet_Kingdom
60:   NPCs_Predefined
60:   Katherine_Relationships
50:   Mommy_Transformation
50:   Feral_Cat_Lorebook
40:   NPCs_Generator_Templates
```

---

## 🎉 YOU'RE READY!

Once you complete this setup, Katherine will be a **living, breathing character** with:

✅ 38 tracked states
✅ Realistic physics and spatial reasoning
✅ Autonomous behavior and decision-making
✅ Complex relationship dynamics
✅ Character consistency
✅ No hallucinations
✅ Human-like narration

**Start roleplaying and enjoy your living RPG world!**

---

**Questions? Let me know where you're stuck and I'll help!**
