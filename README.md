<div align="center">

# Slatewave (Alfred)

A Slatewave theme for [Alfred](https://www.alfredapp.com) — slate foundation, teal signature. Designed as a twin to the [Slatewave VSCode theme](https://github.com/kevinlangleyjr/vscode-slatewave), [Obsidian theme](https://github.com/kevinlangleyjr/obsidian-slatewave), and [oh-my-posh prompt](https://github.com/kevinlangleyjr/slatewave-omp) — editor, launcher, and notes share a single color vocabulary.

> _Slate below, teal above._

</div>

---

## What it styles

Slatewave for Alfred is a single `.alfredappearance` preset tuned against Alfred 5's full appearance schema. It sets:

- **Window** — slate `#282c34` at 90% opacity with a 20pt blur, so Alfred feels like a frosted pane of the Slatewave editor hovering above your desktop
- **Border** — slate-800 `#1e293b`, matching `editorGroup.border` in the VSCode theme
- **Search field** — 36pt System Light on a transparent background, `#e2e8f0` foreground, so the query text reads identically to the VSCode editor foreground
- **Selected result** — slate-700 `#334155` background with the title in teal `#5eead4`, mirroring VSCode's `list.activeSelectionBackground` / `list.activeSelectionForeground` pair
- **Unselected result** — slate-300 `#cbd5e1` title, slate-500 `#64748b` subtext, for a calm, low-fatigue read
- **Shortcut hint** — slate-500 `#64748b` → teal `#5eead4` on selection, echoing the accent bloom used in the VSCode activity bar
- **Scrollbar** — slate-600 `#475569` at 60% alpha, matching `scrollbarSlider.background`

---

## Installation

### Import the theme

1. Download [`Slatewave.alfredappearance`](./Slatewave.alfredappearance).
2. Double-click the file — macOS will hand it to Alfred, which opens **Settings → Appearance** with Slatewave pre-selected.
3. Click **Import** to confirm. Slatewave appears in your theme list.

### From a local clone

```sh
git clone https://github.com/kevinlangleyjr/alfred-slatewave
open alfred-slatewave/Slatewave.alfredappearance
```

Opening the file with Alfred running will offer to import it directly.

### Recommended appearance settings

The preset is self-contained, but these Alfred-wide settings pair well with it:

- **Settings → Appearance → Options** — enable _Hide hat on Alfred window_ for a cleaner top edge
- **Settings → Appearance → Options** — set _Show shortcuts_ to your preference; Slatewave's shortcut slot is tuned for visibility
- **Settings → Features → Default Results** — keep _Show subtext_ on; Slatewave styles the subtext slot as a faint slate-500 so it never competes with the title
- **macOS → System Settings → Displays** — Slatewave assumes a dark desktop. If you run Alfred over a light background, the 90% opacity window will pick up the underlying colors and the slate palette will read cooler

---

## Palette

Slatewave shares its palette with the companion themes. The anchor colors:

| | Hex | Tailwind | Role |
|---|---|---|---|
| ![#282c34](https://placehold.co/20x20/282c34/282c34.png) | `#282c34` | — | **window background** |
| ![#1e293b](https://placehold.co/20x20/1e293b/1e293b.png) | `#1e293b` | slate-800 | window border |
| ![#334155](https://placehold.co/20x20/334155/334155.png) | `#334155` | slate-700 | **selected result background** |
| ![#475569](https://placehold.co/20x20/475569/475569.png) | `#475569` | slate-600 | scrollbar |
| ![#64748b](https://placehold.co/20x20/64748b/64748b.png) | `#64748b` | slate-500 | subtext, unselected shortcut |
| ![#94a3b8](https://placehold.co/20x20/94a3b8/94a3b8.png) | `#94a3b8` | slate-400 | selected subtext |
| ![#cbd5e1](https://placehold.co/20x20/cbd5e1/cbd5e1.png) | `#cbd5e1` | slate-300 | unselected result title |
| ![#e2e8f0](https://placehold.co/20x20/e2e8f0/e2e8f0.png) | `#e2e8f0` | slate-200 | **search field text** |
| ![#5eead4](https://placehold.co/20x20/5eead4/5eead4.png) | `#5eead4` | teal-300 | **selected result title, selected shortcut** |

### Slot mapping

Mirrors the `list.*` / `editor.*` block from [vscode-slatewave](https://github.com/kevinlangleyjr/vscode-slatewave/blob/main/themes/slatewave-color-theme.json) so Alfred's row states line up with VSCode's file-tree selection states.

| Alfred slot | Color | VSCode analogue |
|---|---|---|
| `window.color` | `#282c34E6` | `editor.background` |
| `window.borderColor` | `#1e293bFF` | `editorGroup.border` |
| `search.text.color` | `#e2e8f0FF` | `input.foreground` / `editor.foreground` |
| `result.text.color` | `#cbd5e1FF` | `sideBar.foreground` |
| `result.text.colorSelected` | `#5eead4FF` | `list.activeSelectionForeground` |
| `result.backgroundSelected` | `#334155B3` | `list.activeSelectionBackground` |
| `result.subtext.color` | `#64748bFF` | `descriptionForeground` (faint) |
| `result.shortcut.colorSelected` | `#5eead4FF` | `list.highlightForeground` |
| `scrollbar.color` | `#47556999` | `scrollbarSlider.background` |

---

## Customize

`.alfredappearance` is plain JSON. To override a single slot without forking, open **Alfred → Settings → Appearance**, right-click **Slatewave → Duplicate Theme**, then tweak the copy via Alfred's UI — changes apply live and the original Slatewave stays pristine so future updates can be re-imported.

To fork the preset itself: open `Slatewave.alfredappearance` in any text editor. Every color is an `#RRGGBBAA` string (8-digit hex with alpha); every size is in points. The schema is flat — `alfredtheme.window`, `alfredtheme.search`, `alfredtheme.result`, `alfredtheme.separator`, `alfredtheme.scrollbar` — so edits are local and easy to diff.

---

## Companion themes

Slatewave is one palette, many surfaces. Run them together and your editor, terminal, launcher, and notes all speak the same visual language.

- **Editor** — [vscode-slatewave](https://github.com/kevinlangleyjr/vscode-slatewave)
- **Prompt** — [slatewave-omp](https://github.com/kevinlangleyjr/slatewave-omp)
- **Notes** — [obsidian-slatewave](https://github.com/kevinlangleyjr/obsidian-slatewave)
- **Terminal (Ghostty)** — [ghostty-slatewave](https://github.com/kevinlangleyjr/ghostty-slatewave)
- **Terminal (iTerm2)** — [iterm2-slatewave](https://github.com/kevinlangleyjr/iterm2-slatewave)
- **Terminal (Alacritty)** — [alacritty-slatewave](https://github.com/kevinlangleyjr/alacritty-slatewave)
- **Launcher (Alfred)** — this repo

---

## Contributing

Issues and PRs welcome. For palette changes, include a before/after screenshot of Alfred with the same query showing (a) an empty search, (b) a multi-row result list with at least one selected row, and (c) a row with subtext and a shortcut hint, so the visual tradeoff is obvious across all three states.

---

## License

WTFPL — Do What The Fuck You Want To Public License. See [LICENSE](LICENSE).
