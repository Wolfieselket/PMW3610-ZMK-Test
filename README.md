# Wolfie Keymap Editor — installation

This adds a **provisional** 44-key Piantor-inspired visual layout for Nick Coutsos’ ZMK Keymap Editor. It does not change firmware or key assignments.

1. Back up the working dual-display firmware first (planned checkpoint: `working-complete-dual-displays`).
2. Add `config/wolfie_split.json` to `Wolfieselket/Wolfie-Split-Trackball-ZMK` on a safe test branch (or on `main` after backup). Do not rename `config/wolfie_split.keymap` or alter custom display module files.
3. Open https://nickcoutsos.github.io/keymap-editor/ and use the GitHub source to connect the repository; choose `wolfie_split.keymap`.
4. Confirm all 44 keys appear in the right order (12 + 12 + 12 + 8). Change a harmless key binding, preview and review the diff; don't flash until builds succeed.
5. Exact thumb positions and stagger in this file are illustrative; they can be adjusted without changing the key bindings.

Key binding order from the existing `config/wolfie_split.keymap`:
- Top: 6 left + 6 right
- Home: 6 left + 6 right
- Bottom: 6 left + 6 right
- Thumbs: 4 left + 4 right

The `row` and `col` fields in this JSON are logical positions used for editor formatting, not the actual GPIO scan row/column pairs in the ZMK matrix transform.

Existing `wolfie_split.keymap`: QWERTY and Function layers. Right central + PMW3610 + eye; left peripheral + static space display.

Reference: https://github.com/nickcoutsos/keymap-editor/wiki/Defining-keyboard-layouts
