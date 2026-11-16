# Café

A warm espresso dark theme for Atlas: espresso grounds, cream text and state colors tuned to sit on that dark.

![Atlas with Café: a conversation with tool calls and a code diff](screenshots/chat.png)

In the app's settings it is called **Coffee** in English and **Café** in Portuguese.

## Before and after

The same conversation in Atlas's default dark look and in Café. The layout does not move;
only the colors change.

| Atlas, dark (default) | Atlas, Café |
|---|---|
| ![Atlas with its default dark look](screenshots/default-dark.png) | ![Atlas with Café](screenshots/chat.png) |

The four states keep one meaning each and stay readable on the dark: working, waiting for you,
done and failed.

![A conversation waiting for approval, with a finished and a failed tool call, and another conversation still working](screenshots/states.png)

## What it changes, and what it doesn't

**Changes**

- All 27 named colors Atlas paints with: grounds, text, lines, focus ring, actions, states, and
  added and removed lines.

**Doesn't change**

- Layout, fonts, sizes or spacing.
- Native form controls and scrollbars: the theme sits on `dark`, so they keep their dark variants.
- Your files, settings or other plugins: it only adds a choice to **Look**.

## Install

1. Open **Marketplace** in Atlas, find **Café** under Plugins and press **Install**.
2. Turn it on under **Plugins**. The consent shows one line: it adds a theme, and nothing that runs.
3. Choose **Coffee** in **Settings > General > Look**, beside the system's, Light and Dark.

![Settings, General, Look: the system's, Light, Dark and Coffee, with Coffee chosen](screenshots/settings.png)

From a terminal, steps 1 and 2 are:

```bash
atlas marketplace install cafe
atlas plugins enable cafe
```

Needs Atlas with plugin SDK version 24 (`atlas.api` 24) or later, the version that lets a plugin
bring themes.

## Safety

It brings one file, [`themes/cafe.json`](themes/cafe.json): a hex color for every one of the
app's named colors, on top of the app's dark look. Nothing else.

- **It runs no code.** No Python, no screen, no hooks, no tools, no scripts.
- **It reaches no network** and reads no secret.
- **It touches nothing outside its own folder.**
- **It cannot paint anything but the app's named colors.** Atlas refuses a theme that names any
  other variable or holds anything that is not a hex color, so a theme is data and cannot carry a
  URL or a style rule.

If you turn the plugin off, the app goes back to the system's look and keeps your choice for when
the plugin is on again.

## Palette

![The Café palette: background, sidebar, dialogs, chips, selected, text, and the four states](screenshots/palette.png)

Atlas paints every screen with 27 named colors and no others; this theme sets each of them, so
nothing falls back to the default dark look.

**Grounds**

| Name | Color |
|---|---|
| `background` | `#1a1714` |
| `subtle` | `#211d19` |
| `raised` | `#24201b` |
| `muted` | `#2b2620` |
| `hover` | `#302a23` |
| `selected` | `#3a3229` |
| `scrim` | `#00000099` |

**Text**

| Name | Color |
|---|---|
| `foreground` | `#ece4d4` |
| `soft` | `#c9bfac` |
| `muted-foreground` | `#a89f8d` |
| `faint` | `#6f675a` |

**Lines and focus**

| Name | Color |
|---|---|
| `border` | `#352f27` |
| `border-strong` | `#4a4237` |
| `ring` | `#a89f8d` |

**Actions**

| Name | Color |
|---|---|
| `primary` | `#ece4d4` |
| `primary-foreground` | `#1a1714` |

**States**

| Name | Color |
|---|---|
| `working` | `#7aaee8` |
| `waiting` | `#e0a73c` |
| `waiting-text` | `#f0c36e` |
| `waiting-foreground` | `#2a1d05` |
| `done` | `#4fb3a6` |
| `done-text` | `#7fd1c5` |
| `failed` | `#e26a5c` |
| `failed-text` | `#f29a8f` |
| `danger` | `#e26a5c` |
| `added` | `#4fb3a6` |
| `removed` | `#e26a5c` |

### Contrast

Every text color is at least 4.5:1 (WCAG AA) on the four grounds a screen draws text on. The ratios
below were computed from the hex values with the WCAG relative-luminance formula; `foreground` on
`background` reaches 14.1:1.

| Text color | on `background` | on `subtle` | on `raised` | on `muted` |
|---|---|---|---|---|
| `foreground` `#ece4d4` | 14.1 | 13.2 | 12.8 | 11.9 |
| `soft` `#c9bfac` | 9.8 | 9.2 | 8.9 | 8.2 |
| `muted-foreground` `#a89f8d` | 6.8 | 6.4 | 6.2 | 5.7 |
| `working` `#7aaee8` | 7.7 | 7.2 | 7.0 | 6.5 |
| `waiting-text` `#f0c36e` | 10.8 | 10.2 | 9.8 | 9.1 |
| `done-text` `#7fd1c5` | 10.1 | 9.4 | 9.1 | 8.4 |
| `failed-text` `#f29a8f` | 8.3 | 7.8 | 7.5 | 7.0 |

`faint` only decorates (a chevron, a dot at rest, a word that cannot be used, as Atlas defines it)
and is 3.2:1 on `background` on purpose. `ring`, the keyboard's place, is
6.8:1. `border` and `border-strong` are edges, not text, at
1.3:1 and 1.8:1.

## Design

- **Warm neutrals.** Every ground leans brown instead of grey: `background` is `#1a1714`, the
  sidebar a step lighter, and dialogs and fields another step (`raised`), so depth reads as
  layers of roast.
- **Cream, not white.** Text is `#ece4d4`, a warm cream that sits softer on espresso than pure
  white.
- **States stay legible.** Blue, amber, green and red keep one meaning each; their `-text`
  variants are lifted until they read as words on the dark.

## Develop

```bash
atlas plugins validate cafe     # loads it as Atlas does and says what is wrong
```

The folder name must equal the plugin's `name`, as Atlas requires. To try a change, copy the folder
into your home's `plugins/`, run `atlas plugins enable cafe`, and pick the theme in Settings.

## Changelog

See [CHANGELOG.md](https://github.com/JoaoEquer/atlas-cafe/blob/main/CHANGELOG.md).

## License

MIT, see [LICENSE](LICENSE).
