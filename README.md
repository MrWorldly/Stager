# 🧩 Stager (Beta 1)

**Author:** MrWorldly  
**Platform:** iPad (Stage Manager)  
**Version:** Beta 1  
**Tested on:** iPad Air 13” (2025), iPadOS 26  
**License:** MIT

---

## 🚀 What Is Stager?

**Stager** is a Shortcut-powered window manager for iPadOS 26, designed to automate app layout using Apple’s Stage Manager.  
It mimics the behavior of macOS tiling tools like yabai and Rectangle — but built entirely with Apple Shortcuts.

With Stager, you can:

- Define multiple **stages** (workspace layouts)
- Launch apps into specific positions using a JSON config
- Quickly switch between setups for work, meetings, personal use, and more

Stager is ideal for users who want **automated, repeatable window arrangements** on iPad — something not natively supported by iPadOS or third-party apps.

---

## ⚙️ Why Use Stager?

- 🧠 **No coding required** — just edit a JSON file  
- 🪟 **Automates window placement** — no manual dragging  
- 📚 **Supports multiple workspaces** — up to 10 tested  
- ⚡ **Fast execution** — no artificial delays  
- 🔁 **Selective stage reinitialization** — update only what you need

Unlike native apps, Shortcuts can launch apps but **cannot tile or reposition windows directly**. Stager works around this by chaining Shortcut actions and leveraging Stage Manager’s behavior.

---

## 📥 Installation

Download the Shortcut from [RoutineHub](https://routinehub.co/shortcut/23795/)
Once downloaded:

1. Open the `.shortcut` file in the Shortcuts app  
2. Grant necessary permissions (e.g., scripting, file access)  
3. Place your configuration files in:

```
iCloud Drive › Shortcuts › Stager › Stager.json
```

Also include `Stager Examples.json` for sample layouts.

---

## 🧭 How to Launch Stager

You can trigger the Shortcut using:

- **Home Screen / Dock**  
  - Add the Shortcut to your Home Screen  
  - Optionally drag it to the Dock for quick access

- **Control Center**  
  - Add the Shortcut to Control Center  
  - Launch it directly from there

These methods allow fast access without opening the Shortcuts app manually.

---

## ⚠️ Pre-Run Checklist

Before running Stager:

1. Ensure your iPad is toggling between **Full Screen Apps** and **Stage Manager**, not “Windowed Apps”  
2. If you previously used “Full Screen ↔ Windowed” mode, app positioning may break  
3. To reset:
   - Open a Full Screen app  
   - Activate Stage Manager via Control Center  
   - Confirm windows are grouped under stages  
   - Re-run Stager

---

## 🏎️ Performance Notes

Stager runs as fast as iPadOS allows — there are **no artificial delays**.  
Execution time depends on:

- Number of stages  
- Number of apps per stage  
- Device performance

To optimize speed, you can **select which stages to reinitialize**, avoiding full resets when unnecessary.

---

## 🧩 Configuration Guide

### File Location

```
iCloud Drive › Shortcuts › Stager › Stager.json
```

Include `Stager Examples.json` for reference layouts.

### Sample Configuration

```json
{
  "Options": {
    "SelectAllStagesOnStartup": "No",
    "NotifyWhenDone": "Yes"
  },
  "Stages": {
    "1 - Work": {
      "Apps": [
        { "Name": "Outlook", "WindowPosition": "Left" },
        { "Name": "Things", "WindowPosition": "Top Trailing" },
        { "Name": "Slack", "WindowPosition": "Bottom Trailing" }
      ]
    },
    "2 - Meetings": {
      "Apps": [
        { "Name": "Safari", "WindowPosition": "Right" },
        { "Name": "Notes", "WindowPosition": "Top Leading" },
        { "Name": "Zoom", "WindowPosition": "Bottom Leading" }
      ]
    }
  }
}
```

### Key Options

| Option                    | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| `SelectAllStagesOnStartup` | "Yes" → Pre-selects all stages when Shortcut runs; otherwise, manual selection |
| `NotifyWhenDone`         | "Yes" → Sends a local notification when setup completes                     |

### Stage Naming Tips

- Stager sorts stages alphabetically  
- To control order, prefix with numbers (e.g., `"1 - Work"`)  
- ⚠️ Avoid periods (`1. Work`) — may break parsing

---

## 📱 App Naming & Limitations

- App names must match **Spotlight search** or use **bundle identifiers** (e.g., `"com.apple.mobilesafari"`)  
- An app can only appear in **one stage** — last listed takes precedence  
- Apple Shortcuts **cannot open multiple windows** of the same app (e.g., two Files instances)

---

## 🧮 Supported Layouts

Known working positions include:

- `Left`, `Right`
- `Top`, `Bottom`
- `Top Leading`, `Top Trailing`  
- `Bottom Leading`, `Bottom Trailing`  
- `Left Third`, `Middle Third`, `Right Third`
- `Full Screen`
- `Center`

Other layouts may be possible depending on monitor size and Stage Manager behavior.  
If you discover new layout keywords, please share them for inclusion.

---

## 🚫 Limitations

- Stager **cannot detect current stage state**  
- Re-running the Shortcut will **reposition all windows**, even if already arranged

---

## ⌨️ Native iPadOS 26 Shortcuts

| Shortcut / Gesture             | Action                                     |
|-------------------------------|---------------------------------------------|
| Globe + Control + Left Arrow  | Move focused window to left side            |
| Globe + Control + Right Arrow | Move focused window to right side           |
| Globe + Control + Up Arrow    | Move focused window to top half             |
| Globe + Control + Down Arrow  | Move focused window to bottom half          |
| Globe + Control + C           | Center the focused window                   |
| Four-finger swipe left/right  | Switch between stages                       |

---

## 🖥️ External Monitor Support

Stage Manager doesn’t support multi-monitor control via Shortcuts.  
To migrate a stage to an external display:

1. Open the Dock on the external monitor  
2. Tap any app in the desired stage  
3. The stage will shift to that monitor

---

## 🧠 Inspiration: macOS Window Managers

| Tool       | Description                                      |
|------------|--------------------------------------------------|
| [yabai](https://github.com/koekeishiya/yabai)     | Scriptable tiling manager                         |
| [Amethyst](https://github.com/ianyh/Amethyst)     | Layout-based tiling manager                       |
| [Moom](https://9to5mac.com)                       | Visual layout and snapping tool                   |
| [Rectangle](https://www.howtogeek.com/fix-mac-window-management-with-these-apps/) | Popular free snapping/tiling tool                 |
| [Mosaic](https://macpaw.com/reviews/best-window-manager-mac) | Presets and custom layouts                        |

---

## 🤝 Contributing

I welcome:

- Bug reports  
- Feature suggestions  
- Layout discoveries  
- Configuration tips

Since Shortcuts aren’t collaboratively editable, please **describe your proposed changes clearly** so I can incorporate them manually.

---

## 📜 License

**MIT License** — Free to use, modify, and redistribute (including commercial use)  
Attribution required: *MrWorldly*  
No warranty provided. Use at your own risk.

---

## 🧪 Disclaimer

Tested only on:

- **iPadOS 26**  
- **iPad Air 13” (2025)**

Other devices or OS versions may behave differently.  
The author is not liable for any unintended effects, system issues, or data loss.
