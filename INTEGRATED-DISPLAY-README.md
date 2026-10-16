# Right-half keys + PMW3610 + static nice!view test

This adds one new GitHub Actions build to the previously working right-half AltGr firmware:

- `right_half_keys_trackball_eye` — real 4x6 matrix, existing PMW3610 pointing overlay, and `nice_view_adapter wolfie_niceview` custom screen.
- `right_half_custom_default_trackball` — prior keyboard + sensor build retained as fallback.
- `wolfie_right_eye` — original display-only test retained as fallback.

The new build reuses the static display code from `Wolfieselket/wolfie-niceview` at `main` (via `config/west.yml`). It does not add animation or alter its drawing code.

## Install / test

1. Upload extracted files to the root of your existing PMW3610-ZMK-Test GitHub repo, preserving paths. Commit.
2. Open Actions. If the build fails, review the **right_half_keys_trackball_eye** job and share the first error (not just the summary).
3. Flash **only** the UF2 artifact named `right_half_keys_trackball_eye` to the right-hand nice!nano.
4. Confirm main keys, Enter / Layer 2 / AltGr thumb keys, PMW3610 mouse movement, and the static wolfie eye.
5. If blank screen persists but trackball and keys work, do not assume wiring is broken: reflash the earlier `wolfie_right_eye` display-only build to separate a display/hardware issue from integration.

## Technical notes

- Existing matrix, diode direction, PMW3610 pinmux and the AltGr keymap are unchanged.
- On the display-only test the custom screen was previously drawn with a 180-degree pre-rotated bitmap. That is preserved in the external module.
- The combined configuration has **not** been locally compiled: GitHub Actions is the build validation step.
- Since `west.yml` tracks module branch `main`, it uses the module's latest commit, not a frozen revision. If changed upstream, it could affect behavior.
