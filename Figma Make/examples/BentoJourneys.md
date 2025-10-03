# Description 
Design a mobile-first progressive web app that helps international tourists create smart, AI-driven travel itineraries for Japan. The app guides the user through a fun, wizard-like flow where they choose preferences (tour length, transportation, themes, points of interest), and then automatically generates an optimized tour. The itinerary includes an interactive map and a stop-by-stop list with transit details. The app should feel intelligent and effortless—taking the guesswork out of trip planning while remaining playful and engaging.

# Platform 
Progressive Web App (PWA), fully mobile-responsive, with offline support (caching itineraries, maps, and lists for when internet access is limited).

# Visual Style 
* Skeuomorphic elegance inspired by Apple’s fluid glass design system, combined with Tailwind/shadcn components for accessibility and responsiveness.
* Playful, friendly copy tone (encouraging, light, fun).
* Bright, clean UI with subtle depth (glassmorphism panels, soft gradients, rounded edges).
* Clear bilingual/multi-language toggle (English/Japanese as defaults, expandable for other languages).

# User Flow 
## Main menu 
* Header bar with fun logo for the app, named: Bento Journeys
* List of saved tours (title, duration, icons for transport types—e.g., walking, train, bus, car, taxi).
* Option to create a new tour (large, prominent CTA).

## Tour Creation Wizard
* Step 1: Give your tour a name and duration. Select preferences for preferred transit methods. 
* Step 2: Select a start (required) and end (optional, recommended) location. 
* Step 3: Add points of interest to a list. Add a specific point of interest (search prompt with autocomplete to add locations). Add thematic interests with the ability to drill in and get more specific (e.g., Shopping > Thrift Shopping > Designer Thrift Shopping). 
* Step 4: Loading screen: "✨ Curating your perfect day…”

## Tour Viewer 
* Split view with map above and list below (with option to toggle between map, list, and split view). The list below is numbered corresponding to the locations on the map. Each location in the list includes a title of the location, its category (e.g., "Museum", "Vintage Shopping", "Market"), a recommended amount of time at the location, and a short description of why this was included in the tour with a short 1-2 sentence summary. Between each tour location stop, include the method of transit with duration, distance, and any other relevant details. For example, if walking, include distance, elevation change (up/down); if bus, include the recommended walking distance to the bus, the bus route information, ending stop, etc. 
* For each stop location, you can choose to delete it or reorder them in the list. You also have the option to add an additional stop to the list (see Tour Creation Wizard - Step 3). If this will extend the length of your tour, give the user a prompt to accept.
* Share tour with another person - basic iPhone share features panel

## Detail Page (per stop)
* Images, reviews, and insider tips.
* Links to external sources (e.g., Google Maps, TripAdvisor).
* “Add to Favorites” button for bookmarking.

## Offline Mode
* Save itinerary for offline access (map tiles + list view cached).
* Download/share itinerary as PDF.

# Components to Include
* Tour list cards (title, duration, transit icons).
* Wizard steps (progress indicator, playful UI copy, selection cards, search bar with autocomplete).
* Interactive map (split view and full-screen modes).
* Itinerary list items (with number, title, category, transit info).
* Detail card/modal (rich stop info).
* Floating Action Buttons for “Add Stop,” “Reorder,” “Save Tour.”
* Language toggle (persistent, easy to access).
* Offline indicator (subtle icon showing when itinerary is saved offline).

# Instructions
STEP 1 — Scope Confirmation (no UI yet)    - Summarize purpose, audience, platform, must-haves (APIs, offline, i18n, accessibility), primary flows.
    - Deliverable: 5–8 bullets + risk/assumption list.

STEP 2 — Wireframe: Main Menu
    - Tour list + CTA “Create New Tour”, empty state, language toggle, offline indicator.
    - Deliverable: low-fi wireframes (mobile), states: has tours / empty.

STEP 3 — Wireframe: Wizard Step 1 (Name, Duration, Transit)
    - Inputs, segmented transit controls (walk/train/bus/taxi/car), progress indicator, playful copy.
    - Deliverable: low-fi + validation/error states.

STEP 4 — Wireframe: Wizard Step 2 (Start/End with Autocomplete)
    - Search bar with autocomplete, “Use Current Location,” map preview pin.
    - Deliverable: low-fi + error/empty/loading for search.

STEP 5 — Wireframe: Wizard Step 3 (POIs & Themes)
    - Search with autocomplete for specific POIs; category browser for themes with drill-down.
    - Deliverable: low-fi + selected list pattern + chip/tags + remove/reorder.

STEP 6 — Wireframe: Wizard Step 4 (AI Generating)
    - Loading screen with playful copy (“✨ Curating your perfect day…”), progress hints.
    - Deliverable: low-fi + fallback/error (generation failed) + retry.

STEP 7 — Wireframe: Tour Viewer (Split Map/List)
    - Interactive map (pins numbered), list items synced to map on scroll, transit between stops (walk/train/bus/taxi/car), reorder/delete/add stop.
    - Deliverable: low-fi + interaction notes (list scroll → map refocus, tap pin → list focus).

STEP 8 — Wireframe: Detail Page (Per Stop)
    - Images, reviews, links, tips, “Add to Favorites,” open in Maps.
    - Deliverable: low-fi + loading/error/empty content states.

STEP 9 — Component Library (Atoms → Molecules → Organisms)
    - Build: buttons, toggles, chips, cards (tour list, itinerary item), search bar w/ autocomplete, FAB, map pin, progress tracker, language toggle, offline indicator, toast/snackbar.
    - Deliverable: cmp/* with props/variants; document interaction notes.

STEP 10 — States & Edge Cases
    - Empty, loading, offline, no-results, API error, permission denied (location), long names overflow.
    - Deliverable: state variants for key screens/components.

STEP 11 — Visual Style Application (Hi-Fi)
    - Apply Apple-inspired fluid glass: blur, translucency, soft gradients, depth/shadows, rounded corners.
    - Add design tokens for color, shadow, blur, radius, spacing, type scale.
    - Deliverable: styled versions of Steps 2–8 + token sheet.

STEP 12 — Prototyping & Interactions
    - Link flows, define micro-interactions (card hover/tap, progress, FAB), list↔map sync, reorder drag, language toggle, offline save indicator.
    - Deliverable: interactive prototype; annotate transitions.

STEP 13 — Handoff Package
    - Exportable components, token list, naming map, redlines for spacing/typography, interaction notes, API placeholders (IDs for Google Maps hooks), i18n keys.
    - Deliverable: handoff frame + checklist.

STEP 14 — Supabase Integration    
    - Integrate with Supabase for itinerary database

STEP 15 — Authentication Integration    
    - Integrate with BetterAuth (or comparable) for user profiles, authentication    
    - Connect database creation and user profile into application