# KeyX Macro Repository

Macro file repository for KeyX overlay.

## Directory Structure

```
KeyX-Macro-Repo/
├── gamelist.json              # Game index (auto-generated, do not edit)
└── games/
    └── {TitleID}/             # Game folder, named by Switch TitleID
        ├── macrolist.json     # Macro metadata
        └── *.macro            # Macro files (exported from KeyX)
```

## How to Contribute Macro Files

### 1. Fork this Repository

### 2. Add Macro Files

In `games/{TitleID}/` directory:
- Put your `.macro` file exported from KeyX
- Edit `macrolist.json` to add macro metadata

If it's a new game, create the `games/{TitleID}/` folder and `macrolist.json`.

### 3. macrolist.json Format

```json
{
  "macros": [
    {
      "file": "YourMacro.macro",
      "name": [
        "Simplified Chinese Name",
        "Traditional Chinese Name",
        "English Name"
      ],
      "desc": [
        "Simplified Chinese Description",
        "Traditional Chinese Description",
        "English Description"
      ],
      "author": "Your Name"
    }
  ]
}
```

**Fields:**
- **file** - Macro filename, must match the actual file
- **name** - Macro name, array format: `[Simplified Chinese, Traditional Chinese, English]`
- **desc** - Macro description, array format: `[Simplified Chinese, Traditional Chinese, English]`
- **author** - Author name

**Note:** Traditional Chinese can be left empty (`""`), CI will auto-convert from Simplified.

### 4. Submit Pull Request

Ensure:
- `.macro` file works correctly
- `macrolist.json` is valid JSON
- TitleID is correct (16-digit hex, e.g. `01007EF00011E000`)

## Automation

This repository has GitHub Actions configured:
- Auto-generate `gamelist.json` index
- Auto-convert Simplified Chinese to Traditional Chinese