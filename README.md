# SP201E DMX512 Decoder — Menu Operation Manual

This manual covers only the on-device menu system: the three buttons, the four parameters they control, and how to navigate and edit each one. It does not cover wiring or LED-type-specific setup.

## 1. Confirmed Behavior on This Unit (WS2811)

This unit is configured for WS2811. On power-up, the display shows **2811**, confirming the IC parameter is already set correctly for this LED type; no IC selection is needed unless you want to change LED type.

Pressing MENU from this screen brings up the P parameter, shown as **P--01** (or whichever effect number was last active). UP/DOWN on this screen changes the effect number from 1 to 99, each number running a different one of the built-in patterns.

Live DMX control works automatically on top of this, without needing to pick a separate DMX-only mode: as long as DMX data is actively being sent to the DMX IN port, the decoder follows that data directly. The moment DMX data stops being sent, the unit immediately falls back to running the default built-in effect (whichever number P is currently set to).

## 2. Controls

Three buttons on the front panel:

- **MENU** : moves to the next parameter in the cycle
- **UP** : increases the value of the currently selected parameter
- **DOWN** : decreases the value of the currently selected parameter

## 3. The Four Parameters

Pressing MENU cycles through four parameters in order. The display shows a letter prefix identifying which one is active:

1. **IC** — LED driver chip type (WS2811, WS2812B, APA102, and so on)
2. **P** — mode: either a built-in pattern number (P-01 through P-99) or a special DMX control mode
3. **S** — speed of the built-in pattern; has no effect when a pixel is being driven directly by live DMX data
4. **C** — DMX start channel address

After C, pressing MENU again returns to IC, completing the loop.

## 4. Navigating and Editing Each Parameter

### IC (chip type)
- Press MENU until the display shows IC.
- Press UP to move forward through the chip list, DOWN to move backward.
- Holding UP or DOWN scrolls faster through the list.
- Release once the desired chip name is shown.

### P (mode / effect number)
- Press MENU until the display shows P followed by a number, e.g. P--01.
- UP/DOWN steps through effect numbers 1 to 99, each one a different built-in pattern.
- Long-pressing UP or DOWN fast-scrolls through the range instead of stepping one at a time.
- No separate mode needs to be selected for DMX control. Whichever effect number is set here becomes the default effect that plays whenever live DMX data is not being received.

### S (speed)
- Press MENU until the display shows S followed by a number, e.g. S-05.
- UP/DOWN adjusts the playback speed of the currently selected built-in pattern.
- Only meaningful when P is set to a built-in pattern; has no visible effect in direct DMX control modes.
- Long-press for fast scrolling, same as IC and P.

### C (DMX start channel)
- Press MENU until the display shows C followed by a number, e.g. C-001.
- A short press of UP or DOWN increases or decreases the channel number by one.
- A long press of UP or DOWN shifts which digit is being edited, moving from the ones digit toward the tens, hundreds, and thousands digit. This lets you jump the channel number by large steps instead of stepping one at a time from 1 to 500.
- Release on the desired channel number. This becomes the DMX address at which the decoder starts reading its incoming channel data.

## 5. General Notes on Menu Behavior

- Settings appear to be retained through power cycles (the product description lists "user setting saving" as a feature), so the menu does not need to be reconfigured every time the unit is powered on.
- DMX takeover is automatic: live DMX data received on the IN port immediately takes control of the LEDs. As soon as the DMX data stops being sent, the unit reverts immediately to running the default effect (the P number that is currently set).
- If a setting does not appear to be taking effect, cycle MENU fully around all four parameters once to confirm which one is actually being edited, since it is easy to lose track of which parameter is active on repeated button presses.

## 6. Quick Reference

- MENU : switch parameter (IC → P → S → C → IC ...)
- UP / DOWN : change value of active parameter
- Long-press UP / DOWN on IC/P/S : fast scroll through the list/range
- Long-press UP / DOWN on C : move the active digit for fast large-number entry
