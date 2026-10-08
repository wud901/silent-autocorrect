# Medical & Smart Spellcheck (Auto-Correct) for Obsidian

A clinical and everyday writing plugin for Obsidian featuring **interactive UI, complete bottom status bar integration, and dictionary word management**.

## Key Features

- **Interactive Bottom Status Bar**:
  - Live metrics: `X words · X chars · ~X min read` (updates in real-time as you write).
  - `[+ Add Word]` button directly in the Obsidian bottom bar for 1-click word addition.
  - `[🟢 Auto-Correct: ON]` toggleable status pill with pulsing indicator.
  - `[⚡ BALANCED]` sensitivity pill (click to cycle Proactive → Balanced → Strict → Minimal).
  - `[📚 6 Sub-Dicts]` sub-dictionaries count pill (click to open Dictionary Manager).
  - `[↺ X fixed]` session counter (click to revert last correction).
  - `[✨ Clean]` status indicator.
  - Clicking/Right-clicking status bar opens quick menu for fast settings access.

- **Add Words to Dictionaries Anytime**:
  - **Status bar button**: Click `[+ Add Word]` on the bottom bar.
  - **Left Ribbon**: Click the book icon on the left ribbon.
  - **Editor Right-Click Menu**: Right-click any word → `Add to Medical Dictionary` → choose Cardiology, Pharmacology, Surgery, Neurology, Pathology, Anatomy, or Custom Words.
  - **Command Palette**: Run `Medical Spellcheck: Add word under cursor to dictionary`.
  - **Dictionary Manager Modal**: Add words individually, paste bulk lists, or browse/delete added words.
  - **Settings Tab**: Form to add words and manage custom wordlists.

- **Toggleable Clinical Shorthands**:
  - Individually enable abbreviations like `pt` → `patient`, `hx` → `history`, `dx` → `diagnosis`, `tx` → `treatment`, `rx` → `prescription`, `sob` → `shortness of breath`, `prn` → `as needed`.
  - Choose between **Silent Auto-Correct** (expands on space) or **Underline Mode** (manual review).

- **Medical Sub-Dictionaries**:
  - Toggle specific specialties: *Cardiology*, *Pharmacology*, *Surgery*, *Neurology*, *Pathology*, *Anatomy*.

- **Sensitivity Controls**:
  - 5 tiers: Ultra (35% - fastest), Proactive (45%), Balanced (52% - Word default), Strict (68%), Minimal (Verified Only).

- **Instant Backspace Undo**:
  - If you dislike an auto-correction, pressing Backspace immediately after restores what you typed.

## Frequency Dictionary & Split/Merge Fixes (optional)

Put these two files in the plugin folder next to `main.js` (SymSpell English data):

- `frequency_dictionary_en_82_765.txt` - lets the plugin tell real words from typos and pick the most likely fix (`hte` -> `the`), even without Obsidian's spellcheck.
- `frequency_bigramdictionary_en_243_342.txt` - enables spacing fixes: `ism y name` -> `is my name`, `inthe` -> `in the`, `wh at` -> `what`.

Both load in the background at startup; without them the plugin behaves as before. Toggle them under Settings -> Use frequency dictionary / Fix split and merged words (the settings page also shows what loaded).

## Auto-corrections Panel

Open it from the left ribbon (spell-check icon), the command palette (*Show auto-corrections panel*) or the status-bar right-click menu. It lists every silent fix, newest first, with its type (English, Medical, Shorthand, Case, Spacing), a confidence meter, the note it happened in, and a small **Dict** button that adds the word you originally typed to your dictionary so it's never corrected again. The last 200 fixes are kept; the bin icon clears them.

## Installation

1. In Obsidian, open **Settings** → **Community Plugins**.
2. Turn OFF **Restricted mode**.
3. Click the folder icon next to "Installed plugins" to open `.obsidian/plugins/`.
4. Create a folder named `obsidian-medical-autocorrect`.
5. Place `manifest.json`, `main.js`, and `styles.css` in that folder (plus the two optional frequency files above).
6. Click **Reload plugins** in Obsidian and toggle **Medical & Smart Spellcheck** ON!
