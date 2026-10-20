# Wolfie — Corne keymap transfer (TEST REPOSITORY)

This file is generated from the uploaded `corne_choc_pro.keymap` for the current **44-key Wolfie editor layout**. It is meant for testing in `Wolfieselket/PMW3610-ZMK-Test` before applying to your working Wolfie repository. This is NOT a verified firmware build.

## Upload steps

1. Back up the original `config/wolfie_split.keymap` in the test repository (or use Git history to restore it).
2. Replace `config/wolfie_split.keymap` with the provided file. **Don't place it in `config/boards/`.**
3. Keep your existing `config/wolfie_split.json`; the matching file is also in this ZIP if you need it.
4. Refresh Nick Coutsos' Keymap Editor and reopen `Wolfieselket/PMW3610-ZMK-Test` on `main`.
5. Confirm all ten layers are visible, and check key assignments in each row. Do not flash until a build passes, and verify physical key mapping before using firmware on Wolfie.

## Mapping summary

Uploaded Corne binding order (46):
- Top: 6 left + **2 extra inner** + 6 right
- Middle: 6 left + **2 extra inner** + 6 right
- Bottom: 6 left + 6 right
- Thumbs: 3 left + 3 right

Wolfie (44):
- Top: 6 left + 6 right
- Middle: 6 left + 6 right
- Bottom: 6 left + 6 right
- Thumbs: **new unassigned** + 3 original left + 3 original right + **new unassigned**

### What was dropped or disabled
- Corne inner top-row: `&kp C_MUTE` and `&kp C_PP` (on QWERTY); other layers' matching positions were omitted.
- Corne inner home-row: `&kp LALT` and `&kp RALT` (on QWERTY); other layers' matching positions were omitted.
- `&rgb_ug` bindings -> `&none`, because RGB lighting support hasn't been established for Wolfie. These can be reinstated later if wanted.
- `&studio_unlock` -> `&none`, since ZMK Studio support hasn't been established for Wolfie.
- `sensor-bindings` for the Corne rotary/encoder controls were left out; they are not the PMW3610 pointing bindings.
- Corne `chosen { zmk,physical-layout = &default_layout; }` was deliberately not copied: use Wolfie's own physical layout/matrix settings.

### Kept
- All ten layers including mouse-related layers 3 and 9.
- `&mo 1`, `&mo 2` thumb bindings and `&tog 9` on mouse layer 9.
- Bluetooth selection/clear commands in Functions layer.
- Mouse buttons/scroll bindings (`&mkp`, `&msc`) as in Corne, requiring `CONFIG_ZMK_POINTING=y` in your target firmware.
- Base layer keys and remaining symbols, numbers, F-keys and navigation bindings.

Caution: The layer names and 44 key positions parse correctly and match the provided editor JSON. **No ZMK compilation or hardware validation was possible here.** Missing ZMK behaviours and key definitions may still require changes in the target firmware. Your actual Wolfie matrix transform (not the layout JSON alone) controls which physical switch executes which binding.
