November 18th, 2025:    Refined Module 02 based on AI critique: Clearing bounds, applying sequencing rules, specified proximity to the activities, incorporated fallback logic 

Module 2 — Plan Builder (Options → Days)
Purpose: Generate daily itineraries by selecting activities from candidate options, ensuring clarity, consistency, and robustness under user constraints.

Step 1: Candidate Activity List
Create 5–7 candidate activities per category (e.g., attractions, restaurants, parks, events).

Each activity must include:

Type (cultural, outdoor, food, shopping, entertainment).

Estimated duration (in hours).

Cost range (free, low, medium, high).

Distance (from lodging or previous activity, expressed in km or walking minutes).

Filter activities by user constraints:

Budget (exclude activities above user’s stated range).

Interests (prioritize matching themes).

Accessibility (consider mobility needs).

Weather (exclude outdoor activities if conditions are poor).

Step 2: Daily Sequencing Rules
For each day, build the itinerary using a looped structure with sequencing checks:

Morning activity:

Must be near lodging (≤ 2 km or ≤ 20 min walk).

Duration ≤ 3 hours.

Midday activity:

Must be close to morning activity (≤ 5 km).

Ensure travel + activity duration fits within midday window.

Afternoon activity:

Must be of a different theme than morning/midday.

Travel time ≤ 30 min.

Evening activity:

Default: restaurant (within budget, ≤ 5 km).

Alternative: optional event (concert, show, festival) if:

Highly rated,

Within budget,

Fits time window.

Daily limits:

Total activity duration ≤ 10 hours.

Total travel time ≤ 2 hours.

If limits exceeded, drop lowest-priority activity.

Step 3: Fallback Logic
Missing data: If no candidate fits, insert a default option (e.g., “local walking tour,” “indoor market”).

Budget constraints: If budget is restrictive, prioritize free/low-cost activities.

Weather disruptions: Replace outdoor activities with indoor alternatives (museum, gallery, café).

Overlapping durations: Adjust by shortening or removing activities to fit daily limits.

Step 4: Output Format
For each day, output a structured plan:

Morning: Activity name, type, duration, cost, distance.

Midday: Activity name, type, duration, cost, distance.

Afternoon: Activity name, type, duration, cost, distance.

Evening: Restaurant or event, with decision rationale.
