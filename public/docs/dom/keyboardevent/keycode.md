# KeyboardEvent.keyCode

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `KeyboardEvent.keyCode` read-only property represents a system and implementation dependent numerical code identifying the unmodified value of the pressed key. This is usually the decimal ASCII ([RFC 20](https://tools.ietf.org/html/rfc20)) or Windows 1252 code corresponding to the key. If the key can't be identified, this value is `0`.

You should avoid using this if possible; it's been deprecated for some time. Instead, you should use [`KeyboardEvent.code`](code), if it's implemented. Unfortunately, some browsers still don't have it, so you'll have to be careful to make sure you use one which is supported on all target browsers.

Web developers shouldn't use the `keyCode` attribute for printable characters when handling `keydown` and `keyup` events. As described above, the `keyCode` attribute is not useful for printable characters, especially those input with the Shift or Alt key pressed. When implementing a shortcut key handler, the `keypress` event is usually better (at least when Gecko is the runtime in use). See [Gecko Keypress Event](https://developer.mozilla.org/en-US/docs/Gecko_Keypress_Event) for details.

## Example

    window.addEventListener("keydown", function (event) {
      if (event.defaultPrevented) {
        return; // Should do nothing if the default action has been cancelled
      }

      var handled = false;
      if (event.key !== undefined) {
        // Handle the event with KeyboardEvent.key and set handled true.
      } else if (event.keyCode !== undefined) {
        // Handle the event with KeyboardEvent.keyCode and set handled true.
      }

      if (handled) {
        // Suppress "double action" if event handled
        event.preventDefault();
      }
    }, true);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-keyCode">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.keyCode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition; specified as deprecated</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`keyCode`

26

12

3

9

12.1

5

≤37

26

4

12.1

5.1

1.5

## Value of keyCode

### Printable keys in standard position

The value of key events which are caused by pressing or releasing printable keys in standard position is not compatible between browsers.

IE just exposes the native virtual keycode value as `KeyboardEvent.keyCode`.

Google Chrome, Chromium and Safari must decide the value from the input character. If the inputting character can be inputted with the US keyboard layout, they use the `keyCode` value on the US keyboard layout.

Starting in Firefox 15 (Firefox 15.0 / Thunderbird 15.0 / SeaMonkey 2.12), Gecko gets `keyCode` values from ASCII characters inputtable by the key — even with shift modifiers or an ASCII capable keyboard layout. See the following rules for details:

1.  If the system is Windows and the native keycode of the pressed key indicates that the key is a-z or 0-9, use a keycode for it.
2.  If the system is Mac and the native keycode of the pressed key indicates that the key is 0-9, use a keycode for it.
3.  If the pressed key inputs an ASCII alphabetic or numeric character with no modifier key, use a keycode for it.
4.  If the pressed key inputs an ASCII alphabetic or numeric character with a Shift key modifier, use a keycode for it.
5.  If the pressed key inputs a different ASCII character with no modifier key, use a keycode for it.
6.  If the pressed key inputs a different ASCII character with a Shift key modifier, use a keycode for it.
7.  Otherwise, i.e., pressed key inputs a unicode character:
    1.  If the keyboard layout is ASCII-capable (i.e., can input ASCII alphabets), use 0 or compute with [the following additional rules](#keycode_of_punctuation_keys_on_some_keyboard_layout).
    2.  Otherwise, i.e., the keyboard layout isn't ASCII capable, use the ASCII capable keyboard layout installed on the environment with the highest priority:
        1.  If the pressed key on the alternative keyboard layout inputs an ASCII alphabetic or numeric character, use a keycode for it.
        2.  Otherwise, use 0 or compute with [the following additional rules](#keycode_of_punctuation_keys_on_some_keyboard_layout).

Starting in Firefox 60 (Firefox 60.0 / Thunderbird 60.0 / SeaMonkey 2.57), Gecko sets `keyCode` values of punctuation keys as far as possible (when points 7.1 or 7.2 in the above list are reached) with the following rules:

The purpose of these new additional rules is for making users whose keyboard layouts map unicode characters to punctuation keys in a US keyboard layout can use web applications which support Firefox only with ASCII-capable keyboard layouts or just with a US keyboard layout. Otherwise, the newly mapped `keyCode` values may be conflict with other keys. For example, if the active keyboard layout is Russian, the `keyCode` value of **both** the `"Period"` key and `"Slash"` key are `190` (`KeyEvent.DOM_VK_PERIOD`). If you need to distinguish those keys but you don't want to support all keyboard layouts in the world by yourself, you should probably use [`KeyboardEvent.code`](code).

1.  If running macOS or Linux:
    1.  If the active keyboard layout is not ASCII-capable and an alternative ASCII-capable keyboard layout is available.
        1.  If the alternative ASCII-capable keyboard layout produces an ASCII character via just the unmodified key, use a `keyCode` for the character.
        2.  If the alternative ASCII-capable keyboard layout produces an ASCII character with a Shift key modifier, use a `keyCode` for the shifted character.
        3.  Otherwise, use a `keyCode` for an ASCII character produced by the key when the US keyboard layout is active.
    2.  Otherwise, use a `keyCode` for an ASCII character produced by the key when the US keyboard layout is active.
2.  If running on Windows:
    1.  Use a `keyCode` value for an ASCII character produced by a key which is mapped to the same virtual keycode of Windows when the US keyboard layout is active.

keyCode values of each browser's keydown event caused by printable keys in standard position

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

`"Digit1"`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`0x31 (49)`

`"Digit2"`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`0x32 (50)`

`"Digit3"`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`0x33 (51)`

`"Digit4"`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`0x34 (52)`

`"Digit5"`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`0x35 (53)`

`"Digit6"`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`0x36 (54)`

`"Digit7"`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`0x37 (55)`

`"Digit8"`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`0x38 (56)`

`"Digit9"`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`0x39 (57)`

`"Digit0"`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`0x30 (48)`

`"KeyA"`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`0x41 (65)`

`"KeyB"`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`0x42 (66)`

`"KeyC"`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`0x43 (67)`

`"KeyD"`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`0x44 (68)`

`"KeyE"`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`0x45 (69)`

`"KeyF"`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`0x46 (70)`

`"KeyG"`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`0x47 (71)`

`"KeyH"`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`0x48 (72)`

`"KeyI"`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`0x49 (73)`

`"KeyJ"`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`0x4A (74)`

`"KeyK"`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`0x4B (75)`

`"KeyL"`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`0x4C (76)`

`"KeyM"`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`0x4D (77)`

`"KeyN"`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`0x4E (78)`

`"KeyO"`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`0x4F (79)`

`"KeyP"`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`0x50 (80)`

`"KeyQ"`

`0x51 (81)`

`0x51 (81)`

`0x51 (81)`

`0x51 (81)`

`0xBA (186)`

`0x51 (81)`

`0x51 (81)`

`0xBA (186)`

`0x51 (81)`

`0x51 (81)`

`0xBA (186)`

`0x51 (81)`

`0x51 (81)`

`0x51 (81)`

`0xBA (186)`

`0x51 (81)`

`"KeyR"`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`0x52 (82)`

`"KeyS"`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`0x53 (83)`

`"KeyT"`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`0x54 (84)`

`"KeyU"`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`0x55 (85)`

`"KeyV"`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`0x56 (86)`

`"KeyW"`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`0x57 (87)`

`"KeyX"`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`0x58 (88)`

`"KeyY"`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`0x59 (89)`

`"KeyZ"`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

`0x5A (90)`

[`KeyboardEvent.code`](code)

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

keyCode values of each browser's keydown event caused by printable keys in standard position (punctuations in US layout):

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows (10.9)

Mac (10.9)

Linux (Ubuntu 14.04)

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

`"Comma"`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`0xBC (188)`

`"Comma"` with Shift

`"Period"`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`0xBE (190)`

`"Period"` with Shift

`"Semicolon"`

`0xBA (186)`

`0xBB (187)`

`0xBA (186)`

`0xBA (186)`

`0xBB (187)`

`0xBA (186)`

`0xBA (186)`

`0xBA (186)` \*1

`0xE5 (229) *2`

`0xBA (186)`

`0xBA (186)`

`0xE5 (229) *3`

`0xBA (186)`

`0xBA (186)` \*1

`0xE5 (229) *2`

`0x3B (59)`

`0x3B (59)`

`0x00 (0)`

`0x3B (59)`

`0x3B (59)` \*1

`0x00 (0)`

`0x3B (59)`

`0x3B (59)`

`0x00 (0)`

`"Semicolon"` with Shift

`0xBB (187) `\*1

`0xBB (187)`

`0xBB (187)` \*1

`"Quote"`

`0xDE (222)`

`0xBA (186)`

`0xDE (222)`

`0xDE (222)`

`0xBA (186)`

`0xDE (222)`

`0xDE (222)`

`0xBA (186) *1`

`0xDE (222)`

`0xDE (222)`

`0xBA (186)`

`0xDE (222)`

`0xDE (222)`

`0xBA (186)` \*1

`0xDE (222)`

`0xDE (222)`

`0x3A (58)`

`0xDE (222)`

`0xDE (222)`

`0x3A (58)` \*1

`0xDE (222)`

`0xDE (222)`

`0x3A (58)`

`0xDE (222)`

`"Quote"` with Shift

`0xDE (222)` \*1

`0x38 (56)`

`0xDE (222)` \*1

`"BracketLeft"`

`0xDB (219)`

`0xC0(192)`

`0xDB (219)`

`0xDB (219)`

`0xC0(192)`

`0xDB (219)`

`0xDB (219)`

`0xDB (219)` \*1

`0xDB (219)`

`0xDB (219)`

`0x32 (50)`

`0xDB (219)`

`0xDB (219)`

`0xDB (219) *1 `

`0xDB (219)`

`0xDB (219)`

`0x40 (64)`

`0xDB (219)`

`0xDB (219)`

`0x40 (64)` \*1

`0xDB (219)`

`0xDB (219)`

`0x40 (64)`

`0xDB (219)`

`"BracketLeft"` with Shift

`0xC0 (192) *1`

`0xC0 (192)`

`0xC0 (192) *1`

`"BracketRight"`

`0xDD (221)`

`0xDB (219)`

`0xDD (221)`

`0xDD (221)`

`0xDB (219)`

`0xDD (221)`

`0xDD (221)`

`0xDB (219) *1`

`0xDD (221)`

`0xDD (221)`

`0xDB (219)`

`0xDD (221)`

`0xDD (221)`

`0xDB (219) *1`

`0xDD (221)`

`0xDD (221)`

`0xDB (219)`

`0xDD (221)`

`0xDD (221)`

`0xDB (219)` \*1

`0xDD (221)`

`0xDD (221)`

`0xDB (219)`

`0xDD (221)`

`"BracketRight"` with Shift

`"Backquote"`

`0xC0 (192)`

`N/A`

`0xC0 (192)`

`0xC0 (192)`

`N/A`

`0xC0 (192)`

`0xC0 (192)`

`0xC0 (192)`

`0xF4 (244)`

`0xC0 (192)`

`0xC0 (192)`

`0xC0 (192)`

`N/A`

`0xC0 (192)`

`0xC0 (192)`

`0xC0 (192)`

`0x00 (0)`

`0xC0 (192)`

`"Backquote"` with Shift

`"Backslash"`

`0xDC (220)`

`0xDD (221)`

`0xDC (220)`

`0xDC (220)`

`0xDD (221)`

`0xDC (220)`

`0xDC (220)`

`0xDC (220)`

`0xDD (221)`

`0xDC (220)`

`0xDC (220)`

`0xDC (220)`

`0xDD (221)`

`0xDC (220)`

`0xDC (220)`

`0xDC (220)`

`0xDD (221)`

`0xDC (220)`

`"Backslash"` with Shift

`"Minus"`

`0xBD (189)`

`0xBD (189)`

`0xBD (189)`

`0xBD (189)` \*1

`0xBD (189)`

`0xBD (189)`

`0xBD (189)`

`0xBD (189)`

`0xBD (189)`

`0xBD (189) *1`

`0xBD (189)`

`0xAD (173)`

`0xAD (173)`

`0xAD (173) *1`

`0xAD (173)`

`0xAD (173)`

`"Minus"` with Shift

`0xBB (187)` \*1

`0xBB (187)`

`0xBD (189)`

`0xBB (187) *1`

`0xBD (189)`

`"Equal"`

`0xBB (187)`

`0xDE (222)`

`0xBB (187)`

`0xBB (187)`

`0xDE (222)`

`0xBB (187)`

`0xBB (187)`

`0xBB (187) *1`

`0xBB (187)`

`0xBB (187)`

`0x36 (54)`

`0xBB (187)`

`0xBB (187)`

`0xBB (187) *1`

`0xBB (187)`

`0x3D (61)`

`0xA0 (160)`

`0x3D (61)`

`0x3D (61)`

`0xA0 (160)` \*1

`0x3D (61)`

`0x3D (61)`

`0xA0 (160)`

`0x3D (61)`

`"Equal"` with Shift

`0xC0 (192) *1`

`0xC0 (192)`

`0xBB (187)`

`0xC0 (192) *1`

`0xBB (187)`

`"IntlRo"`

`0xC1 (193)`

`0xE2 (226)`

`0xC1 (193)`

`0xC1 (193)`

`0xE2 (226)`

`0xC1 (193)`

`0xBD (189)`

`0xBD (189)`

`0x00 (0)`

\*4

`0xDC (220)`

\*4

`0xBD (189)`

`0xBD (189)`

`0xE5 `(229) \*5

`0x00 (0)`

`0xDC (220)`

`0x00 (0)`

`0xA7 (167)`

`0xA7 (167)`

`0x00 (0)`

`0x00 (0)`

`0xDC (220)`

`0x00 (0)`

`"IntlRo"` with Shift

`"IntlYen"`

`0xFF (255)`

`0xDC (220)`

`0xFF (255)`

`0xFF (255)`

`0xDC (220)`

`0xFF (255)`

`0x00 (0)`

`0x00 (0)`

`0x00 (0)`

\*4

`0xDC (220)`

\*4

`0x00 (0)`

`0x00 (0)`

`0xE5 `(229) \*5

`0x00 (0)`

`0xDC `(220)

`0x00 (0)`

`0xDC `(220)

`0xDC `(220)

`0x00 (0)`

`0x00 (0)`

`0xDC (220)`

`0x00 (0)`

`"IntlYen"` with Shift

`0xDC (220)`

`0xDC (220)`

`0xBD (189)`

`0xDC (220)`

`0xDC (220)`

[`KeyboardEvent.code`](code)

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

US

Japanese

Greek

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

\*1 The value is input from JIS keyboard. When you use ANSI keyboard, the keyCode value and inputted character are what you select from the US keyboard layout.

\*2 The key is a dead key. The value of `keyup` event is `0xBA (186)`.

\*3 The key is a dead key. The value of `keyup` event is `0x10 (16)`.

\*4 No key events are fired.

\*5 The key isn't available with Greek keyboard layout (does not input any character). The value of `keyup` event is `0x00 (0)`.

### Non-printable keys (function keys)

keyCode values of each browser's keydown event caused by modifier keys:

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

`"AltLeft"`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`"AltRight"`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`0x12 (18)`

`"AltRight"` when it's `"AltGraph"` key

\*1

\*1

N/A

`0xE1 (225)`

N/A

\*1

N/A

`0xE1 (225)`

`"CapsLock"`

`0x14 (20)` \*2

`0x14 (20)` \*2

`0x14 (20)`

`0x14 (20)`

`0x14 (20)`

`0x14 (20)` \*2

`0x14 (20)`

`0x14 (20)` \*3

`"ControlLeft"`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`"ControlRight"`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`0x11 (17)`

`"OSLeft"`

`0x5B (91)`

`0x5B (91)`

`0x5B (91)`

`0x5B (91)`

`0x5B (91)`

`0x5B (91)`

`0xE0 (224)`

`0x5B (91)`

`"OSRight"`

`0x5C (92)`

`0x5C (92)`

`0x5D (93)`

`0x5C (92)`

`0x5D (93)`

`0x5B (91)`

`0xE0 (224)`

`0x5B (91)`

`"ShiftLeft"`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`"ShiftRight"`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

`0x10 (16)`

[`KeyboardEvent.code`](code)

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

\*1 On Windows, `"AltGraph"` key causes `"ControlLeft"` key event and `"AltRight"` key event.

\*2 When Japanese keyboard layout is active, `"CapsLock"` key without Shift causes `0xF0 (240)`. The key works as `"Alphanumeric"` key whose label is "英数".

\*3 When Japanese keyboard layout is active, `"CapsLock"` key without Shift causes `0x00 (0)`. The key works as `"Alphanumeric"` key whose label is `"英数"`.

keyCode values of each browser's keydown event caused by non-printable keys:

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

`"ContextMenu"`

`0x5D (93)`

`0x5D (93)`

`0x00 (0)` \*1

`0x5D (93)`

`0x00 (0)` \*1

`0x5D (93)`

`0x5D (93)`

`0x5D (93)`

`"Enter"`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`"Space"`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`0x20 (32)`

`"Tab"`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`0x09 (9)`

`"Delete"`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`"End"`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`"Help"`

N/A

N/A

`0x2D (45)` \*2

`0x2F (47)` \*3

`0x2D (45)` \*2

N/A

`0x2D (45)` \*2

`0x06 (6)` \*3

`"Home"`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`"Insert"`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`"PageDown"`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`"PageUp"`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`"ArrowDown"`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`"ArrowLeft"`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`"ArrowRight"`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`"ArrowUp"`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`"Escape"`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`0x1B (27)`

`"PrintScreen"`

`0x2C (44)` \*4

`0x2C (44)` \*4

`0x7C (124)`\*5

`0x2A (42)`

`0x7C (124)`\*5

`0x2C (44)` \*4

`0x2C (44)`

`0x2A (42)`

`"ScrollLock"`

`0x91 (145)`

`0x91 (145)`

`0x7D (125)`\*5

`0x91 (145)`

`0x7D (125)`\*5

`0x91 (145)`

`0x91 (145)`

`0x91 (145)`

`"Pause"`

`0x13 (19)` \*6

`0x13 (19)` \*6

`0x7E (126)`\*5

`0x13 (19)`

`0x7E (126)`\*5

`0x13 (19)` \*6

`0x13 (19)`

`0x13 (19)`

[`KeyboardEvent.code`](code)

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

\*1 keypress event is fired whose `keyCode` and `charCode` are `0x10 (16)` but text isn't inputted into editor.

\*2 On Mac, `"Help"` key is mapped to `"Insert"` key of PC keyboard. These `keyCode` values are the same as the `"Insert"` key's `keyCode` value.

\*3 Tested on Fedora 20.

\*4 Only `keyup` event is fired.

\*5 PC's `"PrintScreen"`, `"ScrollLock"` and `"Pause"` are mapped to Mac's `"F13"`, `"F14"` and `"F15"`. Chrome and Safari map same `keyCode` values with Mac's keys.

\*6 `"Pause"` key with Control causes `0x03 (3)`.

keyCode values of each browser's keydown event caused by function keys:

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

`"F1"`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`0x70 (112)`

`"F2"`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`0x71 (113)`

`"F3"`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`0x72 (114)`

`"F4"`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`0x73 (115)`

`"F5"`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`0x74 (116)`

`"F6"`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`0x75 (117)`

`"F7"`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`0x76 (118)`

`"F8"`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`0x77 (119)`

`"F9"`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`0x78 (120)`

`"F10"`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`0x79 (121)`

`"F11"`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`0x7A (122)`

`"F12"`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`0x7B (123)`

`"F13"`

`0x7C (124)`

`0x7C (124)`

`0x7C (124)`

`0x7C (124)` \*1

`0x7C (124)`

`0x7C (124)`

`0x2C (44)` \*2

`0x00 (0)` \*3

`"F14"`

`0x7D (125)`

`0x7D (125)`

`0x7D (125)`

`0x7D (125)` \*1

`0x7D (125)`

`0x7D (125)`

`0x91 (145)` \*2

`0x00 (0)` \*3

`"F15"`

`0x7E (126)`

`0x7E (126)`

`0x7E (126)`

`0x7E (126)` \*1

`0x7E (126)`

`0x7E (126)`

`0x13 (19)` \*2

`0x00 (0)` \*3

`"F16"`

`0x7F (127)`

`0x7F (127)`

`0x7F (127)`

`0x7F (127)` \*1

`0x7F (127)`

`0x7F (127)`

`0x7F (127)`

`0x00 (0)` \*3

`"F17"`

`0x80 (128)`

`0x80 (128)`

`0x80 (128)`

`0x80 (128)` \*1

`0x80 (128)`

`0x80 (128)`

`0x80 (128)`

`0x00 (0)` \*3

`"F18"`

`0x81 (129)`

`0x81 (129)`

`0x81 (129)`

`0x81 (129)` \*1

`0x81 (129)`

`0x81 (129)`

`0x81 (129)`

`0x00 (0)` \*3

`"F19"`

`0x82 (130)`

`0x82 (130)`

`0x82 (130)`

`N/A` \*4

`0x82 (130)`

`0x82 (130)`

`0x82 (130)`

`0x00 (0)` \*3

`"F20"`

`0x83 (131)`

`0x83 (131)`

`0x83 (131)`

`N/A` \*4

`0xE5 (229)` \*5

`0x83 (131)`

`0x00 (0)`

`N/A` \*6

`"F21"`

`0x84 (132)`

`0x84 (132)`

`0x00 (0)` \*7

`N/A` \*4

`0x00 (0)` \*7

`0x84 (132)`

`N/A` \*8

`N/A` \*6

`"F22"`

`0x85 (133)`

`0x85 (133)`

`0x00 (0)` \*7

`N/A` \*4

`0x00 (0)` \*7

`0x85 (133)`

`N/A` \*8

`N/A` \*6

`"F23"`

`0x86 (134)`

`0x86 (134)`

`0x00 (0)` \*7

`N/A` \*4

`0x00 (0)` \*7

`0x86 (134)`

`N/A` \*8

`N/A` \*6

`"F24"`

`0x87 (135)`

`0x87 (135)`

`0x00 (0)` \*7

`N/A` \*4

`0x00 (0)` \*7

`0x87 (135)`

`N/A` \*8

`0x00 (0)` \*3

[`KeyboardEvent.code`](code)

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

\*1 Tested on Fedora 20.

\*2 PC's `"PrintScreen"`, `"ScrollLock"` and `"Pause"` are mapped to `Mac's "F13"`, `"F14"` and `"F15"`. Firefox maps same `keyCode` values with PC's keys.

\*3 Tested on Fedora 20. The keys don't cause `GDK_Fxx` keysyms. If the keys cause proper keysyms, these values must be same as IE.

\*4 Tested on Fedora 20. The keys don't cause DOM key events on Chromium.

\*5 `keyUp` event's keyCode value is `0x83 (131)`.

\*6 Tested on Fedora 20. The keys don't cause DOM key events on Firefox.

\*7 Only `keydown` event is fired.

\*8 No DOM key events are fired on Firefox.

### Numpad keys

keyCode values of each browser's keydown event caused by keys in numpad in NumLock state

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

`"NumLock"`

`0x90 (144)`

`0x90 (144)`

`0x0C (12)` \*1

`0x90 (144)`

`0x0C (12)` \*1

`0x90 (144)`

`0x0C (12)` \*1

`0x90 (144)`

`"Numpad0"`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`0x60 (96)`

`"Numpad1"`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`0x61 (97)`

`"Numpad2"`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`0x62 (98)`

`"Numpad3"`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`0x63 (99)`

`"Numpad4"`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`0x64 (100)`

`"Numpad5"`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`0x65 (101)`

`"Numpad6"`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`0x66 (102)`

`"Numpad7"`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`0x67 (103)`

`"Numpad8"`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`0x68 (104)`

`"Numpad9"`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`0x69 (105)`

`"NumpadAdd"`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`0x6B (107)`

`"NumpadComma"` inputting `","`

`0xC2 (194)`

`0xC2 (194)`

`0xBC (188)`

`Always inputs `"."

`0xBC (188)`

`0xC2 (194)`

`0x6C (108)`

`Always inputs `"."

`"NumpadComma"` inputting `"."` or empty string

`0xC2 (194)`

`0xC2 (194)`

`0xBE (190)`

`0x6E (110)`

`0xBE (190)`

`0xC2 (194)`

`0x6C (108)`

`0x6E (110)`

`"NumpadDecimal"` inputting `"."`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`"NumpadDecimal"` inputting `","`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6C (108)`

`0x6E (110)`

`0x6E (110)`

`0x6E (110)`

`0x6C (108)`

`"NumpadDivide"`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`0x6F (111)`

`"NumpadEnter"`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`0x0D (13)`

`"NumpadEqual"`

`0x0C (12)`

`0x0C (12)`

`0xBB (187)`

`0xBB (187)`

`0xBB (187)`

`0x0C (12)`

`0x3D (61)`

`0x3D (61)`

`"NumpadMultiply"`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`0x6A (106)`

`"NumpadSubtract"`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

`0x6D (109)`

[`KeyboardEvent.code`](code)

Windows

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Mac (10.9)

Windows

Mac (10.9)

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Safari 7

Gecko 29

\*1 `"NumLock"` key works as `"Clear"` key on Mac.

keyCode values of each browser's keydown event caused by keys in numpad without NumLock state

[`KeyboardEvent.code`](code)

Internet Explorer 11

Google Chrome 34

Chromium 34

Gecko 29

Windows

Windows

Linux (Ubuntu 14.04)

Windows

Linux (Ubuntu 14.04)

`"Numpad0"` (`"Insert"`)

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`0x2D (45)`

`"Numpad1"` (`"End"`)

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`0x23 (35)`

`"Numpad2"` (`"ArrowDown"`)

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`0x28 (40)`

`"Numpad3"` (`"PageDown"`)

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`0x22 (34)`

`"Numpad4"` (`"ArrowLeft"`)

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`0x25 (37)`

`"Numpad5"`

`0x0C (12)`

`0x0C (12)`

`0x0C (12)`

`0x0C (12)`

`0x0C (12)`

`"Numpad6"` (`"ArrowRight"`)

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`0x27 (39)`

`"Numpad7"` (`"Home"`)

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`0x24 (36)`

`"Numpad8"` (`"ArrowUp"`)

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`0x26 (38)`

`"Numpad9"` (`"PageUp"`)

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`0x21 (33)`

`"NumpadDecimal"` (`"Delete"`)

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

`0x2E (46)`

[`KeyboardEvent.code`](code)

Windows

Windows

Linux (Ubuntu 14.04)

Windows

Linux (Ubuntu 14.04)

Internet Explorer 11

Google Chrome 34

Chromium 34

Gecko 29

\* Recent Mac doesn't have `"NumLock"` key and state. Therefore, unlocked state isn't available.

## Constants for keyCode value

Gecko defines a lot of `keyCode` values in `KeyboardEvent` for making the mapping table explicitly. These values are useful for add-on developers of Firefox, but not so useful in public web pages.

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_VK_CANCEL</code></td><td>0x03 (3)</td><td>Cancel key.</td></tr><tr class="even"><td><code>DOM_VK_HELP</code></td><td>0x06 (6)</td><td>Help key.</td></tr><tr class="odd"><td><code>DOM_VK_BACK_SPACE</code></td><td>0x08 (8)</td><td>Backspace key.</td></tr><tr class="even"><td><code>DOM_VK_TAB</code></td><td>0x09 (9)</td><td>Tab key.</td></tr><tr class="odd"><td><code>DOM_VK_CLEAR</code></td><td>0x0C (12)</td><td>"5" key on Numpad when NumLock is unlocked. Or on Mac, clear key which is positioned at NumLock key.</td></tr><tr class="even"><td><code>DOM_VK_RETURN</code></td><td>0x0D (13)</td><td>Return/enter key on the main keyboard.</td></tr><tr class="odd"><td><code>DOM_VK_ENTER</code></td><td>0x0E (14)</td><td>Reserved, but not used. <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span> (Dropped, see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=969247">bug 969247</a>.)</td></tr><tr class="even"><td><code>DOM_VK_SHIFT</code></td><td>0x10 (16)</td><td>Shift key.</td></tr><tr class="odd"><td><code>DOM_VK_CONTROL</code></td><td>0x11 (17)</td><td>Control key.</td></tr><tr class="even"><td><code>DOM_VK_ALT</code></td><td>0x12 (18)</td><td>Alt (Option on Mac) key.</td></tr><tr class="odd"><td><code>DOM_VK_PAUSE</code></td><td>0x13 (19)</td><td>Pause key.</td></tr><tr class="even"><td><code>DOM_VK_CAPS_LOCK</code></td><td>0x14 (20)</td><td>Caps lock.</td></tr><tr class="odd"><td><code>DOM_VK_KANA</code></td><td>0x15 (21)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_HANGUL</code></td><td>0x15 (21)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_EISU</code></td><td>0x 16 (22)</td><td>"英数" key on Japanese Mac keyboard.</td></tr><tr class="even"><td><code>DOM_VK_JUNJA</code></td><td>0x17 (23)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_FINAL</code></td><td>0x18 (24)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_HANJA</code></td><td>0x19 (25)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_KANJI</code></td><td>0x19 (25)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_ESCAPE</code></td><td>0x1B (27)</td><td>Escape key.</td></tr><tr class="odd"><td><code>DOM_VK_CONVERT</code></td><td>0x1C (28)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_NONCONVERT</code></td><td>0x1D (29)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_ACCEPT</code></td><td>0x1E (30)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_MODECHANGE</code></td><td>0x1F (31)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_SPACE</code></td><td>0x20 (32)</td><td>Space bar.</td></tr><tr class="even"><td><code>DOM_VK_PAGE_UP</code></td><td>0x21 (33)</td><td>Page Up key.</td></tr><tr class="odd"><td><code>DOM_VK_PAGE_DOWN</code></td><td>0x22 (34)</td><td>Page Down key.</td></tr><tr class="even"><td><code>DOM_VK_END</code></td><td>0x23 (35)</td><td>End key.</td></tr><tr class="odd"><td><code>DOM_VK_HOME</code></td><td>0x24 (36)</td><td>Home key.</td></tr><tr class="even"><td><code>DOM_VK_LEFT</code></td><td>0x25 (37)</td><td>Left arrow.</td></tr><tr class="odd"><td><code>DOM_VK_UP</code></td><td>0x26 (38)</td><td>Up arrow.</td></tr><tr class="even"><td><code>DOM_VK_RIGHT</code></td><td>0x27 (39)</td><td>Right arrow.</td></tr><tr class="odd"><td><code>DOM_VK_DOWN</code></td><td>0x28 (40)</td><td>Down arrow.</td></tr><tr class="even"><td><code>DOM_VK_SELECT</code></td><td>0x29 (41)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_PRINT</code></td><td>0x2A (42)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_EXECUTE</code></td><td>0x2B (43)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="odd"><td><code>DOM_VK_PRINTSCREEN</code></td><td>0x2C (44)</td><td>Print Screen key.</td></tr><tr class="even"><td><code>DOM_VK_INSERT</code></td><td>0x2D (45)</td><td>Ins(ert) key.</td></tr><tr class="odd"><td><code>DOM_VK_DELETE</code></td><td>0x2E (46)</td><td>Del(ete) key.</td></tr><tr class="even"><td><code>DOM_VK_0</code></td><td>0x30 (48)</td><td>"0" key in standard key location.</td></tr><tr class="odd"><td><code>DOM_VK_1</code></td><td>0x31 (49)</td><td>"1" key in standard key location.</td></tr><tr class="even"><td><code>DOM_VK_2</code></td><td>0x32 (50)</td><td>"2" key in standard key location.</td></tr><tr class="odd"><td><code>DOM_VK_3</code></td><td>0x33 (51)</td><td>"3" key in standard key location.</td></tr><tr class="even"><td><code>DOM_VK_4</code></td><td>0x34 (52)</td><td>"4" key in standard key location.</td></tr><tr class="odd"><td><code>DOM_VK_5</code></td><td>0x35 (53)</td><td>"5" key in standard key location.</td></tr><tr class="even"><td><code>DOM_VK_6</code></td><td>0x36 (54)</td><td>"6" key in standard key location.</td></tr><tr class="odd"><td><code>DOM_VK_7</code></td><td>0x37 (55)</td><td>"7" key in standard key location.</td></tr><tr class="even"><td><code>DOM_VK_8</code></td><td>0x38 (56)</td><td>"8" key in standard key location.</td></tr><tr class="odd"><td><code>DOM_VK_9</code></td><td>0x39 (57)</td><td>"9" key in standard key location.</td></tr><tr class="even"><td><code>DOM_VK_COLON</code></td><td>0x3A (58)</td><td>Colon (":") key.</td></tr><tr class="odd"><td><code>DOM_VK_SEMICOLON</code></td><td>0x3B (59)</td><td>Semicolon (";") key.</td></tr><tr class="even"><td><code>DOM_VK_LESS_THAN</code></td><td>0x3C (60)</td><td>Less-than ("&lt;") key.</td></tr><tr class="odd"><td><code>DOM_VK_EQUALS</code></td><td>0x3D (61)</td><td>Equals ("=") key.</td></tr><tr class="even"><td><code>DOM_VK_GREATER_THAN</code></td><td>0x3E (62)</td><td>Greater-than ("&gt;") key.</td></tr><tr class="odd"><td><code>DOM_VK_QUESTION_MARK</code></td><td>0x3F (63)</td><td>Question mark ("?") key.</td></tr><tr class="even"><td><code>DOM_VK_AT</code></td><td>0x40 (64)</td><td>Atmark ("@") key.</td></tr><tr class="odd"><td><code>DOM_VK_A</code></td><td>0x41 (65)</td><td>"A" key.</td></tr><tr class="even"><td><code>DOM_VK_B</code></td><td>0x42 (66)</td><td>"B" key.</td></tr><tr class="odd"><td><code>DOM_VK_C</code></td><td>0x43 (67)</td><td>"C" key.</td></tr><tr class="even"><td><code>DOM_VK_D</code></td><td>0x44 (68)</td><td>"D" key.</td></tr><tr class="odd"><td><code>DOM_VK_E</code></td><td>0x45 (69)</td><td>"E" key.</td></tr><tr class="even"><td><code>DOM_VK_F</code></td><td>0x46 (70)</td><td>"F" key.</td></tr><tr class="odd"><td><code>DOM_VK_G</code></td><td>0x47 (71)</td><td>"G" key.</td></tr><tr class="even"><td><code>DOM_VK_H</code></td><td>0x48 (72)</td><td>"H" key.</td></tr><tr class="odd"><td><code>DOM_VK_I</code></td><td>0x49 (73)</td><td>"I" key.</td></tr><tr class="even"><td><code>DOM_VK_J</code></td><td>0x4A (74)</td><td>"J" key.</td></tr><tr class="odd"><td><code>DOM_VK_K</code></td><td>0x4B (75)</td><td>"K" key.</td></tr><tr class="even"><td><code>DOM_VK_L</code></td><td>0x4C (76)</td><td>"L" key.</td></tr><tr class="odd"><td><code>DOM_VK_M</code></td><td>0x4D (77)</td><td>"M" key.</td></tr><tr class="even"><td><code>DOM_VK_N</code></td><td>0x4E (78)</td><td>"N" key.</td></tr><tr class="odd"><td><code>DOM_VK_O</code></td><td>0x4F (79)</td><td>"O" key.</td></tr><tr class="even"><td><code>DOM_VK_P</code></td><td>0x50 (80)</td><td>"P" key.</td></tr><tr class="odd"><td><code>DOM_VK_Q</code></td><td>0x51 (81)</td><td>"Q" key.</td></tr><tr class="even"><td><code>DOM_VK_R</code></td><td>0x52 (82)</td><td>"R" key.</td></tr><tr class="odd"><td><code>DOM_VK_S</code></td><td>0x53 (83)</td><td>"S" key.</td></tr><tr class="even"><td><code>DOM_VK_T</code></td><td>0x54 (84)</td><td>"T" key.</td></tr><tr class="odd"><td><code>DOM_VK_U</code></td><td>0x55 (85)</td><td>"U" key.</td></tr><tr class="even"><td><code>DOM_VK_V</code></td><td>0x56 (86)</td><td>"V" key.</td></tr><tr class="odd"><td><code>DOM_VK_W</code></td><td>0x57 (87)</td><td>"W" key.</td></tr><tr class="even"><td><code>DOM_VK_X</code></td><td>0x58 (88)</td><td>"X" key.</td></tr><tr class="odd"><td><code>DOM_VK_Y</code></td><td>0x59 (89)</td><td>"Y" key.</td></tr><tr class="even"><td><code>DOM_VK_Z</code></td><td>0x5A (90)</td><td>"Z" key.</td></tr><tr class="odd"><td><code>DOM_VK_WIN</code></td><td>0x5B (91)</td><td>Windows logo key on Windows. Or Super or Hyper key on Linux.</td></tr><tr class="even"><td><code>DOM_VK_CONTEXT_MENU</code></td><td>0x5D (93)</td><td>Opening context menu key.</td></tr><tr class="odd"><td><code>DOM_VK_SLEEP</code></td><td>0x5F (95)</td><td>Linux support for this keycode was added in Gecko 4.0.</td></tr><tr class="even"><td><code>DOM_VK_NUMPAD0</code></td><td>0x60 (96)</td><td>"0" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_NUMPAD1</code></td><td>0x61 (97)</td><td>"1" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_NUMPAD2</code></td><td>0x62 (98)</td><td>"2" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_NUMPAD3</code></td><td>0x63 (99)</td><td>"3" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_NUMPAD4</code></td><td>0x64 (100)</td><td>"4" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_NUMPAD5</code></td><td>0x65 (101)</td><td>"5" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_NUMPAD6</code></td><td>0x66 (102)</td><td>"6" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_NUMPAD7</code></td><td>0x67 (103)</td><td>"7" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_NUMPAD8</code></td><td>0x68 (104)</td><td>"8" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_NUMPAD9</code></td><td>0x69 (105)</td><td>"9" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_MULTIPLY</code></td><td>0x6A (106)</td><td>"*" on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_ADD</code></td><td>0x6B (107)</td><td>"+" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_SEPARATOR</code></td><td>0x6C (108)</td><td></td></tr><tr class="odd"><td><code>DOM_VK_SUBTRACT</code></td><td>0x6D (109)</td><td>"-" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_DECIMAL</code></td><td>0x6E (110)</td><td>Decimal point on the numeric keypad.</td></tr><tr class="odd"><td><code>DOM_VK_DIVIDE</code></td><td>0x6F (111)</td><td>"/" on the numeric keypad.</td></tr><tr class="even"><td><code>DOM_VK_F1</code></td><td>0x70 (112)</td><td>F1 key.</td></tr><tr class="odd"><td><code>DOM_VK_F2</code></td><td>0x71 (113)</td><td>F2 key.</td></tr><tr class="even"><td><code>DOM_VK_F3</code></td><td>0x72 (114)</td><td>F3 key.</td></tr><tr class="odd"><td><code>DOM_VK_F4</code></td><td>0x73 (115)</td><td>F4 key.</td></tr><tr class="even"><td><code>DOM_VK_F5</code></td><td>0x74 (116)</td><td>F5 key.</td></tr><tr class="odd"><td><code>DOM_VK_F6</code></td><td>0x75 (117)</td><td>F6 key.</td></tr><tr class="even"><td><code>DOM_VK_F7</code></td><td>0x76 (118)</td><td>F7 key.</td></tr><tr class="odd"><td><code>DOM_VK_F8</code></td><td>0x77 (119)</td><td>F8 key.</td></tr><tr class="even"><td><code>DOM_VK_F9</code></td><td>0x78 (120)</td><td>F9 key.</td></tr><tr class="odd"><td><code>DOM_VK_F10</code></td><td>0x79 (121)</td><td>F10 key.</td></tr><tr class="even"><td><code>DOM_VK_F11</code></td><td>0x7A (122)</td><td>F11 key.</td></tr><tr class="odd"><td><code>DOM_VK_F12</code></td><td>0x7B (123)</td><td>F12 key.</td></tr><tr class="even"><td><code>DOM_VK_F13</code></td><td>0x7C (124)</td><td>F13 key.</td></tr><tr class="odd"><td><code>DOM_VK_F14</code></td><td>0x7D (125)</td><td>F14 key.</td></tr><tr class="even"><td><code>DOM_VK_F15</code></td><td>0x7E (126)</td><td>F15 key.</td></tr><tr class="odd"><td><code>DOM_VK_F16</code></td><td>0x7F (127)</td><td>F16 key.</td></tr><tr class="even"><td><code>DOM_VK_F17</code></td><td>0x80 (128)</td><td>F17 key.</td></tr><tr class="odd"><td><code>DOM_VK_F18</code></td><td>0x81 (129)</td><td>F18 key.</td></tr><tr class="even"><td><code>DOM_VK_F19</code></td><td>0x82 (130)</td><td>F19 key.</td></tr><tr class="odd"><td><code>DOM_VK_F20</code></td><td>0x83 (131)</td><td>F20 key.</td></tr><tr class="even"><td><code>DOM_VK_F21</code></td><td>0x84 (132)</td><td>F21 key.</td></tr><tr class="odd"><td><code>DOM_VK_F22</code></td><td>0x85 (133)</td><td>F22 key.</td></tr><tr class="even"><td><code>DOM_VK_F23</code></td><td>0x86 (134)</td><td>F23 key.</td></tr><tr class="odd"><td><code>DOM_VK_F24</code></td><td>0x87 (135)</td><td>F24 key.</td></tr><tr class="even"><td><code>DOM_VK_NUM_LOCK</code></td><td>0x90 (144)</td><td>Num Lock key.</td></tr><tr class="odd"><td><code>DOM_VK_SCROLL_LOCK</code></td><td>0x91 (145)</td><td>Scroll Lock key.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_FJ_JISHO</code></td><td>0x92 (146)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for "Dictionary" key on Fujitsu OASYS.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_FJ_MASSHOU</code></td><td>0x93 (147)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for "Unregister word" key on Fujitsu OASYS.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_FJ_TOUROKU</code></td><td>0x94 (148)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for "Register word" key on Fujitsu OASYS.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_FJ_LOYA</code></td><td>0x95 (149)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for "Left OYAYUBI" key on Fujitsu OASYS.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_FJ_ROYA</code></td><td>0x96 (150)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for "Right OYAYUBI" key on Fujitsu OASYS.</td></tr><tr class="odd"><td><code>DOM_VK_CIRCUMFLEX</code></td><td>0xA0 (160)</td><td>Circumflex ("^") key.</td></tr><tr class="even"><td><code>DOM_VK_EXCLAMATION</code></td><td>0xA1 (161)</td><td>Exclamation ("!") key.</td></tr><tr class="odd"><td><code>DOM_VK_DOUBLE_QUOTE</code></td><td>0xA3 (162)</td><td>Double quote (""") key.</td></tr><tr class="even"><td><code>DOM_VK_HASH</code></td><td>0xA3 (163)</td><td>Hash ("#") key.</td></tr><tr class="odd"><td><code>DOM_VK_DOLLAR</code></td><td>0xA4 (164)</td><td>Dollar sign ("$") key.</td></tr><tr class="even"><td><code>DOM_VK_PERCENT</code></td><td>0xA5 (165)</td><td>Percent ("%") key.</td></tr><tr class="odd"><td><code>DOM_VK_AMPERSAND</code></td><td>0xA6 (166)</td><td>Ampersand ("&amp;") key.</td></tr><tr class="even"><td><code>DOM_VK_UNDERSCORE</code></td><td>0xA7 (167)</td><td>Underscore ("_") key.</td></tr><tr class="odd"><td><code>DOM_VK_OPEN_PAREN</code></td><td>0xA8 (168)</td><td>Open parenthesis ("(") key.</td></tr><tr class="even"><td><code>DOM_VK_CLOSE_PAREN</code></td><td>0xA9 (169)</td><td>Close parenthesis (")") key.</td></tr><tr class="odd"><td><code>DOM_VK_ASTERISK</code></td><td>0xAA (170)</td><td>Asterisk ("*") key.</td></tr><tr class="even"><td><code>DOM_VK_PLUS</code></td><td>0xAB (171)</td><td>Plus ("+") key.</td></tr><tr class="odd"><td><code>DOM_VK_PIPE</code></td><td>0xAC (172)</td><td>Pipe ("|") key.</td></tr><tr class="even"><td><code>DOM_VK_HYPHEN_MINUS</code></td><td>0xAD (173)</td><td>Hyphen-US/docs/Minus ("-") key.</td></tr><tr class="odd"><td><code>DOM_VK_OPEN_CURLY_BRACKET</code></td><td>0xAE (174)</td><td>Open curly bracket ("{") key.</td></tr><tr class="even"><td><code>DOM_VK_CLOSE_CURLY_BRACKET</code></td><td>0xAF (175)</td><td>Close curly bracket ("}") key.</td></tr><tr class="odd"><td><code>DOM_VK_TILDE</code></td><td>0xB0 (176)</td><td>Tilde ("~") key.</td></tr><tr class="even"><td><code>DOM_VK_VOLUME_MUTE</code></td><td>0xB5 (181)</td><td>Audio mute key.</td></tr><tr class="odd"><td><code>DOM_VK_VOLUME_DOWN</code></td><td>0xB6 (182)</td><td>Audio volume down key</td></tr><tr class="even"><td><code>DOM_VK_VOLUME_UP</code></td><td>0xB7 (183)</td><td>Audio volume up key</td></tr><tr class="odd"><td><code>DOM_VK_COMMA</code></td><td>0xBC (188)</td><td>Comma (",") key.</td></tr><tr class="even"><td><code>DOM_VK_PERIOD</code></td><td>0xBE (190)</td><td>Period (".") key.</td></tr><tr class="odd"><td><code>DOM_VK_SLASH</code></td><td>0xBF (191)</td><td>Slash ("/") key.</td></tr><tr class="even"><td><code>DOM_VK_BACK_QUOTE</code></td><td>0xC0 (192)</td><td>Back tick ("`") key.</td></tr><tr class="odd"><td><code>DOM_VK_OPEN_BRACKET</code></td><td>0xDB (219)</td><td>Open square bracket ("[") key.</td></tr><tr class="even"><td><code>DOM_VK_BACK_SLASH</code></td><td>0xDC (220)</td><td>Back slash ("\") key.</td></tr><tr class="odd"><td><code>DOM_VK_CLOSE_BRACKET</code></td><td>0xDD (221)</td><td>Close square bracket ("]") key.</td></tr><tr class="even"><td><code>DOM_VK_QUOTE</code></td><td>0xDE (222)</td><td>Quote (''') key.</td></tr><tr class="odd"><td><code>DOM_VK_META</code></td><td>0xE0 (224)</td><td>Meta key on Linux, Command key on Mac.</td></tr><tr class="even"><td><code>DOM_VK_ALTGR</code></td><td>0xE1 (225)</td><td>AltGr key (Level 3 Shift key or Level 5 Shift key) on Linux.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_ICO_HELP</code></td><td>0xE3 (227)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This is (was?) used for Olivetti ICO keyboard.</td></tr><tr class="even"><td><code>DOM_VK_WIN_ICO_00</code></td><td>0xE4 (228)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This is (was?) used for Olivetti ICO keyboard.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_ICO_CLEAR</code></td><td>0xE6 (230)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This is (was?) used for Olivetti ICO keyboard.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_RESET</code></td><td>0xE9 (233)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_JUMP</code></td><td>0xEA (234)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_PA1</code></td><td>0xEB (235)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_PA2</code></td><td>0xEC (236)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_PA3</code></td><td>0xED (237)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_WSCTRL</code></td><td>0xEE (238)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_CUSEL</code></td><td>0xEF (239)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_ATTN</code></td><td>0xF0 (240)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_FINISH</code></td><td>0xF1 (241)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_COPY</code></td><td>0xF2 (242)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_AUTO</code></td><td>0xF3 (243)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_WIN_OEM_ENLW</code></td><td>0xF4 (244)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_BACKTAB</code></td><td>0xF5 (245)</td><td>An <a href="#oem_specific_keys_on_windows">OEM specific key on Windows</a>. This was used for Nokia/Ericsson's device.</td></tr><tr class="odd"><td><code>DOM_VK_ATTN</code></td><td>0xF6 (246)</td><td>Attn (Attention) key of IBM midrange computers, e.g., AS/400.</td></tr><tr class="even"><td><code>DOM_VK_CRSEL</code></td><td>0xF7 (247)</td><td>CrSel (Cursor Selection) key of IBM 3270 keyboard layout.</td></tr><tr class="odd"><td><code>DOM_VK_EXSEL</code></td><td>0xF8 (248)</td><td>ExSel (Extend Selection) key of IBM 3270 keyboard layout.</td></tr><tr class="even"><td><code>DOM_VK_EREOF</code></td><td>0xF9 (249)</td><td>Erase EOF key of IBM 3270 keyboard layout.</td></tr><tr class="odd"><td><code>DOM_VK_PLAY</code></td><td>0xFA (250)</td><td>Play key of IBM 3270 keyboard layout.</td></tr><tr class="even"><td><code>DOM_VK_ZOOM</code></td><td>0xFB (251)</td><td>Zoom key.</td></tr><tr class="odd"><td><code>DOM_VK_PA1</code></td><td>0xFD (253)</td><td>PA1 key of IBM 3270 keyboard layout.</td></tr><tr class="even"><td><code>DOM_VK_WIN_OEM_CLEAR</code></td><td>0xFE (254)</td><td>Clear key, but we're not sure the meaning difference from <code>DOM_VK_CLEAR</code>.</td></tr></tbody></table>

### OEM specific keys on Windows

On Windows, some values of virtual keycode are defined (reserved) for OEM specific key. They are available for special keys on non-standard keyboard. In other words, some values are used for different meaning by two or more vendors (or hardware).

Starting Gecko 21 (and older than 15), OEM specific key values are available on the keyCode attribute only on Windows. So they are not useful for usual web applications. They are useful only for intranet applications or in similar situations.

See "[Manufacturer-specific Virtual-Key Codes (Windows CE 5.0)](https://msdn.microsoft.com/en-us/library/aa452679.aspx)" in MSDN for the detail.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode</a>
