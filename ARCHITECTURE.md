# vscode-theme/ARCHITECTURE.md

```sh
vscode-theme/
├── extension.ts                          # activate() → console.log only (minimal)
├── themes/
│   ├── yemreak.json                      # Dark theme
│   │   ├── colors                        # UI colors
│   │   │   ├── base: #202020             # Dark background (editor, panels, terminal)
│   │   │   ├── borders: #2c2c2c, #808080
│   │   │   ├── foreground: #c1c1c1       # Main text
│   │   │   ├── accents:
│   │   │   │   ├── primary: #E09440      # Orange (tabs, links, highlights)
│   │   │   │   ├── selection: #4A3018, #2E1F0F
│   │   │   │   ├── hover: #2A1C10
│   │   │   │   └── find: #FFA500        # Find/search highlights
│   │   │   └── cursor: #9CDCFE
│   │   └── tokenColors                   # Syntax highlighting
│   │       ├── functions: #F1BE34        # Yellow-gold
│   │       ├── classes: #eb9744          # Orange
│   │       ├── keywords: #B180D7         # Purple
│   │       ├── strings: #98C300          # Green
│   │       ├── constants: #588DCC        # Blue
│   │       ├── comments: #6b7992         # Gray-blue
│   │       ├── operators: #A3C3C7        # Cyan
│   │       ├── types: #E4BEDF, #C996A7   # Pink
│   │       └── variables: #c1c1c1        # Gray (italic)
│   │
│   └── yemreak-light.json                # Light theme
│       ├── colors                        # UI colors
│       │   ├── base: #FFFFFF, #F7F7F7    # Light backgrounds
│       │   ├── borders: #E6E6E6
│       │   ├── foreground: #3B3B3B, #878787
│       │   ├── accents:
│       │   │   ├── primary: #5C9FE8      # Blue (tabs, links, highlights)
│       │   │   ├── selection: #D0E8FF, #E5EBF1
│       │   │   ├── hover: #F2F2F2
│       │   │   └── find: #FFA500        # Find/search highlights
│       │   └── cursor: #3B3B3B
│       └── tokenColors                   # Syntax highlighting
│           ├── functions: #D7A10F        # Gold
│           ├── classes: #C1650B          # Orange
│           ├── keywords: #6D2CA0         # Purple
│           ├── strings: #9FCC00          # Green
│           ├── constants: #2A61A2        # Blue
│           ├── comments: #8B959E         # Gray
│           ├── operators: #4B7B81        # Teal
│           ├── types: #8A425A            # Mauve
│           └── variables: #3B3B3B        # Dark gray (italic)
│
└── package.json
    └── contributes.themes[2]
        ├── "Yemreak" → vs-dark → themes/yemreak.json
        └── "Yemreak Light" → vs → themes/yemreak-light.json
```

## Color Philosophy

**Dark theme**: High contrast with warm orange (#E09440) accents
- Background: Pure dark (#202020)
- Syntax: Vibrant colors (yellow functions, green strings, purple keywords)
- Highlights: Warm orange selections/focus

**Light theme**: Clean with cool blue (#5C9FE8) accents
- Background: Pure white + subtle gray (#F7F7F7)
- Syntax: Muted colors (gold functions, green strings, purple keywords)
- Highlights: Blue selections/focus

## Extension Behavior

`extension.ts` activates on `onStartupFinished` → logs activation message only
- No runtime features
- Pure theme contribution
- Minimal extension footprint
