Part 1: Project Ideas
Prompt Used
"I am working on a Python project to create a simple AI system based on rules or heuristics. This is for an assignment where I need to understand how AI worked before machine learning. Could you suggest some project ideas for a rule-based AI system? Please include examples like chatbots, recommendation systems, or diagnostic tools."

Idea 1 — Esoteric Journal & Dream Interpretation System
•	What it does: The user types a dream or journal entry and the system identifies symbolic themes (water, fire, shadow, love, journey, etc.) and returns matching tarot cards, astrological correspondences, esoteric guidance, and a journaling prompt.
•	How it uses rules: IF the input contains words like 'ocean', 'river', or 'swim' → THEN activate the WATER theme and return The Moon tarot card, Neptune/Pisces astrology, and corresponding guidance.

Idea 2 — Troubleshooting Diagnostic Assistant
•	What it does: The user describes a problem with a device (laptop, phone, etc.) and the system walks them through troubleshooting steps based on keyword matching.
•	How it uses rules: IF the user mentions 'won't turn on' → THEN suggest checking the power source. IF 'overheating' → THEN suggest cleaning vents and checking background processes.

Idea 3 — Recipe Recommendation System
•	What it does: The user enters ingredients they have available and the system suggests recipes that match, using predefined ingredient-to-recipe mappings.
•	How it uses rules: IF user has 'eggs', 'flour', and 'milk' → THEN suggest pancakes or crepes. IF 'tomato' and 'pasta' → THEN suggest marinara.

Selected Idea & Justification
I chose the Esoteric Journal & Dream Interpretation System because it connects directly to a Lucid atlas project I am building — a visual esoteric journaling app that maps tarot, astrology, numerology, chakras, and symbology. The rule-based system acts as the interpretive engine for that app, giving it a functional AI-like layer without machine learning. It also felt like the most personally meaningful project to develop, which made the design and coding process more engaging.

Part 2: Rules & Logic Design
Prompt Used
"I want to create an esoteric journal and dream interpretation system that combines tarot, astrology, and symbolism. The system will be rule-based. Can you help me outline the rules and logic needed to make this work? What conditions or keywords should I check for, and what responses or actions should my system take?"

IF-THEN Rule Structure
Step 1 — Ask the user whether they are sharing a dream or a journal entry.
•	IF input is '1' → THEN activate Dream mode
•	IF input is '2' → THEN activate Journal Entry mode
•	IF anything else → THEN default to Journal Entry mode

Step 2 — Receive the user's text and scan for symbolic keywords.
•	IF input contains 'water', 'ocean', 'river', 'rain', 'flood', 'swim', 'wave', 'drown', 'sea', or 'lake' → THEN activate WATER theme
•	IF input contains 'fire', 'flame', 'burn', 'candle', 'sun', 'spark', 'heat', or 'blaze' → THEN activate FIRE theme
•	IF input contains 'dark', 'shadow', 'fear', 'chase', 'lost', 'trap', 'hide', or 'nightmare' → THEN activate SHADOW theme
•	IF input contains 'birth', 'new', 'spring', 'seed', 'bloom', 'transform', 'butterfly', or 'awaken' → THEN activate REBIRTH theme
•	IF input contains 'love', 'heart', 'rose', 'kiss', 'embrace', 'longing', 'desire', or 'union' → THEN activate LOVE theme
•	IF input contains 'road', 'path', 'travel', 'door', 'bridge', 'map', 'direction', or 'walk' → THEN activate JOURNEY theme
•	IF input contains 'death', 'dead', 'grave', 'coffin', 'ghost', 'funeral', or 'tomb' → THEN activate DEATH theme
•	(Additional themes: EARTH, AIR, LIGHT follow the same pattern)
•	IF no keywords match → THEN return a neutral reading (The Hanged Man — pause and stillness)

Step 3 — For each activated theme, output:
•	The associated Tarot card and its meaning
•	The astrological correspondence (planet, sign, house)
•	An esoteric guidance message
•	A personalized journaling prompt

Step 4 — Ask if the user wants to continue or exit.
•	IF yes → THEN return to Step 1
•	IF no → THEN print a farewell message and exit

Part 3: Test Results
Test Input 1 — Dream: Water & Shadow
Entry type: Dream
Input: "I was swimming in a dark ocean and the waves were pulling me under. There was a shadow following me but I couldn't see its face."

Detected themes: WATER, SHADOW
WATER → Tarot: The Moon | Astrology: Neptune / Pisces / Cancer
        Guidance: Your subconscious is speaking. A time for emotional honesty.
        Prompt: Write about an emotion you have been avoiding.
SHADOW → Tarot: The Tower / The Devil | Astrology: Pluto / Scorpio
         Guidance: Something from the shadow self is asking to be seen.
         Prompt: What part of yourself do you keep hidden?

Test Input 2 — Journal Entry: Fire, Shadow & Rebirth
Entry type: Journal Entry
Input: "I feel like I am finally burning away the old version of myself. Something new is being born from the ashes. I watched a candle tonight and felt the spark of transformation."

Detected themes: FIRE, SHADOW, REBIRTH
FIRE    → Tarot: The Sun / The Emperor | Astrology: Mars / Aries / Leo
          Guidance: A spark of transformation is alive in you.
SHADOW  → Tarot: The Tower / The Devil | Astrology: Pluto / Scorpio
          Guidance: Something from the shadow self is asking to be seen.
REBIRTH → Tarot: Judgement / The World | Astrology: Uranus / Pisces / Aries
          Guidance: Transformation is underway. Trust the process.

Test Input 3 — Dream: Love & Journey
Entry type: Dream
Input: "I dreamed I was walking a long path through a rose garden looking for someone I loved. There was a bridge ahead but I couldn't reach it."

Detected themes: LOVE, JOURNEY
LOVE    → Tarot: The Lovers / Two of Cups | Astrology: Venus / Libra / 7th House
          Guidance: The heart is at the center of this dream.
          Prompt: What does your heart most deeply want right now?
JOURNEY → Tarot: The Chariot / The Fool | Astrology: Jupiter / Sagittarius
          Guidance: Your soul is on the move.
          Prompt: If your life were a story, what chapter are you in now?

Part 4: Reflection
How the System Works
The Esoteric Journal & Dream Interpretation System is a rule-based AI that uses keyword pattern matching to analyze user-submitted text. The system stores ten symbolic theme dictionaries: Water, Fire, Earth, Air, Shadow, Light, Death, Rebirth, Love, and Journey,  each containing a list of associated words. When the user types a journal entry or dream description, the program iterates through every keyword in every theme dictionary. If any keyword is found in the user's lowercased input, that theme is flagged as active. This implements the core rule-based heuristic: IF keyword present THEN activate theme.

Once all active themes are identified, the system consults three additional lookup tables — one for tarot correspondences, one for astrological associations, and one for esoteric guidance text, and prints a complete reading for each theme. A final lookup provides a personalized journaling prompt per theme. If no keywords are detected at all, the system falls back to a neutral "The Hanged Man" reading that encourages stillness and reflection, representing the rule: IF no match THEN return default output.

The system also uses a simple entry-type selector at the start of each loop (IF '1' → Dream mode, IF '2' → Journal mode) that adjusts the prompt language but not the core logic. Multiple themes can be detected from a single entry, making the system capable of compound readings that reflect the layered nature of symbolic interpretation.

Challenges Encountered
One of the main challenges was working with an AI assistant to design the keyword libraries, the AI would often suggest very broad or generic terms that could trigger false positives. For example, the word 'new' was included in the REBIRTH theme, but it also appears constantly in everyday language ('new day', 'new shoes') where it has no symbolic meaning. Balancing keyword sensitivity (catching real symbolic content) against specificity (avoiding noise) required several rounds of refinement.

Another challenge was prompting the AI to generate guidance text that felt genuinely esoteric and not generic. Early iterations produced bland responses like 'trust your emotions' that could apply to anything. I had to push the AI to anchor each piece of guidance in a specific symbolic tradition, water to Neptune and Pisces, shadow to Plutonian transformation, to make the output feel intentional and connected to the broader esoteric framework I am building in my Lucid atlas project.

Finally, handling multi-theme entries was trickier than expected. The AI initially suggested using only the 'most prominent' theme, but a single dream can meaningfully embody fire AND rebirth AND shadow simultaneously. Redesigning the logic to support compound readings and formatting the output so multiple themes don't feel cluttered, was a valuable lesson in thinking beyond binary IF-ELSE logic toward layered heuristic systems.
