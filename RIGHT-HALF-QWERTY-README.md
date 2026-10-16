# Right-half QWERTY + PMW3610

This updates the **working** right-half keys-and-trackball test repository.
It only changes `config/right_half_test.keymap` and the artifact name in `build.yaml`;
all hardware GPIO assignments, diode direction, and PMW3610 overlay are unchanged.

## Physical mapping (as viewed from above, left to right)

    Y     U     I     O     P    Backspace
    H     J     K     L     ;    Apostrophe
    N     M     ,     .     /    Escape

    Thumb 1: Space
    Thumb 2: Enter
    Thumb 3: Backspace
    Thumb 4: Momentary NAV layer

Layer 2: the first four physical keys in the home row become
Left, Up, Down, Right respectively;
all other keys pass through to the default layer.

The keymap accounts for the scan ordering proved by the earlier test:
`XWVUTS / RQPONM / LKJIHG / FEDC`.

## Build and flash

1. Copy all repository files to GitHub, replacing the old versions (the ZIP is
   a **repository content ZIP**, not a UF2 image).
2. Let GitHub Actions run.
3. Download the artifact named `right_half_qwerty_trackball`.
4. Flash the UF2 to the right-hand nice!nano using its bootloader.
5. Test all 22 switches and the PMW3610 sensor.

The custom display animation is intentionally NOT included in this firmware.
Firmware has not been compiled in this environment; GitHub Actions is the first
build verification. This is a standalone right-half test, not the final split firmware.
