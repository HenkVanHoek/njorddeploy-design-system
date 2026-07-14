# NjordDeploy Design System 🎨

Welcome to the **NjordDeploy Design System**. This repository serves as the **Single Source of Truth (SST)** for the user interface styles, fonts, and brand assets used across the entire NjordDeploy ecosystem (including the Configurator App, Editor App, and public landing page).

The design system implements a **Futuristic Glassmorphic Theme** featuring elegant gradients, translucent panel designs, subtle micro-animations, and vibrant accents tailored for self-hosted home server dashboards.

---

## 🚀 Key Features

* **Glassmorphic Cards & Containers:** Sleek, semi-transparent backgrounds using `backdrop-filter: blur()`.
* **Futuristic Palette:** Deep space dark mode base with vivid neon violet, electric cyan, and clean emerald status highlights.
* **Modern Typography:** Standardized clean sans-serif font stack prioritizing screen readability.
* **Responsive Layouts:** Built-in mobile-friendly layout grid rules.
* **Asset Repository:** Hosts official graphics, logos, and high-fidelity icons.

---

## 📁 Repository Structure

```
njorddeploy-design-system/
├── css/
│   └── njorddeploy-style.css    # The master stylesheet (Single Source of Truth)
├── images/
│   └── njorddeploy-icon192x192.png # Official NjordDeploy logo asset
├── style_guide.html             # Interactive HTML guide to preview component styles
└── README.md
```

---

## 🛠️ Viewing the Style Guide Locally

You can preview the components and styling rules by opening the `style_guide.html` file in any modern web browser.

To open it from the command line:
* **Linux:** `xdg-open style_guide.html`
* **macOS:** `open style_guide.html`
* **Windows (WSL/cmd):** `start style_guide.html`

The style guide serves as an interactive playground showcasing buttons, forms, badges, modals, status indicators, and grid layouts.

---

## 🔄 Synchronization Workflow

To ensure styling consistency, the master style file must never be edited directly within individual applications. Always follow the sync pipeline:

### 1. Modify Styles
Make your edits directly to the CSS file inside this design system repository:
* Edit [css/njorddeploy-style.css](css/njorddeploy-style.css).
* Verify changes using the local `style_guide.html`.

### 2. Push Changes
Commit and push the styling updates to GitHub:
```bash
git add .
git commit -m "style: update card border radius and button hover shadows"
git push origin main
```

### 3. Fetch in Applications
Run the asset sync script in the main NjordDeploy project directory to pull the latest styles:
```bash
python scripts/fetch_assets.py
```
This script downloads the updated CSS and logo files directly from the design system's raw GitHub URLs and saves them to the application's static assets directory.

---

## 📝 Design Tokens & Guidelines

### Colors
* **Primary Deep Background:** Dark cosmic blues and deep grays.
* **Card Backing:** `rgba(255, 255, 255, 0.05)` with `backdrop-filter: blur(12px)`.
* **Accent Neon:** Electric Violet (hover effects) and Neon Teal (actions/active states).

### Layout & Borders
* **Card Border Radius:** Standardized `12px` or `16px`.
* **Borders:** Subtle `1px solid rgba(255, 255, 255, 0.1)` to define translucent cards against dark background gradients.