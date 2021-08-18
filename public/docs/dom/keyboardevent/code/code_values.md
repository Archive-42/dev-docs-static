# KeyboardEvent: code values

The following tables show what code values are used for each native scancode or virtual keycode on major platforms. The reason is that some browsers choose to interpret physical keys differently, there are some differences in which keys map to which codes. These tables show those variations when known.

## Code values

### Code values on Windows

This table shows the Windows scan codes representing keys and the `KeyboardEvent.code` values which correspond to those hardware keys. Only keys which generate scan codes on Windows are listed.

`KeyboardEvent.code` value

Code

Firefox

Chrome

`0x0000`

`"Unidentified"`

`""`

`0x0001`

`"Escape"`

`"Escape"`

`0x0002`

`"Digit0"`

`"Digit0"`

`0x0003`

`"Digit1"`

`"Digit1"`

`0x0004`

`"Digit2"`

`"Digit2"`

`0x0005`

`"Digit3"`

`"Digit3"`

`0x0006`

`"Digit4"`

`"Digit4"`

`0x0007`

`"Digit5"`

`"Digit5"`

`0x0008`

`"Digit6"`

`"Digit6"`

`0x0009`

`"Digit7"`

`"Digit7"`

`0x000A`

`"Digit8"`

`"Digit8"`

`0x000B`

`"Digit9"`

`"Digit9"`

`0x000C`

`"Minus"`

`"Minus"`

`0x000D`

`"Equal"`

`"Equal"`

`0x000E`

`"Backspace"`

`"Backspace"`

`0x000F`

`"Tab"`

`"Tab"`

`0x0010`

`"KeyQ"`

`"KeyQ"`

`0x0011`

`"KeyW"`

`"KeyW"`

`0x0012`

`"KeyE"`

`"KeyE"`

`0x0013`

`"KeyR"`

`"KeyR"`

`0x0014`

`"KeyT"`

`"KeyT"`

`0x0015`

`"KeyY"`

`"KeyY"`

`0x0016`

`"KeyU"`

`"KeyU"`

`0x0017`

`"KeyI"`

`"KeyI"`

`0x0018`

`"KeyO"`

`"KeyO"`

`0x0019`

`"KeyP"`

`"KeyP"`

`0x001A`

`"BracketLeft"`

`"BracketLeft"`

`0x001B`

`"BracketRight"`

`"BracketRight"`

`0x001C`

`"Enter"`

`"Enter"`

`0x001D`

`"ControlLeft"`

`"ControlLeft"`

`0x001E`

`"KeyA"`

`"KeyA"`

`0x001F`

`"KeyS"`

`"KeyS"`

`0x0020`

`"KeyD"`

`"KeyD"`

`0x0021`

`"KeyF"`

`"KeyF"`

`0x0022`

`"KeyG"`

`"KeyG"`

`0x0023`

`"KeyH"`

`"KeyH"`

`0x0024`

`"KeyJ"`

`"KeyJ"`

`0x0025`

`"KeyK"`

`"KeyK"`

`0x0026`

`"KeyL"`

`"KeyL"`

`0x0027`

`"Semicolon"`

`"Semicolon"`

`0x0028`

`"Quote"`

`"Quote"`

`0x0029`

`"Backquote"`

`"Backquote"`

`0x002A`

`"ShiftLeft"`

`"ShiftLeft"`

`0x002B`

`"Backslash"`

`"Backslash"`

`0x002C`

`"KeyZ"`

`"KeyZ"`

`0x002D`

`"KeyX"`

`"KeyX"`

`0x002E`

`"KeyC"`

`"KeyC"`

`0x002F`

`"KeyV"`

`"KeyV"`

`0x0030`

`"KeyB"`

`"KeyB"`

`0x0031`

`"KeyN"`

`"KeyN"`

`0x0032`

`"KeyM"`

`"KeyM"`

`0x0033`

`"Comma"`

`"Comma"`

`0x0034`

`"Period"`

`"Period"`

`0x0035`

`"Slash"`

`"Slash"`

`0x0036`

`"ShiftRight"`

`"ShiftRight"`

`0x0037`

`"NumpadMultiply"`

`"NumpadMultiply"`

`0x0038`

`"AltLeft"`

`"AltLeft"`

`0x0039`

`"Space"`

`"Space"`

`0x003A`

`"CapsLock"`

`"CapsLock"`

`0x003B`

`"F1"`

`"F1"`

`0x003C`

`"F2"`

`"F2"`

`0x003D`

`"F3"`

`"F3"`

`0x003E`

`"F4"`

`"F4"`

`0x003F`

`"F5"`

`"F5"`

`0x0040`

`"F6"`

`"F6"`

`0x0041`

`"F7"`

`"F7"`

`0x0042`

`"F8"`

`"F8"`

`0x0043`

`"F9"`

`"F9"`

`0x0044`

`"F10"`

`"F10"`

`0x0045`

`"Pause"`

`"Pause"`

`0x0046`

`"ScrollLock"`

`"ScrollLock"`

`0x0047`

`"Numpad7"`

`"Numpad7"`

`0x0048`

`"Numpad8"`

`"Numpad8"`

`0x0049`

`"Numpad9"`

`"Numpad9"`

`0x004A`

`"NumpadSubtract"`

`"NumpadSubtract"`

`0x004B`

`"Numpad4"`

`"Numpad4"`

`0x004C`

`"Numpad5"`

`"Numpad5"`

`0x004D`

`"Numpad6"`

`"Numpad6"`

`0x004E`

`"NumpadAdd"`

`"NumpadAdd"`

`0x004F`

`"Numpad1"`

`"Numpad1"`

`0x0050`

`"Numpad2"`

`"Numpad2"`

`0x0051`

`"Numpad3"`

`"Numpad3"`

`0x0052`

`"Numpad0"`

`"Numpad0"`

`0x0053`

`"NumpadDecimal"`

`"NumpadDecimal"`

`0x0054 (Alt + PrintScreen)`

`"PrintScreen"`

`""`

`0x0055`

`"Unidentified"`

`""`

`0x0056`

`"IntlBackslash"`

`"IntlBackslash"`

`0x0057`

`"F11"`

`"F11"`

`0x0058`

`"F12"`

`"F12"`

`0x0059`

`"NumpadEqual"`

`""`

`0x005A`

`"Unidentified"`

`""`

`0x005B`

`"Unidentified"`

`"F13"`

`0x005C`

`"Unidentified"`

`"F14"`

`0x005D`

`"Unidentified"`

`"F15"`

`0x005E`

`"Unidentified"`

`""`

`0x005F`

`"Unidentified"`

`""`

`0x0060`

`"Unidentified"`

`""`

`0x0061`

`"Unidentified"`

`""`

`0x0062`

`"Unidentified"`

`""`

`0x0063`

`"Unidentified"`

`"F16"`

`0x0064`

`"F13"`

`"F17"`

`0x0065`

`"F14"`

`"F18"`

`0x0066`

`"F15"`

`"F19"`

`0x0067`

`"F16"`

`"F20"`

`0x0068`

`"F17"`

`"F21"`

`0x0069`

`"F18"`

`"F22"`

`0x006A`

`"F19"`

`"F23"`

`0x006B`

`"F20"`

`"F24"`

`0x006C`

`"F21"`

`""`

`0x006D`

`"F22"`

`""`

`0x006E`

`"F23"`

`""`

`0x006F`

`"Unidentified"`

`""`

`0x0070`

`"KanaMode"`

`""`

`0x0071` (Hanja key without Korean keyboard layout)

`"Lang2"`

`""`

`0x0072` (Han/Yeong key without Korean keyboard layout)

`"Lang1"`

`""`

`0x0073`

`"IntlRo"`

`""`

`0x0074`, `0x0075`

`"Unidentified"`

`""`

`0x0076`

`"F24"`

`""`

`0x0077`, `0x0078`

`"Unidentified"`

`""`

`0x0079`

`"Convert"`

`""`

`0x007A`

`"Unidentified"`

`""`

`0x007B`

`"NonConvert"`

`""`

`0x007C`

`"Unidentified"`

`""`

`0x007D`

`"IntlYen"`

`"IntlYen"`

`0x007E`

`"NumpadComma"`

`""`

`0x007F`

`"Unidentified"`

`""`

`0xE000` ～ `0xE007`

`"Unidentified"`

`""`

`0xE008`

`"Unidentified"`

`"Undo"`

`0xE009`

`"Unidentified"`

`""`

`0xE00A`

`""`

`"Paste"`

`0xE00B` ～ `0xE00F`

""

`""`

`0xE010`

`"MediaTrackPrevious"`

`"MediaTrackPrevious"`

`0xE011` ～ `0xE016`

`""`

`""`

`0xE017`

`"Unidentified"`

`"Cut"`

`0xE018`

`"Unidentified"`

`"Copy"`

`0xE019`

`"MediaTrackNext"`

`"MediaTrackNext"`

`0xE01A, 0xE01B`

`"Unidentified"`

`""`

`0xE01C`

`"NumpadEnter"`

`"NumpadEnter"`

`0xE01D`

`"ControlRight"`

`"ControlRight"`

`0xE01E`

`"Unidentified"`

`"LaunchMail"`

`0xE01F`

`"Unidentified"`

`""`

`0xE020`

`"AudioVolumeMute"`

`"AudioVolumeMute"`

`0xE021`

`"LaunchApp2"`

`""`

`0xE022`

`"MediaPlayPause"`

`"MediaPlayPause"`

`0xE023`

`"Unidentified"`

`""`

`0xE024`

`"MediaStop"`

`"MediaStop"`

`0xE025` ～ `0xE02B`

`"Unidentified"`

`""`

`0xE02C`

`"Unidentified"`

`"Eject"`

`0xE02D`

`"Unidentified"`

`""`

`0xE02E`

`"AudioVolumeDown"`

`"VolumeDown"` (was `"VolumeDown"` until Chrome 50)

`0xE02F`

`"Unidentified"`

`""`

`0xE030`

`"AudioVolumeUp"`

`"VolumeUp"` (was `"VolumeUp"` until Chrome 50)

`0xE031`

`"Unidentified"`

`""`

`0xE032`

`"BrowserHome"`

`"BrowserHome"`

`0xE033`, `0xE034`

`"Unidentified"`

`""`

`0xE035`

`"NumpadDivide"`

`"NumpadDivide"`

`0xE036`

`"Unidentified"`

`""`

`0xE037`

`"PrintScreen"`

`"PrintScreen"`

`0xE038`

`"AltRight"`

`"AltRight"`

`0xE039`, `0xE03A`

`"Unidentified"`

`""`

`0xE03B`

`"Unidentified"`

`"Help"`

`0xE03C`～ `0xE044`

`"Unidentified"`

`""`

`0xE045`

`"NumLock"`

`"NumLock"`

`0xE046` (Ctrl + Pause)

`"Pause"`

`"Pause"`

`0xE047`

`"Home"`

`"Home"`

`0xE048`

`"ArrowUp"`

`"ArrowUp"`

`0xE049`

`"PageUp"`

`"PageUp"`

`0xE04A`

`"Unidentified"`

`""`

`0xE04B`

`"ArrowLeft"`

`"ArrowLeft"`

`0xE04C`

`"Unidentified"`

`""`

`0xE04D`

`"ArrowRight"`

`"ArrowRight"`

`0xE04E`

`"Unidentified"`

`""`

`0xE04F`

`"End"`

`"End"`

`0xE050`

`"ArrowDown"`

`"ArrowDown"`

`0xE051`

`"PageDown"`

`"PageDown"`

`0xE052`

`"Insert"`

`"Insert"`

`0xE053`

`"Delete"`

`"Delete"`

`0xE054` ～ `0xE05A`

`"Unidentified"`

`""`

`0xE05B`

`"MetaLeft"`

`"OSLeft"`

`0xE05C`

`"MetaRight"`

`"OSRight"`

`0xE05D`

`"ContextMenu"`

`"ContextMenu"`

`0xE05E`

`"Power"`

`""`

`0xE05F` ～ `0xE064`

`"Unidentified"`

`""`

`0xE065`

`"BrowserSearch"`

`"BrowserSearch"`

`0xE066`

`"BrowserFavorites"`

`"BrowserFavorites"`

`0xE067`

`"BrowserRefresh"`

`"BrowserRefresh"`

`0xE068`

`"BrowserStop"`

`"BrowserStop"`

`0xE069`

`"BrowserForward"`

`"BrowserForward"`

`0xE06A`

`"BrowserBack"`

`"BrowserBack"`

`0xE06B`

`"LaunchApp1"`

`""`

`0xE06C`

`"LaunchMail"`

`""`

`0xE06D`

`"LaunchMediaPlayer"` (`"MediaSelect"` prior to Firefox 49)

`""`

`0xE06E ～ 0xE0F0`

`"Unidentified"`

`""`

`0xE0F1` (Hanja key with Korean keyboard layout)

`"Lang2"`

`""`

`0xE0F2` (Han/Yeong key with Korean keyboard layout)

`"Lang1"`

`""`

### Code values on Mac

On Mac OS X, it's hard to get scancode or something which can distinguish a physical key from a key event. Therefore, Gecko always maps `code` value from the virtual keycode.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Virtual keycode</th><th>Gecko</th><th>Chromium (48)</th></tr></thead><tbody><tr class="odd"><td><code>kVK_ANSI_A (0x00)</code></td><td><code>"KeyA"</code></td><td><code>"KeyA"</code></td></tr><tr class="even"><td><code>kVK_ANSI_S (0x01)</code></td><td><code>"KeyS"</code></td><td><code>"KeyS"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_D (0x02)</code></td><td><code>"KeyD"</code></td><td><code>"KeyD"</code></td></tr><tr class="even"><td><code>kVK_ANSI_F (0x03)</code></td><td><code>"KeyF"</code></td><td><code>"KeyF"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_H (0x04)</code></td><td><code>"KeyH"</code></td><td><code>"KeyH"</code></td></tr><tr class="even"><td><code>kVK_ANSI_G (0x05)</code></td><td><code>"KeyG"</code></td><td><code>"KeyG"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Z (0x06)</code></td><td><code>"KeyZ"</code></td><td><code>"KeyZ"</code></td></tr><tr class="even"><td><code>kVK_ANSI_X (0x07)</code></td><td><code>"KeyX"</code></td><td><code>"KeyX"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_C (0x08)</code></td><td><code>"KeyC"</code></td><td><code>"KeyC"</code></td></tr><tr class="even"><td><code>kVK_ANSI_V (0x09)</code></td><td><code>"KeyV"</code></td><td><code>"KeyV"</code></td></tr><tr class="odd"><td><code>kVK_ISO_Section (0x0A)</code></td><td><code>"IntlBackslash"</code></td><td><code>"IntlBackslash"</code></td></tr><tr class="even"><td><code>kVK_ANSI_B (0x0B)</code></td><td><code>"KeyB"</code></td><td><code>"KeyB"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Q (0x0C)</code></td><td><code>"KeyQ"</code></td><td><code>"KeyQ"</code></td></tr><tr class="even"><td><code>kVK_ANSI_W (0x0D)</code></td><td><code>"KeyW"</code></td><td><code>"KeyW"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_E (0x0E)</code></td><td><code>"KeyE"</code></td><td><code>"KeyE"</code></td></tr><tr class="even"><td><code>kVK_ANSI_R (0x0F)</code></td><td><code>"KeyR"</code></td><td><code>"KeyR"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Y (0x10)</code></td><td><code>"KeyY"</code></td><td><code>"KeyY"</code></td></tr><tr class="even"><td><code>kVK_ANSI_T (0x11)</code></td><td><code>"KeyT"</code></td><td><code>"KeyT"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_1 (0x12)</code></td><td><code>"Digit1"</code></td><td><code>"Digit1"</code></td></tr><tr class="even"><td><code>kVK_ANSI_2 (0x13)</code></td><td><code>"Digit2"</code></td><td><code>"Digit2"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_3 (0x14)</code></td><td><code>"Digit3"</code></td><td><code>"Digit3"</code></td></tr><tr class="even"><td><code>kVK_ANSI_4 (0x15)</code></td><td><code>"Digit4"</code></td><td><code>"Digit4"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_6 (0x16)</code></td><td><code>"Digit6"</code></td><td><code>"Digit6"</code></td></tr><tr class="even"><td><code>kVK_ANSI_5 (0x17)</code></td><td><code>"Digit5"</code></td><td><code>"Digit5"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Equal (0x18)</code></td><td><code>"Equal"</code></td><td><code>"Equal"</code></td></tr><tr class="even"><td><code>kVK_ANSI_9 (0x19)</code></td><td><code>"Digit9"</code></td><td><code>"Digit9"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_7 (0x1A)</code></td><td><code>"Digit7"</code></td><td><code>"Digit7"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Minus (0x1B)</code></td><td><code>"Minus"</code></td><td><code>"Minus"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_8 (0x1C)</code></td><td><code>"Digit8"</code></td><td><code>"Digit8"</code></td></tr><tr class="even"><td><code>kVK_ANSI_0 (0x1D)</code></td><td><code>"Digit0"</code></td><td><code>"Digit0"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_RightBracket (0x1E)</code></td><td><code>"BracketRight"</code></td><td><code>"BracketRight"</code></td></tr><tr class="even"><td><code>kVK_ANSI_O (0x1F)</code></td><td><code>"KeyO"</code></td><td><code>"KeyO"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_U (0x20)</code></td><td><code>"KeyU"</code></td><td><code>"KeyU"</code></td></tr><tr class="even"><td><code>kVK_ANSI_LeftBracket (0x21)</code></td><td><code>"BracketLeft"</code></td><td><code>"BracketLeft"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_I (0x22)</code></td><td><code>"KeyI"</code></td><td><code>"KeyI"</code></td></tr><tr class="even"><td><code>kVK_ANSI_P (0x23)</code></td><td><code>"KeyP"</code></td><td><code>"KeyP"</code></td></tr><tr class="odd"><td><code>kVK_Return (0x24)</code></td><td><code>"Enter"</code></td><td><code>"Enter"</code></td></tr><tr class="even"><td><code>kVK_ANSI_L (0x25)</code></td><td><code>"KeyL"</code></td><td><code>"KeyL"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_J (0x26)</code></td><td><code>"KeyJ"</code></td><td><code>"KeyJ"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Quote (0x27)</code></td><td><code>"Quote"</code></td><td><code>"Quote"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_K (0x28)</code></td><td><code>"KeyK"</code></td><td><code>"KeyK"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Semicolon (0x29)</code></td><td><code>"Semicolon"</code></td><td><code>"Semicolon"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Backslash (0x2A)</code></td><td><code>"Backslash"</code></td><td><code>"Backslash"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Comma (0x2B)</code></td><td><code>"Comma"</code></td><td><code>"Comma"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Slash (0x2C)</code></td><td><code>"Slash"</code></td><td><code>"Slash"</code></td></tr><tr class="even"><td><code>kVK_ANSI_N (0x2D)</code></td><td><code>"KeyN"</code></td><td><code>"KeyN"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_M (0x2E)</code></td><td><code>"KeyM"</code></td><td><code>"KeyM"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Period (0x2F)</code></td><td><code>"Period"</code></td><td><code>"Period"</code></td></tr><tr class="odd"><td><code>kVK_Tab (0x30)</code></td><td><code>"Tab"</code></td><td><code>"Tab"</code></td></tr><tr class="even"><td><code>kVK_Space (0x31)</code></td><td><code>"Space"</code></td><td><code>"Space"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Grave (0x32)</code></td><td><code>"Backquote"</code></td><td><code>"Backquote"</code></td></tr><tr class="even"><td><code>kVK_Delete (0x33)</code></td><td><code>"Backspace"</code></td><td><code>"Backspace"</code></td></tr><tr class="odd"><td>Enter key on keypad of PowerBook (<code>0x34</code>)</td><td><code>"NumpadEnter"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>kVK_Escape (0x35)</code></td><td><code>"Escape"</code></td><td><code>"Escape"</code></td></tr><tr class="odd"><td>right-command key (<code>0x36</code>)</td><td><code>"OSRight"</code></td><td><code>"OSRight"</code></td></tr><tr class="even"><td><code>kVK_Command (0x37)</code></td><td><code>"OSLeft"</code></td><td><code>"OSLeft"</code></td></tr><tr class="odd"><td><code>kVK_Shift (0x38)</code></td><td><code>"ShiftLeft"</code></td><td><code>"ShiftLeft"</code></td></tr><tr class="even"><td><code>kVK_CapsLock (0x39)</code></td><td><code>"CapsLock"</code></td><td><code>"CapsLock"</code></td></tr><tr class="odd"><td><code>kVK_Option (0x3A)</code></td><td><code>"AltLeft"</code></td><td><code>"AltLeft"</code></td></tr><tr class="even"><td><code>kVK_Control (0x3B)</code></td><td><code>"ControlLeft"</code></td><td><code>"ControlLeft"</code></td></tr><tr class="odd"><td><code>kVK_RightShift (0x3C)</code></td><td><code>"ShiftRight"</code></td><td><code>"ShiftRight"</code></td></tr><tr class="even"><td><code>kVK_RightOption (0x3D)</code></td><td><code>"AltRight"</code></td><td><code>"AltRight"</code></td></tr><tr class="odd"><td><code>kVK_RightControl (0x3E)</code></td><td><code>"ControlRight"</code></td><td><code>"ControlRight"</code></td></tr><tr class="even"><td><code>kVK_Function (0x3F)</code></td><td><code>"Fn"</code> <em>(no events fired actually)</em></td><td><code>""</code> <em>(no events fired actually)</em></td></tr><tr class="odd"><td><code>kVK_F17 (0x40)</code></td><td><code>"F17"</code></td><td><code>"F17"</code></td></tr><tr class="even"><td><code>kVK_ANSI_KeypadDecimal (0x41)</code></td><td><code>"NumpadDecimal"</code></td><td><code>"NumpadDecimal"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_KeypadMultiply (0x43)</code></td><td><code>"NumpadMultiply"</code></td><td><code>"NumpadMultiply"</code></td></tr><tr class="even"><td><code>kVK_ANSI_KeypadPlus (0x45)</code></td><td><code>"NumpadAdd"</code></td><td><code>"NumpadAdd"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_KeypadClear (0x47)</code></td><td><code>"NumLock"</code></td><td><code>"NumLock"</code></td></tr><tr class="even"><td><code>kVK_VolumeUp (0x48)</code></td><td><code>"AudioVolumeUp" </code>(was <code>"VolumeUp"</code> until Firefox 48)</td><td><code>"AudioVolumeUp" </code>(was <code>"VolumeUp"</code> until Chrome 50)</td></tr><tr class="odd"><td><code>kVK_VolumeDown (0x49)</code></td><td><code>"AudioVolumeDown"</code> (was <code>"VolumeDown"</code> until Firefox 49)</td><td><code>"AudioVolumeDown"</code> (was <code>"VolumeDown"</code> until Chrome 50)</td></tr><tr class="even"><td><code>kVK_Mute (0x4A)</code></td><td><code>"AudioVolumeMute"</code> (was <code>"VolumeMute"</code> until Firefox 49)</td><td><code>"AudioVolumeMute"</code> (was <code>"VolumeMute"</code> until Chrome 50)</td></tr><tr class="odd"><td><code>kVK_ANSI_KeypadDivide (0x4B)</code></td><td><code>"NumpadDivide"</code></td><td><code>"NumpadDivide"</code></td></tr><tr class="even"><td><code>kVK_ANSI_KeypadEnter (0x4C)</code></td><td><code>"NumpadEnter"</code></td><td><code>"NumpadEnter"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_KeypadMinus (0x4E)</code></td><td><code>"NumpadSubtract"</code></td><td><code>"NumpadSubtract"</code></td></tr><tr class="even"><td><code>kVK_F18 (0x4F)</code></td><td><code>"F18"</code></td><td><code>"F18"</code></td></tr><tr class="odd"><td><code>kVK_F19 (0x50)</code></td><td><code>"F19"</code></td><td><code>"F19"</code></td></tr><tr class="even"><td><code>kVK_ANSI_KeypadEquals (0x51)</code></td><td><code>"NumpadEqual"</code></td><td><code>"NumpadEqual"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Keypad0 (0x52)</code></td><td><code>"Numpad0"</code></td><td><code>"Numpad0"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Keypad1 (0x53)</code></td><td><code>"Numpad1"</code></td><td><code>"Numpad1"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Keypad2 (0x54)</code></td><td><code>"Numpad2"</code></td><td><code>"Numpad2"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Keypad3 (0x55)</code></td><td><code>"Numpad3"</code></td><td><code>"Numpad3"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Keypad4 (0x56)</code></td><td><code>"Numpad4"</code></td><td><code>"Numpad4"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Keypad5 (0x57)</code></td><td><code>"Numpad5"</code></td><td><code>"Numpad5"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Keypad6 (0x58)</code></td><td><code>"Numpad6"</code></td><td><code>"Numpad6"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Keypad7 (0x59)</code></td><td><code>"Numpad7"</code></td><td><code>"Numpad7"</code></td></tr><tr class="odd"><td><code>kVK_F20 (0x5A)</code></td><td><code>"F20"</code></td><td><code>"F20"</code></td></tr><tr class="even"><td><code>kVK_ANSI_Keypad8 (0x5B)</code></td><td><code>"Numpad8"</code></td><td><code>"Numpad8"</code></td></tr><tr class="odd"><td><code>kVK_ANSI_Keypad9 (0x5C)</code></td><td><code>"Numpad9"</code></td><td><code>"Numpad9"</code></td></tr><tr class="even"><td><code>kVK_JIS_Yen (0x5D)</code></td><td><code>"IntlYen"</code></td><td><code>"IntlYen"</code></td></tr><tr class="odd"><td><code>kVK_JIS_Underscore (0x5E)</code></td><td><code>"IntlRo"</code></td><td><code>"IntlRo"</code></td></tr><tr class="even"><td><code>kVK_JIS_KeypadComma (0x5F)</code></td><td><code>"NumpadComma"</code></td><td><code>"NumpadComma"</code></td></tr><tr class="odd"><td><code>kVK_F5 (0x60)</code></td><td><code>"F5"</code></td><td><code>"F5"</code></td></tr><tr class="even"><td><code>kVK_F6 (0x61)</code></td><td><code>"F6"</code></td><td><code>"F6"</code></td></tr><tr class="odd"><td><code>kVK_F7 (0x62)</code></td><td><code>"F7"</code></td><td><code>"F7"</code></td></tr><tr class="even"><td><code>kVK_F3 (0x63)</code></td><td><code>"F3"</code></td><td><code>"F3"</code></td></tr><tr class="odd"><td><code>kVK_F8 (0x64)</code></td><td><code>"F8"</code></td><td><code>"F8"</code></td></tr><tr class="even"><td><code>kVK_F9 (0x65)</code></td><td><code>"F9"</code></td><td><code>"F9"</code></td></tr><tr class="odd"><td><code>kVK_JIS_Eisu (0x66)</code></td><td><p><code>"Lang2"</code></p></td><td><code>""</code> <em>(no events fired actually)</em></td></tr><tr class="even"><td><code>kVK_F11 (0x67)</code></td><td><code>"F11"</code></td><td><code>"F11"</code></td></tr><tr class="odd"><td><code>kVK_JIS_Kana (0x68)</code></td><td><code>"Lang1"</code></td><td><code>"KanaMode"</code> <em>(no events fired actually)</em></td></tr><tr class="even"><td><code>kVK_F13 (0x69)</code></td><td><code>"F13"</code></td><td><code>"F13"</code></td></tr><tr class="odd"><td><code>kVK_F16 (0x6A)</code></td><td><code>"F16"</code></td><td><code>"F16"</code></td></tr><tr class="even"><td><code>kVK_F14 (0x6B)</code></td><td><code>"F14"</code></td><td><code>"F14"</code></td></tr><tr class="odd"><td><code>kVK_F10 (0x6D)</code></td><td><code>"F10"</code></td><td><code>"F10"</code></td></tr><tr class="even"><td><code>kVK_F12 (0x6F)</code></td><td><code>"F12"</code></td><td><code>"F12"</code></td></tr><tr class="odd"><td><code>kVK_F15 (0x71)</code></td><td><code>"F15"</code></td><td><code>"F15"</code></td></tr><tr class="even"><td><code>kVK_Help (0x72)</code></td><td><code>"Help"</code></td><td><code>"Insert"</code></td></tr><tr class="odd"><td><code>kVK_Home (0x73)</code></td><td><code>"Home"</code></td><td><code>"Home"</code></td></tr><tr class="even"><td><code>kVK_PageUp (0x74)</code></td><td><code>"PageUp"</code></td><td><code>"PageUp"</code></td></tr><tr class="odd"><td><code>kVK_ForwardDelete (0x75)</code></td><td><code>"Delete"</code></td><td><code>"Delete"</code></td></tr><tr class="even"><td><code>kVK_F4 (0x76)</code></td><td><code>"F4"</code></td><td><code>"F4"</code></td></tr><tr class="odd"><td><code>kVK_End (0x77)</code></td><td><code>"End"</code></td><td><code>"End"</code></td></tr><tr class="even"><td><code>kVK_F2 (0x78)</code></td><td><code>"F2"</code></td><td><code>"F2"</code></td></tr><tr class="odd"><td><code>kVK_PageDown (0x79)</code></td><td><code>"PageDown"</code></td><td><code>"PageDown"</code></td></tr><tr class="even"><td><code>kVK_F1 (0x7A)</code></td><td><code>"F1"</code></td><td><code>"F1"</code></td></tr><tr class="odd"><td><code>kVK_LeftArrow (0x7B)</code></td><td><code>"ArrowLeft"</code></td><td><code>"ArrowLeft"</code></td></tr><tr class="even"><td><code>kVK_RightArrow (0x7C)</code></td><td><code>"ArrowRight"</code></td><td><code>"ArrowRight"</code></td></tr><tr class="odd"><td><code>kVK_DownArrow (0x7D)</code></td><td><code>"ArrowDown"</code></td><td><code>"ArrowDown"</code></td></tr><tr class="even"><td><code>kVK_UpArrow (0x7E)</code></td><td><code>"ArrowUp"</code></td><td><code>"ArrowUp"</code></td></tr></tbody></table>

### Code values on Linux (X11) (When scancode is available)

Note that X has too many keys and some of them are not testable with usual keyboard. So, following table is created from source code which maps from scancode to code value.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>scancode (hardware_keycode)</th><th>Gecko</th><th>Chromium (44)</th></tr></thead><tbody><tr class="odd"><td><code>0x0009</code></td><td><code>"Escape"</code></td><td><code>"Escape"</code></td></tr><tr class="even"><td><code>0x000A</code></td><td><code>"Digit1"</code></td><td><code>"Digit1"</code></td></tr><tr class="odd"><td><code>0x000B</code></td><td><code>"Digit2"</code></td><td><code>"Digit2"</code></td></tr><tr class="even"><td><code>0x000C</code></td><td><code>"Digit3"</code></td><td><code>"Digit3"</code></td></tr><tr class="odd"><td><code>0x000D</code></td><td><code>"Digit4"</code></td><td><code>"Digit4"</code></td></tr><tr class="even"><td><code>0x000E</code></td><td><code>"Digit5"</code></td><td><code>"Digit5"</code></td></tr><tr class="odd"><td><code>0x000F</code></td><td><code>"Digit6"</code></td><td><code>"Digit6"</code></td></tr><tr class="even"><td><code>0x0010</code></td><td><code>"Digit7"</code></td><td><code>"Digit7"</code></td></tr><tr class="odd"><td><code>0x0011</code></td><td><code>"Digit8"</code></td><td><code>"Digit8"</code></td></tr><tr class="even"><td><code>0x0012</code></td><td><code>"Digit9"</code></td><td><code>"Digit9"</code></td></tr><tr class="odd"><td><code>0x0013</code></td><td><code>"Digit0"</code></td><td><code>"Digit0"</code></td></tr><tr class="even"><td><code>0x0014</code></td><td><code>"Minus"</code></td><td><code>"Minus"</code></td></tr><tr class="odd"><td><code>0x0015</code></td><td><code>"Equal"</code></td><td><code>"Equal"</code></td></tr><tr class="even"><td><code>0x0016</code></td><td><code>"Backspace"</code></td><td><code>"Backspace"</code></td></tr><tr class="odd"><td><code>0x0017</code></td><td><code>"Tab"</code></td><td><code>"Tab"</code></td></tr><tr class="even"><td><code>0x0018</code></td><td><code>"KeyQ"</code></td><td><code>"KeyQ"</code></td></tr><tr class="odd"><td><code>0x0019</code></td><td><code>"KeyW"</code></td><td><code>"KeyW"</code></td></tr><tr class="even"><td><code>0x001A</code></td><td><code>"KeyE"</code></td><td><code>"KeyE"</code></td></tr><tr class="odd"><td><code>0x001B</code></td><td><code>"KeyR"</code></td><td><code>"KeyR"</code></td></tr><tr class="even"><td><code>0x001C</code></td><td><code>"KeyT"</code></td><td><code>"KeyT"</code></td></tr><tr class="odd"><td><code>0x001D</code></td><td><code>"KeyY"</code></td><td><code>"KeyY"</code></td></tr><tr class="even"><td><code>0x001E</code></td><td><code>"KeyU"</code></td><td><code>"KeyU"</code></td></tr><tr class="odd"><td><code>0x001F</code></td><td><code>"KeyI"</code></td><td><code>"KeyI"</code></td></tr><tr class="even"><td><code>0x0020</code></td><td><code>"KeyO"</code></td><td><code>"KeyO"</code></td></tr><tr class="odd"><td><code>0x0021</code></td><td><code>"KeyP"</code></td><td><code>"KeyP"</code></td></tr><tr class="even"><td><code>0x0022</code></td><td><code>"BracketLeft"</code></td><td><code>"BracketLeft"</code></td></tr><tr class="odd"><td><code>0x0023</code></td><td><code>"BracketRight"</code></td><td><code>"BracketRight"</code></td></tr><tr class="even"><td><code>0x0024</code></td><td><code>"Enter"</code></td><td><code>"Enter"</code></td></tr><tr class="odd"><td><code>0x0025</code></td><td><code>"ControlLeft"</code></td><td><code>"ControlLeft"</code></td></tr><tr class="even"><td><code>0x0026</code></td><td><code>"KeyA"</code></td><td><code>"KeyA"</code></td></tr><tr class="odd"><td><code>0x0027</code></td><td><code>"KeyS"</code></td><td><code>"KeyS"</code></td></tr><tr class="even"><td><code>0x0028</code></td><td><code>"KeyD"</code></td><td><code>"KeyD"</code></td></tr><tr class="odd"><td><code>0x0029</code></td><td><code>"KeyF"</code></td><td><code>"KeyF"</code></td></tr><tr class="even"><td><code>0x002A</code></td><td><code>"KeyG"</code></td><td><code>"KeyG"</code></td></tr><tr class="odd"><td><code>0x002B</code></td><td><code>"KeyH"</code></td><td><code>"KeyH"</code></td></tr><tr class="even"><td><code>0x002C</code></td><td><code>"KeyJ"</code></td><td><code>"KeyJ"</code></td></tr><tr class="odd"><td><code>0x002D</code></td><td><code>"KeyK"</code></td><td><code>"KeyK"</code></td></tr><tr class="even"><td><code>0x002E</code></td><td><code>"KeyL"</code></td><td><code>"KeyL"</code></td></tr><tr class="odd"><td><code>0x002F</code></td><td><code>"Semicolon"</code></td><td><code>"Semicolon"</code></td></tr><tr class="even"><td><code>0x0030</code></td><td><code>"Quote"</code></td><td><code>"Quote"</code></td></tr><tr class="odd"><td><code>0x0031</code></td><td><code>"Backquote"</code></td><td><code>"Backquote"</code></td></tr><tr class="even"><td><code>0x0032</code></td><td><code>"ShiftLeft"</code></td><td><code>"ShiftLeft"</code></td></tr><tr class="odd"><td><code>0x0033</code></td><td><code>"Backslash"</code></td><td><code>"Backslash"</code></td></tr><tr class="even"><td><code>0x0034</code></td><td><code>"KeyZ"</code></td><td><code>"KeyZ"</code></td></tr><tr class="odd"><td><code>0x0035</code></td><td><code>"KeyX"</code></td><td><code>"KeyX"</code></td></tr><tr class="even"><td><code>0x0036</code></td><td><code>"KeyC"</code></td><td><code>"KeyC"</code></td></tr><tr class="odd"><td><code>0x0037</code></td><td><code>"KeyV"</code></td><td><code>"KeyV"</code></td></tr><tr class="even"><td><code>0x0038</code></td><td><code>"KeyB"</code></td><td><code>"KeyB"</code></td></tr><tr class="odd"><td><code>0x0039</code></td><td><code>"KeyN"</code></td><td><code>"KeyN"</code></td></tr><tr class="even"><td><code>0x003A</code></td><td><code>"KeyM"</code></td><td><code>"KeyM"</code></td></tr><tr class="odd"><td><code>0x003B</code></td><td><code>"Comma"</code></td><td><code>"Comma"</code></td></tr><tr class="even"><td><code>0x003C</code></td><td><code>"Period"</code></td><td><code>"Period"</code></td></tr><tr class="odd"><td><code>0x003D</code></td><td><code>"Slash"</code></td><td><code>"Slash"</code></td></tr><tr class="even"><td><code>0x003E</code></td><td><code>"ShiftRight"</code></td><td><code>"ShiftRight"</code></td></tr><tr class="odd"><td><code>0x003F</code></td><td><code>"NumpadMultiply"</code></td><td><code>"NumpadMultiply"</code></td></tr><tr class="even"><td><code>0x0040</code></td><td><code>"AltLeft"</code></td><td><code>"AltLeft"</code></td></tr><tr class="odd"><td><code>0x0041</code></td><td><code>"Space"</code></td><td><code>"Space"</code></td></tr><tr class="even"><td><code>0x0042</code></td><td><code>"CapsLock"</code></td><td><code>"CapsLock"</code></td></tr><tr class="odd"><td><code>0x0043</code></td><td><code>"F1"</code></td><td><code>"F1"</code></td></tr><tr class="even"><td><code>0x0044</code></td><td><code>"F2"</code></td><td><code>"F2"</code></td></tr><tr class="odd"><td><code>0x0045</code></td><td><code>"F3"</code></td><td><code>"F3"</code></td></tr><tr class="even"><td><code>0x0046</code></td><td><code>"F4"</code></td><td><code>"F4"</code></td></tr><tr class="odd"><td><code>0x0047</code></td><td><code>"F5"</code></td><td><code>"F5"</code></td></tr><tr class="even"><td><code>0x0048</code></td><td><code>"F6"</code></td><td><code>"F6"</code></td></tr><tr class="odd"><td><code>0x0049</code></td><td><code>"F7"</code></td><td><code>"F7"</code></td></tr><tr class="even"><td><code>0x004A</code></td><td><code>"F8"</code></td><td><code>"F8"</code></td></tr><tr class="odd"><td><code>0x004B</code></td><td><code>"F9"</code></td><td><code>"F9"</code></td></tr><tr class="even"><td><code>0x004C</code></td><td><code>"F10"</code></td><td><code>"F10"</code></td></tr><tr class="odd"><td><code>0x004D</code></td><td><code>"NumLock"</code></td><td><code>"NumLock"</code></td></tr><tr class="even"><td><code>0x004E</code></td><td><code>"ScrollLock"</code></td><td><code>"ScrollLock"</code></td></tr><tr class="odd"><td><code>0x004F</code></td><td><code>"Numpad7"</code></td><td><code>"Numpad7"</code></td></tr><tr class="even"><td><code>0x0050</code></td><td><code>"Numpad8"</code></td><td><code>"Numpad8"</code></td></tr><tr class="odd"><td><code>0x0051</code></td><td><code>"Numpad9"</code></td><td><code>"Numpad9"</code></td></tr><tr class="even"><td><code>0x0052</code></td><td><code>"NumpadSubtract"</code></td><td><code>"NumpadSubtract"</code></td></tr><tr class="odd"><td><code>0x0053</code></td><td><code>"Numpad4"</code></td><td><code>"Numpad4"</code></td></tr><tr class="even"><td><code>0x0054</code></td><td><code>"Numpad5"</code></td><td><code>"Numpad5"</code></td></tr><tr class="odd"><td><code>0x0055</code></td><td><code>"Numpad6"</code></td><td><code>"Numpad6"</code></td></tr><tr class="even"><td><code>0x0056</code></td><td><code>"NumpadAdd"</code></td><td><code>"NumpadAdd"</code></td></tr><tr class="odd"><td><code>0x0057</code></td><td><code>"Numpad1"</code></td><td><code>"Numpad1"</code></td></tr><tr class="even"><td><code>0x0058</code></td><td><code>"Numpad2"</code></td><td><code>"Numpad2"</code></td></tr><tr class="odd"><td><code>0x0059</code></td><td><code>"Numpad3"</code></td><td><code>"Numpad3"</code></td></tr><tr class="even"><td><code>0x005A</code></td><td><code>"Numpad0"</code></td><td><code>"Numpad0"</code></td></tr><tr class="odd"><td><code>0x005B</code></td><td><code>"NumpadDecimal"</code></td><td><code>"NumpadDecimal"</code></td></tr><tr class="even"><td><code>0x005C</code>, <code>0x005D</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x005E</code></td><td><code>"IntlBackslash"</code></td><td><code>"IntlBackslash"</code></td></tr><tr class="even"><td><code>0x005F</code></td><td><code>"F11"</code></td><td><code>"F11"</code></td></tr><tr class="odd"><td><code>0x0060</code></td><td><code>"F12"</code></td><td><code>"F12"</code></td></tr><tr class="even"><td><code>0x0061</code></td><td><code>"IntlRo"</code></td><td><code>"IntlRo"</code></td></tr><tr class="odd"><td><code>0x0062</code>, <code>0x0063</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0064</code></td><td><code>"Convert"</code></td><td><code>"Convert"</code></td></tr><tr class="odd"><td><code>0x0065</code></td><td><code>"KanaMode"</code></td><td><code>"KanaMode"</code></td></tr><tr class="even"><td><code>0x0066</code></td><td><code>"NonConvert"</code></td><td><code>"NonConvert"</code></td></tr><tr class="odd"><td><code>0x0067</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0068</code></td><td><code>"NumpadEnter"</code></td><td><code>"NumpadEnter"</code></td></tr><tr class="odd"><td><code>0x0069</code></td><td><code>"ControlRight"</code></td><td><code>"ControlRight"</code></td></tr><tr class="even"><td><code>0x006A</code></td><td><code>"NumpadDivide"</code></td><td><code>"NumpadDivide"</code></td></tr><tr class="odd"><td><code>0x006B</code></td><td><code>"PrintScreen"</code></td><td><code>"PrintScreen"</code></td></tr><tr class="even"><td><code>0x006C</code></td><td><code>"AltRight"</code></td><td><code>"AltRight"</code></td></tr><tr class="odd"><td><code>0x006D</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x006E</code></td><td><code>"Home"</code></td><td><code>"Home"</code></td></tr><tr class="odd"><td><code>0x006F</code></td><td><code>"ArrowUp"</code></td><td><code>"ArrowUp"</code></td></tr><tr class="even"><td><code>0x0070</code></td><td><code>"PageUp"</code></td><td><code>"PageUp"</code></td></tr><tr class="odd"><td><code>0x0071</code></td><td><code>"ArrowLeft"</code></td><td><code>"ArrowLeft"</code></td></tr><tr class="even"><td><code>0x0072</code></td><td><code>"ArrowRight"</code></td><td><code>"ArrowRight"</code></td></tr><tr class="odd"><td><code>0x0073</code></td><td><code>"End"</code></td><td><code>"End"</code></td></tr><tr class="even"><td><code>0x0074</code></td><td><code>"ArrowDown"</code></td><td><code>"ArrowDown"</code></td></tr><tr class="odd"><td><code>0x0075</code></td><td><code>"PageDown"</code></td><td><code>"PageDown"</code></td></tr><tr class="even"><td><code>0x0076</code></td><td><code>"Insert"</code></td><td><code>"Insert"</code></td></tr><tr class="odd"><td><code>0x0077</code></td><td><code>"Delete"</code></td><td><code>"Delete"</code></td></tr><tr class="even"><td><code>0x0078</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x0079</code></td><td><code>"AudioVolumeMute"</code></td><td><code>"AudioVolumeMute"</code> (was <code>"VolumeMute"</code> until Chrome 50)</td></tr><tr class="even"><td><code>0x007A</code></td><td><code>"AudioVolumeDown"</code></td><td><code>"AudioVolumeDown"</code> (was <code>"VolumeDown"</code> until Chrome 50)</td></tr><tr class="odd"><td><code>0x007B</code></td><td><code>"AudioVolumeUp"</code></td><td><code>"AudioVolumeUp"</code> (was <code>"VolumeUp"</code> until Chrome 50)</td></tr><tr class="even"><td><code>0x007C</code></td><td><code>"Unidentified"</code></td><td><code>"Power"</code></td></tr><tr class="odd"><td><code>0x007D</code></td><td><code>"NumpadEqual"</code></td><td><code>"NumpadEqual"</code></td></tr><tr class="even"><td><code>0x007E</code></td><td><code>"Unidentified"</code></td><td><code>"NumpadChangeSign"</code></td></tr><tr class="odd"><td><code>0x007F</code></td><td><code>"Pause"</code></td><td><code>"Pause"</code></td></tr><tr class="even"><td><code>0x0080</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x0081</code></td><td><code>"NumpadComma"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0082</code></td><td><code>"Lang1"</code></td><td><code>"HangulMode"</code></td></tr><tr class="odd"><td><code>0x0083</code></td><td><code>"Lang2"</code></td><td><code>"Hanja"</code></td></tr><tr class="even"><td><code>0x0084</code></td><td><code>"IntlYen"</code></td><td><code>"IntlYen"</code></td></tr><tr class="odd"><td><code>0x0085</code></td><td><code>"OSLeft"</code></td><td><code>"OSLeft"</code></td></tr><tr class="even"><td><code>0x0086</code></td><td><code>"OSRight"</code></td><td><code>"OSRight"</code></td></tr><tr class="odd"><td><code>0x0087</code></td><td><code>"ContextMenu"</code></td><td><code>"ContextMenu"</code></td></tr><tr class="even"><td><code>0x0088</code></td><td><code>"BrowserStop"</code></td><td><code>"Cancel"</code></td></tr><tr class="odd"><td><code>0x0089</code></td><td>"Again"</td><td><code>""</code></td></tr><tr class="even"><td><code>0x008A</code></td><td><code>"Props"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x008B</code></td><td><code>"Undo"</code></td><td><code>"Undo"</code></td></tr><tr class="even"><td><code>0x008C</code></td><td><code>"Select"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x008D</code></td><td><code>"Copy"</code></td><td><code>"Copy"</code></td></tr><tr class="even"><td><code>0x008E</code></td><td><code>"Open"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x008F</code></td><td><code>"Paste"</code></td><td><code>"Paste"</code></td></tr><tr class="even"><td><code>0x0090</code></td><td><code>"Find"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x0091</code></td><td><code>"Cut"</code></td><td><code>"Cut"</code></td></tr><tr class="even"><td><code>0x0092</code></td><td><code>"Help"</code></td><td><code>"Help"</code></td></tr><tr class="odd"><td><code>0x0093</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0094</code></td><td><code>"LaunchApp2"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x0095</code>, <code>0x0096</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0097</code></td><td><code>"WakeUp"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x0098</code></td><td><code>"LaunchApp1"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x0099</code> ～ <code>0x00A2</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00A3</code></td><td><code>"LaunchMail"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00A4</code></td><td><code>"BrowserFavorites"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00A5</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00A6</code></td><td><code>"BrowserBack"</code></td><td><code>"BrowserBack"</code></td></tr><tr class="odd"><td><code>0x00A7</code></td><td><code>"BrowserForward"</code></td><td><code>"BrowserForward"</code></td></tr><tr class="even"><td><code>0x00A8</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00A9</code></td><td><code>"Eject"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00AA</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00AB</code></td><td><code>"MediaTrackNext"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00AC</code></td><td><code>"MediaPlayPause"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00AD</code></td><td><code>"MediaTrackPrevious"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00AE</code></td><td><code>"MediaStop"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00AF</code> ～ <code>0x00B2</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00B3</code></td><td><code>"LaunchMediaPlayer"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00B4</code></td><td><code>"BrowserHome"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00B5</code></td><td><code>"BrowserRefresh"</code></td><td><code>"BrowserRefresh"</code></td></tr><tr class="odd"><td><code>0x00B6</code> ～ <code>0x00BA</code></td><td><code>"Unidentified"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00BB</code></td><td><p><code>"Unidentified"</code></p></td><td><code>"NumpadParenLeft"</code></td></tr><tr class="odd"><td><code>0x00BC</code></td><td><p><code>"Unidentified"</code></p></td><td><code>"NumpadParenRight"</code></td></tr><tr class="even"><td><code>0x00BD</code>, <code>0x00BE</code></td><td><p><code>"Unidentified"</code></p></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00BF</code></td><td><code>"F13"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00C0</code></td><td><code>"F14"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00C1</code></td><td><code>"F15"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00C2</code></td><td><code>"F16"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00C3</code></td><td><code>"F17"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00C4</code></td><td><code>"F18"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00C5</code></td><td><code>"F19"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00C6</code></td><td><code>"F20"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00C7</code></td><td><code>"F21"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00C8</code></td><td><code>"F22"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00C9</code></td><td><code>"F23"</code></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00CA</code></td><td><code>"F24"</code></td><td><code>""</code></td></tr><tr class="odd"><td><code>0x00CB ～ 0x00E0</code></td><td><p><code>"Unidentified"</code></p></td><td><code>""</code></td></tr><tr class="even"><td><code>0x00E1</code></td><td><code>"BrowserSearch"</code></td><td><code>""</code></td></tr></tbody></table>

### Code values on Android and Firefox OS (When scancode is available)

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>scancode</th><th>Gecko</th></tr></thead><tbody><tr class="odd"><td><code>0x0001</code></td><td><code>"Escape"</code></td></tr><tr class="even"><td><code>0x0002</code></td><td><code>"Digit1"</code></td></tr><tr class="odd"><td><code>0x0003</code></td><td><code>"Digit2"</code></td></tr><tr class="even"><td><code>0x0004</code></td><td><code>"Digit3"</code></td></tr><tr class="odd"><td><code>0x0005</code></td><td><code>"Digit4"</code></td></tr><tr class="even"><td><code>0x0006</code></td><td><code>"Digit5"</code></td></tr><tr class="odd"><td><code>0x0007</code></td><td><code>"Digit6"</code></td></tr><tr class="even"><td><code>0x0008</code></td><td><code>"Digit7"</code></td></tr><tr class="odd"><td><code>0x0009</code></td><td><code>"Digit8"</code></td></tr><tr class="even"><td><code>0x000A</code></td><td><code>"Digit9"</code></td></tr><tr class="odd"><td><code>0x000B</code></td><td><code>"Digit0"</code></td></tr><tr class="even"><td><code>0x000C</code></td><td><code>"Minus"</code></td></tr><tr class="odd"><td><code>0x000D</code></td><td><code>"Equal"</code></td></tr><tr class="even"><td><code>0x000E</code></td><td><code>"Backspace"</code></td></tr><tr class="odd"><td><code>0x000F</code></td><td><code>"Tab"</code></td></tr><tr class="even"><td><code>0x0010</code></td><td><code>"KeyQ"</code></td></tr><tr class="odd"><td><code>0x0011</code></td><td><code>"KeyW"</code></td></tr><tr class="even"><td><code>0x0012</code></td><td><code>"KeyE"</code></td></tr><tr class="odd"><td><code>0x0013</code></td><td><code>"KeyR"</code></td></tr><tr class="even"><td><code>0x0014</code></td><td><code>"KeyT"</code></td></tr><tr class="odd"><td><code>0x0015</code></td><td><code>"KeyY"</code></td></tr><tr class="even"><td><code>0x0016</code></td><td><code>"KeyU"</code></td></tr><tr class="odd"><td><code>0x0017</code></td><td><code>"KeyI"</code></td></tr><tr class="even"><td><code>0x0018</code></td><td><code>"KeyO"</code></td></tr><tr class="odd"><td><code>0x0019</code></td><td><code>"KeyP"</code></td></tr><tr class="even"><td><code>0x001A</code></td><td><code>"BracketLeft"</code></td></tr><tr class="odd"><td><code>0x001B</code></td><td><code>"BracketRight"</code></td></tr><tr class="even"><td><code>0x001C</code></td><td><code>"Enter"</code></td></tr><tr class="odd"><td><code>0x001D</code></td><td><code>"ControlLeft"</code></td></tr><tr class="even"><td><code>0x001E</code></td><td><code>"KeyA"</code></td></tr><tr class="odd"><td><code>0x001F</code></td><td><code>"KeyS"</code></td></tr><tr class="even"><td><code>0x0020</code></td><td><code>"KeyD"</code></td></tr><tr class="odd"><td><code>0x0021</code></td><td><code>"KeyF"</code></td></tr><tr class="even"><td><code>0x0022</code></td><td><code>"KeyG"</code></td></tr><tr class="odd"><td><code>0x0023</code></td><td><code>"KeyH"</code></td></tr><tr class="even"><td><code>0x0024</code></td><td><code>"KeyJ"</code></td></tr><tr class="odd"><td><code>0x0025</code></td><td><code>"KeyK"</code></td></tr><tr class="even"><td><code>0x0026</code></td><td><code>"KeyL"</code></td></tr><tr class="odd"><td><code>0x0027</code></td><td><code>"Semicolon"</code></td></tr><tr class="even"><td><code>0x0028</code></td><td><code>"Quote"</code></td></tr><tr class="odd"><td><code>0x0029</code></td><td><code>"Backquote"</code></td></tr><tr class="even"><td><code>0x002A</code></td><td><code>"ShiftLeft"</code></td></tr><tr class="odd"><td><code>0x002B</code></td><td><code>"Backslash"</code></td></tr><tr class="even"><td><code>0x002C</code></td><td><code>"KeyZ"</code></td></tr><tr class="odd"><td><code>0x002D</code></td><td><code>"KeyX"</code></td></tr><tr class="even"><td><code>0x002E</code></td><td><code>"KeyC"</code></td></tr><tr class="odd"><td><code>0x002F</code></td><td><code>"KeyV"</code></td></tr><tr class="even"><td><code>0x0030</code></td><td><code>"KeyB"</code></td></tr><tr class="odd"><td><code>0x0031</code></td><td><code>"KeyN"</code></td></tr><tr class="even"><td><code>0x0032</code></td><td><code>"KeyM"</code></td></tr><tr class="odd"><td><code>0x0033</code></td><td><code>"Comma"</code></td></tr><tr class="even"><td><code>0x0034</code></td><td><code>"Period"</code></td></tr><tr class="odd"><td><code>0x0035</code></td><td><code>"Slash"</code></td></tr><tr class="even"><td><code>0x0036</code></td><td><code>"ShiftRight"</code></td></tr><tr class="odd"><td><code>0x0037</code></td><td><code>"NumpadMultiply"</code></td></tr><tr class="even"><td><code>0x0038</code></td><td><code>"AltLeft"</code></td></tr><tr class="odd"><td><code>0x0039</code></td><td><code>"Space"</code></td></tr><tr class="even"><td><code>0x003A</code></td><td><code>"CapsLock"</code></td></tr><tr class="odd"><td><code>0x003B</code></td><td><code>"F1"</code></td></tr><tr class="even"><td><code>0x003C</code></td><td><code>"F2"</code></td></tr><tr class="odd"><td><code>0x003D</code></td><td><code>"F3"</code></td></tr><tr class="even"><td><code>0x003E</code></td><td><code>"F4"</code></td></tr><tr class="odd"><td><code>0x003F</code></td><td><code>"F5"</code></td></tr><tr class="even"><td><code>0x0040</code></td><td><code>"F6"</code></td></tr><tr class="odd"><td><code>0x0041</code></td><td><code>"F7"</code></td></tr><tr class="even"><td><code>0x0042</code></td><td><code>"F8"</code></td></tr><tr class="odd"><td><code>0x0043</code></td><td><code>"F9"</code></td></tr><tr class="even"><td><code>0x0044</code></td><td><code>"F10"</code></td></tr><tr class="odd"><td><code>0x0045</code></td><td><code>"NumLock"</code></td></tr><tr class="even"><td><code>0x0046</code></td><td><code>"ScrollLock"</code></td></tr><tr class="odd"><td><code>0x0047</code></td><td><code>"Numpad7"</code></td></tr><tr class="even"><td><code>0x0048</code></td><td><code>"Numpad8"</code></td></tr><tr class="odd"><td><code>0x0049</code></td><td><code>"Numpad9"</code></td></tr><tr class="even"><td><code>0x004A</code></td><td><code>"NumpadSubtract"</code></td></tr><tr class="odd"><td><code>0x004B</code></td><td><code>"Numpad4"</code></td></tr><tr class="even"><td><code>0x004C</code></td><td><code>"Numpad5"</code></td></tr><tr class="odd"><td><code>0x004D</code></td><td><code>"Numpad6"</code></td></tr><tr class="even"><td><code>0x004E</code></td><td><code>"NumpadAdd"</code></td></tr><tr class="odd"><td><code>0x004F</code></td><td><code>"Numpad1"</code></td></tr><tr class="even"><td><code>0x0050</code></td><td><code>"Numpad2"</code></td></tr><tr class="odd"><td><code>0x0051</code></td><td><code>"Numpad3"</code></td></tr><tr class="even"><td><code>0x0052</code></td><td><code>"Numpad0"</code></td></tr><tr class="odd"><td><code>0x0053</code></td><td><code>"NumpadDecimal"</code></td></tr><tr class="even"><td><code>0x0054</code>, <code>0x0055</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x0056</code></td><td><code>"IntlBackslash"</code></td></tr><tr class="even"><td><code>0x0057</code></td><td><code>"F11"</code></td></tr><tr class="odd"><td><code>0x0058</code></td><td><code>"F12"</code></td></tr><tr class="even"><td><code>0x0059</code></td><td><code>"IntlRo"</code></td></tr><tr class="odd"><td><code>0x005A</code>, <code>0x005B</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x005C</code></td><td><code>"Convert"</code></td></tr><tr class="odd"><td><code>0x005D</code></td><td><code>"KanaMode"</code></td></tr><tr class="even"><td><code>0x005E</code></td><td><code>"NonConvert"</code></td></tr><tr class="odd"><td><code>0x005F</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x0060</code></td><td><code>"NumpadEnter"</code></td></tr><tr class="odd"><td><code>0x0061</code></td><td><code>"ControlRight"</code></td></tr><tr class="even"><td><code>0x0062</code></td><td><code>"NumpadDivide"</code></td></tr><tr class="odd"><td><code>0x0063</code></td><td><code>"PrintScreen"</code></td></tr><tr class="even"><td><code>0x0064</code></td><td><code>"AltRight"</code></td></tr><tr class="odd"><td><code>0x0065</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x0066</code></td><td><code>"Home"</code></td></tr><tr class="odd"><td><code>0x0067</code></td><td><code>"ArrowUp"</code></td></tr><tr class="even"><td><code>0x0068</code></td><td><code>"PageUp"</code></td></tr><tr class="odd"><td><code>0x0069</code></td><td><code>"ArrowLeft"</code></td></tr><tr class="even"><td><code>0x006A</code></td><td><code>"ArrowRight"</code></td></tr><tr class="odd"><td><code>0x006B</code></td><td><code>"End"</code></td></tr><tr class="even"><td><code>0x006C</code></td><td><code>"ArrowDown"</code></td></tr><tr class="odd"><td><code>0x006D</code></td><td><code>"PageDown"</code></td></tr><tr class="even"><td><code>0x006E</code></td><td><code>"Insert"</code></td></tr><tr class="odd"><td><code>0x006F</code></td><td><code>"Delete"</code></td></tr><tr class="even"><td><code>0x0070</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x0071</code></td><td><p><code>"AudioVolumeMute"</code></p></td></tr><tr class="even"><td><code>0x0072</code></td><td><p><code>"AudioVolumeDown"</code></p></td></tr><tr class="odd"><td><code>0x0073</code></td><td><p><code>"AudioVolumeUp"</code></p></td></tr><tr class="even"><td><code>0x0074</code></td><td><code>"Power"</code></td></tr><tr class="odd"><td><code>0x0075</code></td><td><code>"NumpadEqual"</code></td></tr><tr class="even"><td><code>0x0076</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x0077</code></td><td><code>"Pause"</code></td></tr><tr class="even"><td><code>0x0078</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x0079</code></td><td><code>"NumpadComma"</code></td></tr><tr class="even"><td><code>0x007A</code></td><td><code>"Lang1"</code></td></tr><tr class="odd"><td><code>0x007B</code></td><td><code>"Lang2"</code></td></tr><tr class="even"><td><code>0x007C</code></td><td><code>"IntlYen"</code></td></tr><tr class="odd"><td><code>0x007D</code></td><td><p><code>"MetaLeft"</code></p></td></tr><tr class="even"><td><code>0x007E</code></td><td><p><code>"MetaRight"</code></p></td></tr><tr class="odd"><td><code>0x007F</code></td><td><code>"ContextMenu"</code></td></tr><tr class="even"><td><code>0x0080</code></td><td><code>"BrowserStop"</code></td></tr><tr class="odd"><td><code>0x0081</code></td><td>"Again"</td></tr><tr class="even"><td><code>0x0082</code></td><td><code>"Props"</code></td></tr><tr class="odd"><td><code>0x0083</code></td><td><code>"Undo"</code></td></tr><tr class="even"><td><code>0x0084</code></td><td><code>"Select"</code></td></tr><tr class="odd"><td><code>0x0085</code></td><td><code>"Copy"</code></td></tr><tr class="even"><td><code>0x0086</code></td><td><code>"Open"</code></td></tr><tr class="odd"><td><code>0x0087</code></td><td><code>"Paste"</code></td></tr><tr class="even"><td><code>0x0088</code></td><td><code>"Find"</code></td></tr><tr class="odd"><td><code>0x0089</code></td><td><code>"Cut"</code></td></tr><tr class="even"><td><code>0x008A</code></td><td><code>"Help"</code></td></tr><tr class="odd"><td><code>0x008B</code> ～ <code>0x008D</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x008E</code></td><td><code>"Sleep"</code></td></tr><tr class="odd"><td><code>0x008F</code></td><td><code>"WakeUp"</code></td></tr><tr class="even"><td><code>0x0090</code></td><td><code>"LaunchApp1"</code></td></tr><tr class="odd"><td><code>0x0091</code> ～ <code>0x009B</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x009C</code></td><td><code>"BrowserFavorites"</code></td></tr><tr class="odd"><td><code>0x009D</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x009E</code></td><td><code>"BrowserBack"</code></td></tr><tr class="odd"><td><code>0x009F</code></td><td><code>"BrowserForward"</code></td></tr><tr class="even"><td><code>0x00A0</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x00A1</code></td><td><code>"Eject"</code></td></tr><tr class="even"><td><code>0x00A2</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x00A3</code></td><td><code>"MediaTrackNext"</code></td></tr><tr class="even"><td><code>0x00A4</code></td><td><code>"MediaPlayPause"</code></td></tr><tr class="odd"><td><code>0x00A5</code></td><td><code>"MediaTrackPrevious"</code></td></tr><tr class="even"><td><code>0x00A6</code></td><td><code>"MediaStop"</code></td></tr><tr class="odd"><td><code>0x00A7</code> ～ <code>0x00AC</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="even"><td><code>0x00AD</code></td><td><code>"BrowserRefresh"</code></td></tr><tr class="odd"><td><code>0x00AE</code> ～ <code>0x00B6</code></td><td>"Unidentified"</td></tr><tr class="even"><td><code>0x00B7</code></td><td><code>"F13"</code></td></tr><tr class="odd"><td><code>0x00B8</code></td><td><code>"F14"</code></td></tr><tr class="even"><td><code>0x00B9</code></td><td><code>"F15"</code></td></tr><tr class="odd"><td><code>0x00BA</code></td><td><code>"F16"</code></td></tr><tr class="even"><td><code>0x00BB</code></td><td><code>"F17"</code></td></tr><tr class="odd"><td><code>0x00BC</code></td><td><code>"F18"</code></td></tr><tr class="even"><td><code>0x00BD</code></td><td><code>"F19"</code></td></tr><tr class="odd"><td><code>0x00BE</code></td><td><code>"F20"</code></td></tr><tr class="even"><td><code>0x00BF</code></td><td><code>"F21"</code></td></tr><tr class="odd"><td><code>0x00C0</code></td><td><code>"F22"</code></td></tr><tr class="even"><td><code>0x00C1</code></td><td><code>"F23"</code></td></tr><tr class="odd"><td><code>0x00C2</code></td><td><code>"F24"</code></td></tr><tr class="even"><td><code>0x00C3</code> ～ <code>0x00D8</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x00D9</code></td><td><code>"BrowserSearch"</code></td></tr><tr class="even"><td><code>0x00DA</code> ～ <code>0x01CF</code></td><td><p><code>"Unidentified"</code></p></td></tr><tr class="odd"><td><code>0x01D0</code></td><td><code>"Fn"</code></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code/code_values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code/code_values</a>
