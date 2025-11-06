# AGENT CODING GUIDELINES

Last Updated: November 7, 2025

This repository contains a single Stylus-based UserCSS file. All modifications must adhere to the existing style and structure.

## 1. Build, Lint, and Test Commands

| Command | Description |
| :--- | :--- |
| **Lint** | `stylelint OpenAI-Gruvbox-Dark.user.css` (Recommended) |
| **Test** | None. Changes are verified visually on the target domain. |
| **Single Test** | N/A. |

## 2. Code Style and Conventions

### General Structure and Language
*   **Language:** Stylus is the required preprocessor (indicated by `@preprocessor stylus`).
*   **Formatting:** Use **4-space indentation**. Opening braces (`{`) must be on the same line as the selector.
*   **Specificity:** Use `!important` on almost every property to ensure overrides on the target site. Only omit it if the property is guaranteed to take effect without it.
*   **UserCSS Block:** Do not modify the `/* ==UserStyle== ... ==/UserStyle== */` block unless updating metadata or variables.

### Variables and Naming
*   **CSS Variables:** Use CSS variables (`--variable-name`) within `:root` blocks for defining colors, fonts, and other global values.
*   **Stylus Variables:** Use Stylus variables (`$variable-name = value`) for preprocessor logic and font aliases.
*   **Nesting:** Use Stylus nesting (`&:hover`, `&::before`, `.child-selector`) extensively for pseudo-classes and descendant selectors.

### Micro-interactions and Transitions
*   **Transitions:** All visual changes (color, background, transform) must be animated.
    *   **Timing:** Common timing functions are `ease-in-out` and `all 0.3s ease-in-out`.
    *   **Multi-property:** Use comma-separated transitions for multiple properties (e.g., `transition: background 0.6s ease-in-out, padding 0.22s ease-in-out`).
    *   **Cubic-Bezier:** Avoid complex `cubic-bezier` unless strictly necessary for a specific, non-standard effect.
*   **Hover Effects:** Implement subtle hover effects using the following properties:
    *   `transform`: Used for scaling (`scale(1.02)`) or slight movement (`translateY(-1px)`).
    *   `text-shadow`: Used to add a glow effect to text.
    *   `box-shadow`: Used to add depth or glow to elements.

### Typography and Font Rendering
*   **Font Smoothing:** Apply the following properties to text elements for a polished look:
    ```css
    -webkit-font-smoothing: antialiased !important;
    -moz-osx-font-smoothing: grayscale !important;
    text-rendering: optimizeLegibility !important;
    ```
*   **Font Usage:** Use the defined CSS variables (e.g., `var(--font-Jetbrains)`) for font-family declarations.

### Commit Message Style
*   **Format:** Use a concise, single-line subject. The format should be `type: subject`.
*   **Type:** Use conventional commit types (e.g., `feat`, `fix`, `chore`, `style`, `refactor`, `docs`).
*   **Subject:** Focus on the area of change and what was done (e.g., `The links text was too small fixed`).

### External Rules
*   **Rules:** No external Cursor or Copilot rules were found.
