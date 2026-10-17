# Nano35 keymap update

Thumb bindings, in source order from left to right:

| Left 1 | Left 2 | Left 3 | Right 1 | Right 2 |
| --- | --- | --- | --- | --- |
| Space | Enter / NUM | Tab / FUN | Escape / OS | Backspace / NAV |

Tap produces the named key; hold activates the named layer. The existing
320 ms tapping term, 175 ms quick tap and 150 ms prior idle settings are retained.

Hold the left Tab/FUN thumb for function keys. Positions below use Colemak-DH
base letters, not physical QWERTY labels:

| Base positions | FUN output |
| --- | --- |
| Q W F P | F9 F10 F11 F12 |
| A R S T | F5 F6 F7 F8 |
| Z X C D | F1 F2 F3 F4 |

NUM keeps its existing numbers and Backspace, with no added Tab shortcuts.
NAV, OS, MOUSE, BT, the hash combo and all combos except Escape are unchanged.
The former Escape combo (positions 0 + 11) is removed.

Either Shift plus Backspace sends forward Delete without Shift. This applies
to the Backspace/NAV thumb and NUM's Backspace key. If Control, Alt/Option or
GUI/Command is also held, the original modifier + Backspace combination is
preserved, including any Shift. NAV's Option+Backspace word deletion is unchanged.

## Verification after flashing

Check normal Backspace, both Shift+Backspace combinations, holding NAV, and
NAV word deletion. Check Escape tap, OS hold, Tab tap, FUN hold and all twelve
function keys. Verify that the removed Escape combo types its two normal
letters. The firmware build checks syntax and linking; these physical input
checks still require the actual keyboard.

## Bluetooth persistence

Ordinary firmware updates retain Bluetooth host profiles and the split bond.
Use the correct left/right UF2 for the existing nice!nano board and central role.
Do not flash `settings_reset`, enable `CONFIG_ZMK_SETTINGS_RESET_ON_START`, or
erase the flash for this keymap update.

Reference: https://zmk.dev/docs/config/settings
