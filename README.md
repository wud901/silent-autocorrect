# Silent Autocorrect

Word-style, real-time auto-correct for Obsidian, with an interactive status bar, a dictionary manager, toggleable clinical shorthands and medical sub-dictionaries. Fixes happen silently as you type, and one press of Backspace undoes any of them.

> **Desktop only.** Silent Autocorrect uses the status bar and Obsidian's built-in spellchecker, so it is marked desktop-only.

## Features

- **Status bar**
  - Live word and character counts with an estimated reading time.
  - `Add Word` button for one-click dictionary additions.
  - Auto-correct on/off pill.
  - Sensitivity pill: click to cycle Ultra, Proactive, Balanced, Strict and Minimal.
  - Sub-dictionary count: click to open the dictionary manager.
  - Session counter: click to revert the last correction.
  - Right-click the status bar for a quick menu.
- **Add words anytime**
  - Status bar button, left ribbon icon, or right-click a word in the editor.
  - Command palette: *Add word under cursor to dictionary*.
  - Dictionary manager: add single words, bulk-paste lists, and browse or remove custom words.
  - Plugin settings.
- **Clinical shorthands** (each individually toggleable): `pt` to `patient`, `hx` to `history`, `dx` to `diagnosis`, `tx` to `treatment`, `rx` to `prescription`, `sob` to `shortness of breath`, `prn` to `as needed` and more. Choose silent auto-correct or underline-only per shorthand.
- **Medical sub-dictionaries**: Cardiology and Pulmonology, Pharmacology, Surgery, Neurology, Pathology and Anatomy, each toggleable.
- **Sensitivity tiers**: Ultra (35%), Proactive (45%), Balanced (52%, the default), Strict (68%) and Minimal (verified fixes only).
- **Instant Backspace undo**: press Backspace right after a correction to restore what you typed.
- **Auto-corrections panel**: lists every silent fix, newest first, with its type (English, Medical, Shorthand, Case, Spacing), a confidence meter, the note it happened in, and a **Dict** button to add the original word to your dictionary. The last 200 fixes are kept; the bin icon clears them. Open it from the ribbon, the command palette (*Show auto-corrections panel*) or the status bar menu.

## Optional frequency dictionaries (network use)

Two English word-frequency files let the plugin tell real words from typos, pick the most likely fix (`hte` to `the`) and repair spacing (`ism y name` to `is my name`, `inthe` to `in the`, `wh at` to `what`).

Obsidian only installs `main.js`, `manifest.json` and `styles.css`, so these files are **downloaded on request**:

- The first time the plugin loads without them, it asks once whether to download them. Nothing is fetched unless you click **Download**.
- You can download (or re-download) them any time from **Settings, Silent Autocorrect, Frequency dictionaries**, or with the command *Download frequency dictionaries*.
- Source: `https://raw.githubusercontent.com/wolfgarbe/SymSpell/master/SymSpell/` (about 6.5 MB in total). The files are saved in the plugin's own folder.
- This is the plugin's only network access. No note content, vault data or analytics are ever sent.

Without these files the plugin still works using its built-in dictionaries.

## Privacy and data

- Everything runs locally. The plugin makes no network requests other than the optional download above.
- The auto-corrections panel history (original word, corrected word, confidence and the **title of the note** it happened in) is stored locally in the plugin's `data.json` inside your vault, together with your settings and custom words. Use the bin icon in the panel to clear the history.
- On desktop the plugin asks Obsidian's built-in Chromium spellchecker whether a word is misspelled (via Electron's `webFrame`). This stays on your machine and only works when *Settings, Editor, Spellcheck* is enabled.
- No ads, no telemetry, no account required.

## Medical disclaimer

Silent Autocorrect is a writing aid, not a clinical tool. Auto-expanded shorthands and corrected drug or condition names can be wrong. Always proofread anything used in clinical, legal or other safety-critical settings.

## Installation

### From Community Plugins (once approved)

1. In Obsidian, open **Settings, Community plugins**.
2. Turn off Restricted mode, choose **Browse**, search for **Silent Autocorrect**, then **Install** and **Enable**.

### Manual

1. Download `main.js`, `manifest.json` and `styles.css` from the latest GitHub release.
2. Create the folder `<your vault>/.obsidian/plugins/silent-autocorrect/` and copy the three files into it. The folder name must be `silent-autocorrect`.
3. Reload Obsidian and enable **Silent Autocorrect** under **Settings, Community plugins**.

## Credits and licenses

- Word-frequency data (`frequency_dictionary_en_82_765.txt`, `frequency_bigramdictionary_en_243_342.txt`) comes from [SymSpell](https://github.com/wolfgarbe/SymSpell) by Wolf Garbe (MIT License). Please see that repository for the data's own sources and licensing terms. The files are downloaded from there and are not redistributed in this repository.
- This plugin is released under the license in the `LICENSE` file.
