# Key Values

The tables below list the standard key values in various categories of key, with an explanation of what the key is typically used for. Corresponding virtual keycodes for common platforms are included where available.

Learn how to use these key values in JavaScript using [KeyboardEvent.key](../key)

[Special Values](#special_values) | [Modifier Keys](#modifier_keys) | [Whitespace Keys](#whitespace_keys) | [Navigation Keys](#navigation_keys) | [Editing Keys](#editing_keys) | [UI Keys](#ui_keys) | [Device Keys](#device_keys) | [IME and Composition Keys](#ime_and_composition_keys) | [Function Keys](#function_keys) | [Phone Keys](#phone_keys) | [Multimedia Keys](#multimedia_keys) | [Audio Control Keys](#audio_control_keys) | [TV Control Keys](#tv_control_keys) | [Media Controller Keys](#media_controller_keys) | [Speech Recognition Keys](#speech_recognition_keys) | [Document Keys](#document_keys) | [Application Selector Keys](#application_selector_keys) | [Browser Control Keys](#browser_control_keys) | [Numeric Keypad Keys](#numeric_keypad_keys)

## Special values

Values of `key` which have special meanings other than identifying a specific key or character.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Unidentified"`

The user agent wasn't able to map the event's virtual keycode to a specific key value.

This can happen due to hardware or software constraints, or because of constraints around the platform on which the user agent is running.

_varies_

_varies_

_varies_

_varies_

## Modifier keys

_Modifiers_ are special keys which are used to generate special characters or cause special actions when used in combination with other keys. Examples include the Shift and Control keys, and lock keys such as Caps Lock and NumLock.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Alt"` \[5\]

The Alt (Alternative) key.

`VK_MENU` (0x12)  
`VK_LMENU` (0xA4)  
`VK_RMENU` (0xA5)

`kVK_Option` (0x3A)  
`kVK_RightOption` (0x3D)

`GDK_KEY_Alt_L` (0xFFE9)  
`GDK_KEY_Alt_R` (0xFFEA)  
`Qt::Key_Alt` (0x01000023)

`KEYCODE_ALT_LEFT` (57)  
`KEYCODE_ALT_RIGHT` (58)

`"AltGraph"` \[5\]

The AltGr or AltGraph (Alternate Graphics) key. Enables the ISO Level 3 shift modifier (where Shift is the level 2 modifier).

`GDK_KEY_Mode_switch` (0xFF7E)  
`GDK_KEY_ISO_Level3_Shift` (0xFE03)  
`GDK_KEY_ISO_Level3_Latch` (0xFE04)  
`GDK_KEY_ISO_Level3_Lock` (0xFE05)  
`GDK_KEY_ISO_Level5_Shift` (0xFE11)  
`GDK_KEY_ISO_Level5_Latch` (0xFE12)  
`GDK_KEY_ISO_Level5_Lock` (0xFE13)  
`Qt::Key_AltGr` (0x01001103  
`Qt::Key_Mode_switch` (0x0100117E)

`"CapsLock"`

The Caps Lock key. Toggles the capital character lock on and off for subsequent input.

`VK_CAPITAL` (0x14)

`kVK_CapsLock` (0x39)

`GDK_KEY_Caps_Lock` (0xFFE5)  
`Qt::Key_CapsLock` (0x01000024)

`KEYCODE_CAPS_LOCK` (115)

`"Control"`

The Control, Ctrl, or Ctl key. Allows typing control characters.

`VK_CONTROL` (0x11)  
`VK_LCONTROL` (0xA2)  
`VK_RCONTROL` (0xA3)

`kVK_Control` (0x3B)  
`kVK_RightControl` (0x3E)

`GDK_KEY_Control_L` (0xFFE3)  
`GDK_KEY_Control_R` (0xFFE4)  
`Qt::Key_Control` (0x01000021)

`KEYCODE_CTRL_LEFT` (113)  
`KEYCODE_CTRL_RIGHT` (114)

`"Fn"`

The Fn (Function modifier) key. Used to allow generating function key (F1–F15, for instance) characters on keyboards without a dedicated function key area. Often handled in hardware so that events aren't generated for this key.

`kVK_Function` (0x3F)

`KEYCODE_FUNCTION` (119)

`"FnLock"`

The FnLock or F-Lock (Function Lock) key.Toggles the function key mode described by `"Fn"` on and off. Often handled in hardware so that events aren't generated for this key.

`"Hyper"` \[4\]

The Hyper key.

`GDK_KEY_Hyper_L` (0xFFED)  
`GDK_KEY_Hyper_R` (0xFFEE)  
`Qt::Key_Hyper_L` (0x01000056)  
`Qt::Key_Hyper_R` (0x01000057)

`"Meta"` \[1\]

The Meta key. Allows issuing special command inputs. This is the Windows logo key, or the Command or ⌘ key on Mac keyboards.

`VK_LWIN` (0x5B)  
`VK_RWIN` (0x5C)

`kVK_Command` (0x37)  
`kVK_RightCommand` (0x36)

`GDK_KEY_Meta_L` (0xFFE7)  
`GDK_KEY_Meta_R` (0xFFE8)  
`Qt::Key_Meta` (0x01000022)

`KEYCODE_META_LEFT` (117)  
`KEYCODE_META_RIGHT` (118)

`"NumLock"`

The NumLock (Number Lock) key. Toggles the numeric keypad between number entry some other mode (often directional arrows).

`VK_NUMLOCK` (0x90)

`GDK_KEY_Num_Lock` (0xFF7F)  
`Qt::Key_NumLock` (0x01000025)

`KEYCODE_NUM_LOCK` (143)

`"ScrollLock"` \[2\]

The Scroll Lock key. Toggles between scrolling and cursor movement modes.

`VK_SCROLL` (0x91)

`GDK_KEY_Scroll_Lock` (0xFF14)  
`Qt::Key_ScrollLock` (0x01000026)

`KEYCODE_SCROLL_LOCK` (116)

`"Shift"`

The Shift key. Modifies keystrokes to allow typing upper (or other) case letters, and to support typing punctuation and other special characters.

`VK_SHIFT` (0x10)  
`VK_LSHIFT` (0xA0)  
`VK_RSHIFT` (0xA1)

`kVK_Shift` (0x38)  
`kVK_RightShift` (0x3C)

`GDK_KEY_Shift_L` (0xFFE1)  
`GDK_KEY_Shift_R` (0xFFE2)  
`Qt::Key_Shift` (0x01000020)

`KEYCODE_SHIFT_LEFT` (59)  
`KEYCODE_SHIFT_RIGHT` (60)

`"Super"` \[4\]

The Super key.

`GDK_KEY_Super_L` (0xFFEB)  
`GDK_KEY_Super_R` (0xFFEC)  
`Qt::Key_Super_L` (0x01000053)  
`Qt::Key_Super_R` (0x01000054)

`"Symbol"`

The Symbol modifier key (found on certain virtual keyboards).

`KEYCODE_SYM` (63) \[3\]

`"SymbolLock"`

The Symbol Lock key.

\[1\] In Internet Explorer (tested on release 9 and 11), as well as in all versions of Firefox, the Windows key is reported as `"OS"` instead of as `"Meta"`. This will be changed in Firefox per [bug 1232918](https://bugzilla.mozilla.org/show_bug.cgi?id=1232918). Until that's fixed, these keys are returned as `"OS"` by Firefox: `VK_LWIN` (0x5B) and `VK_RWIN` (0x5C) on Windows, and `GDK_KEY_Super_L` (0xFFEB), `GDK_KEY_Super_R` (0xFFEC), `GDK_KEY_Hyper_L` (0xFFED), and `GDK_KEY_Hyper_R` (0xFFEE) on Linux.

\[2\] Internet Explorer (tested on release 9 and 11) reports `"Scroll"` instead of `"ScrollLock"` for the Scroll Lock key.

\[3\] Firefox did not add support for the Symbol key until Firefox 37.

\[4\] Firefox generates the key value `"OS`" for the Super and Hyper keys, instead of `"Super"` and `"Hyper"`.

\[5\] Chrome 67 and Firefox 63 now correctly interpret the right Alt key for keyboard layouts which map that key to AltGr. See Firefox bug [bug 900750](https://bugzilla.mozilla.org/show_bug.cgi?id=900750) and [Chrome bug 25503](https://bugs.chromium.org/p/chromium/issues/detail?id=25503) for further details.

## Whitespace keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Enter"`

The Enter or ↵ key (sometimes labeled Return).

`VK_RETURN` (0x0D)

`kVK_Return` (0x24)  
`kVK_ANSI_KeypadEnter` (0x4C)  
`kVK_Powerbook_KeypadEnter` (0x34)

`GDK_KEY_Return` (0xFF0D)  
`GDK_KEY_KP_Enter` (0xFF8D)  
`GDK_KEY_ISO_Enter` (0xFE34)  
`GDK_KEY_3270_Enter` (0xFD1E)  
`Qt::Key_Return` (0x01000004)  
`Qt::Key_Enter` (0x01000005)

`KEYCODE_ENTER` (66)  
`KEYCODE_NUMPAD_ENTER` (160)  
`KEYCODE_DPAD_CENTER` (23)

`"Tab"`

The Horizontal Tab key, Tab.

`VK_TAB` (0x09)

`kVK_Tab` (0x30)

`GDK_KEY_Tab` (0xFF09)  
`GDK_KEY_KP_Tab` (0xFF89)  
`GDK_KEY_ISO_Left_Tab` (0xFE20)  
`Qt::Key_Tab` (0x01000001)

`KEYCODE_TAB` (61)

`" "` \[1\]

The space key, Space Bar.

`VK_SPACE` (0x20)

`kVK_Space` (0x31)

`GDK_KEY_space` (0x20)  
`GDK_KEY_KP_Space` (0xFF80)  
`Qt::Key_Space` (0x20)

`KEYCODE_SPACE` (62)

\[1\] Older browsers may return `"Spacebar"` instead of `" "` for the Space Bar key. Firefox did so until version 37, as did Internet Explorer 9, 10, and 11.

## Navigation keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"ArrowDown"` \[1\]

The down arrow key.

`VK_DOWN` (0x28)

`kVK_DownArrow` (0x7D)

`GDK_KEY_Down` (0xFF54)  
`GDK_KEY_KP_Down` (0xFF99)  
`Qt::Key_Down` (0x01000015)

`KEYCODE_DPAD_DOWN` (20)

`"ArrowLeft"` \[1\]

The left arrow key.

`VK_LEFT` (0x25)

`kVK_LeftArrow` (0x7B)

`GDK_KEY_Left` (0xFF51)  
`GDK_KEY_KP_Left` (0xFF96)  
`Qt::Key_Left` (0x01000012)

`KEYCODE_DPAD_LEFT` (21)

`"ArrowRight"` \[1\]

The right arrow key.

`VK_RIGHT` (0x27)

`kVK_RightArrow` (0x7C)

`GDK_KEY_Right` (0xFF53)  
`GDK_KEY_KP_Right` (0xFF98)  
`Qt::Key_Right` (0x01000014)

`KEYCODE_DPAD_RIGHT` (22)

`"ArrowUp"` \[1\]

The up arrow key.

` VK_UP`` (0x26) `

`kVK_UpArrow` (0x7E)

`GDK_KEY_Up` (0xFF52)  
`GDK_KEY_KP_Up` (0xFF97)  
`Qt::Key_Up` (0x01000013)

`KEYCODE_DPAD_UP` (19)

`"End"`

The End key. Moves to the end of content.

`VK_END` (0x23)

`kVK_End` (0x77)

`GDK_KEY_End` (0xFF57)  
`GDK_KEY_KP_End` (0xFF9C)  
`Qt::Key_End` (0x01000011)

`KEYCODE_MOVE_END` (123)

`"Home"`

The Home key. Moves to the start of content.

`VK_HOME` (0x24)

`kVK_Home` (0x73)

`GDK_KEY_Home` (0xFF50)  
`GDK_KEY_KP_Home` (0xFF95)  
`Qt::Key_Home` (0x01000010)

`KEYCODE_MOVE_HOME` (122)

`"PageDown"`

The Page Down (or PgDn) key. Scrolls down or displays the next page of content.

`VK_NEXT` (0x22)

` kVK_PageDown`` (0x79) `

`GDK_KEY_Page_Down` (0xFF56)  
`GDK_KEY_KP_Page_Down` (0xFF9B)  
`Qt::Key_PageDown` (0x01000017)

`KEYCODE_PAGE_DOWN` (93)

`"PageUp"`

The Page Up (or PgUp) key. Scrolls up or displays the previous page of content.

`VK_PRIOR` (0x21)

`kVK_PageUp` (0x74)

`GDK_KEY_Page_Up` (0xFF55)  
`GDK_KEY_KP_Page_Up` (0xFF9A)  
`Qt::Key_PageUp` (0x01000016)

`KEYCODE_PAGE_UP` (92)

\[1\] Internet Explorer, Edge (16 and earlier), and Firefox (36 and earlier) use `"Left"`, `"Right"`, `"Up"`, and `"Down"` instead of `"ArrowLeft"`, `"ArrowRight"`, `"ArrowUp"`, and `"ArrowDown"`.

## Editing keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Backspace"`

The Backspace key. This key is labeled Delete on Mac keyboards.

`VK_BACK` (0x08)

`kVK_Delete` (0x33)

`GDK_KEY_BackSpace` (0xFF08)  
`Qt::Key_Backspace` (0x01000003)

`KEYCODE_DEL` (67)

`"Clear"`

The Clear key. Removes the currently selected input.

`VK_CLEAR` (0x0C)  
`VK_OEM_CLEAR` (0xFE)

`kVK_ANSI_KeypadClear` (0x47)

`GDK_KEY_Clear` (0xFF0B)  
`Qt::Key_Clear` (0x0100000B)

`KEYCODE_CLEAR` (28)

`"Copy"`

The Copy key (on certain extended keyboards).

`APPCOMMAND_COPY`

`GDK_KEY_Copy` (0x1008FF57)  
`Qt::Key_Copy` (0x010000CF)

`"CrSel"` \[3\]

The Cursor Select key, CrSel.

`VK_CRSEL` (0xF7)

`GDK_KEY_3270_CursorSelect` (0xFD1C)

`"Cut"`

The Cut key (on certain extended keyboards).

`APPCOMMAND_CUT`

`GDK_KEY_Cut` (0x1008FF58)  
`Qt::Key_Cut` (0x010000D0)

`"Delete"` \[2\]

The Delete key, Del.

`VK_DELETE` (0x2E)

`kVK_ForwardDelete` (0x75) \[1\]

`GDK_KEY_Delete` (0xFFFF)  
`GDK_KEY_KP_Delete` (0xFF9F)  
`Qt::Key_Delete` (0x01000007)

`KEYCODE_FORWARD_DEL` (112)

`"EraseEof"`

Erase to End of Field. Deletes all characters from the current cursor position to the end of the current field.

`VK_EREOF` (0xF9)

`GDK_KEY_3270_ExSelect` (0xFD1B)

`"ExSel"` \[4\]

The ExSel (Extend Selection) key.

`VK_EXSEL` (0xF8)

`GDK_KEY_3270_ExSelect` (0xFD1B)

`"Insert"`

The Insert key, Ins. Toggles between inserting and overwriting text.

`VK_INSERT` (0x2D)

`GDK_KEY_Insert` (0xFF63)  
`GDK_KEY_KP_Insert` (0xFF9E)  
`Qt::Key_Insert` (0x01000006)

`KEYCODE_INSERT` (124)

`"Paste"`

Paste from the clipboard.

`APPCOMMAND_PASTE`

`GDK_KEY_Paste` (0x1008FF6D)  
`Qt::Key_Paste` (0x010000E2)

`"Redo"`

Redo the last action.

`APPCOMMAND_REDO`

`GDK_KEY_Redo` (0xFF66)

`"Undo"`

Undo the last action.

`APPCOMMAND_UNDO`

`GDK_KEY_Undo` (0xFF65)

\[1\] On keyboards without a dedicated Del key, the Mac generates the `"Delete"` value when Fn is pressed in tandem with Delete (which is Backspace on other platforms).

\[2\] Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier use `"Del"` instead of `"Delete"` for the Del key.

\[3\] Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier generate the value `"Crsel"` instead of `"CrSel"` when the CrSel key is pressed.

\[4\] Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier generate the value `"Exsel"` instead of `"ExSel"` when the ExSel key is pressed.

## UI keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Accept"`

The Accept, Commit, or OK key or button. Accepts the currently selected option or input method sequence conversion.

`VK_ACCEPT` (0x1E)

`KEYCODE_DPAD_CENTER` (23)

`"Again"`

The Again key. Redoes or repeats a previous action.

`GDK_KEY_Redo` (0xFF66)

`"Attn"` \[4\]

The Attn (Attention) key.

`VK_OEM_ATTN` (0xF0)

`GDK_KEY_3270_Attn` (0xFD0E)

`"Cancel"` \[1\]

The Cancel key.

`GDK_KEY_Cancel` (0xFF69)

`"ContextMenu"` \[3\]

Shows the context menu. Typically found between the Windows (or OS) key and the Control key on the right side of the keyboard.

`VK_APPS` (0x5D)

`kVK_PC_ContextMenu` (0x6E)

`GDK_KEY_Menu` (0xFF67)  
`Qt::Key_Menu` (0x01000055)

`KEYCODE_MENU` (82)

`"Escape"` \[2\]

The Esc (Escape) key. Typically used as an exit, cancel, or "escape this operation" button. Historically, the Escape character was used to signal the start of a special control sequence of characters called an "escape sequence."

`VK_ESCAPE` (0x1B)

`kVK_Escape` (0x35)

`GDK_KEY_Escape` (0xFF1B)  
`Qt::Key_Escape` (0x01000000)

`KEYCODE_ESCAPE` (111)

`"Execute"`

The Execute key.

`VK_EXECUTE` (0x2B)

`Qt::Key_Execute` (0x01020003)

`"Find"`

The Find key. Opens an interface (typically a dialog box) for performing a find/search operation.

`APPCOMMAND_FIND`

`GDK_KEY_Find` (0xFF68)

`"Finish"` \[5\]

The Finish key.

`VK_OEM_FINISH` (0xF1)

`"Help"`

The Help key. Opens or toggles the display of help information.

`VK_HELP` (0x2F)  
`APPCOMMAND_HELP`

`kVK_Help` (0x72)

`GDK_KEY_Help` (0xFF6A)  
`Qt::Key_Help` (0x01000058)

`KEYCODE_HELP` (259)

`"Pause"`

The Pause key. Pauses the current application or state, if applicable.

**Note:** This shouldn't be confused with the `"MediaPause"` key value, which is used for media controllers, rather than to control applications and processes.

`VK_PAUSE` (0x13)

`GDK_KEY_Pause` (0xFF13)  
`GDK_KEY_Break` (0xFF6B)  
`Qt::Key_Pause` (0x01000008)

`KEYCODE_BREAK` (121)

`"Play"`

The Play key. Resumes a previously paused application, if applicable.

**Note:** This shouldn't be confused with the `"MediaPlay"` key value, which is used for media controllers, rather than to control applications and processes.

`VK_PLAY` (0xFA)

`GDK_KEY_3270_Play` (0xFD16)  
`Qt::Key_Play` (0x01020005)

`"Props"`

The Props (Properties) key.

`"Select"`

The Select key.

`VK_SELECT` (0x29)

`GDK_KEY_Select` (0xFF60)

`KEYCODE_BUTTON_SELECT` (109)

`"ZoomIn"` \[6\]

The ZoomIn key.

`GDK_KEY_ZoomIn` (0x1008FF8B)  
`Qt::Key_ZoomIn` (0x010000F6)

`KEYCODE_ZOOM_IN` (168)

`"ZoomOut"` \[6\]

The ZoomOut key.

`GDK_KEY_ZoomOut` (0x1008FF8C)  
`Qt::Key_ZoomOut` (0x010000F7)

`KEYCODE_ZOOM_OUT` (169)

\[1\] In Google Chrome 52, the Cancel key incorrectly returns the key code `"Pause"`. This is fixed in Chrome 53. (See [Chrome bug 612749](https://bugs.chromium.org/p/chromium/issues/detail?id=612749) for details.)

\[2\] In Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier, the Esc key returns `"Esc"` instead of `"Escape"`.

\[3\] Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier report `"Apps"` instead of `"ContextMenu"` for the context menu key.

\[4\] The Attn key generates the key code `"Unidentified"` on Internet Explorer (tested on release 9 and 11). Firefox and Google Chrome report the same, unless the Japanese keyboard layout is in effect, in which case it generates `"KanaMode"` instead.

\[5\] The Finish key generates the key code `"Unidentified"` on Internet Explorer (tested on release 9 and 11). Firefox reports the same, unless the Japanese keyboard layout is in effect, in which case it generates `"Katakana"` instead.

\[6\] Firefox didn't support the `"ZoomIn"` and `"ZoomOut"` keys until Firefox 37.

## Device keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"BrightnessDown"`

The Brightness Down key. Typically used to reduce the brightness of the display.

`GDK_KEY_MonBrightnessDown` (0x1008FF03)  
`Qt::Key_MonBrightnessDown` (0x010000B3)

`KEYCODE_BRIGHTNESS_DOWN` (220)

`"BrightnessUp"`

The Brightness Up key. Typically increases the brightness of the display.

`GDK_KEY_MonBrightnessUp` (0x1008FF02)  
`Qt::Key_MonBrightnessUp` (0x010000B2)

`KEYCODE_BRIGHTNESS_UP` (221)

`"Eject"`

The Eject key. Ejects removable media (or toggles an optical storage device tray open and closed).

`GDK_KEY_Eject` (0x1008FF2C)  
`Qt::Key_Eject` (0x010000B9)

`KEYCODE_MEDIA_EJECT` (129)

`"LogOff"` \[2\]

The LogOff key.

`GDK_KEY_LogOff` (0x1008FF61)  
`Qt::Key_LogOff` (0x010000D9)

`"Power"`

The Power button or key, to toggle power on and off.

**Note:** Not all systems pass this key through to the user agent.

`KEYCODE_POWER` (26)

`"PowerOff"`

The PowerOff or PowerDown key. Shuts off the system.

`GDK_KEY_PowerDown` (0x1008FF21)  
`GDK_KEY_PowerOff` (0x1008FF2A)  
`Qt::Key_PowerDown` (0x0100010B)  
`Qt::Key_PowerOff` (0x010000B7)

`"PrintScreen"`

The PrintScreen or PrtScr key. Sometimes SnapShot. Captures the screen and prints it or saves it to disk.

`VK_SNAPSHOT` (0x2C)

`GDK_KEY_3270_PrintScreen` (0xFD1D)  
`GDK_KEY_Print` (0xFF61)  
`GDK_KEY_Sys_Req` (0xFF15)  
`Qt::Key_Print` (0x01000009)  
`Qt::Key_SysReq` (0x0100000A)

`KEYCODE_SYSRQ` (120)

`"Hibernate"` \[2\]

The Hibernate key. This saves the state of the computer to disk and then shuts down; the computer can be returned to its previous state by restoring the saved state information.

`GDK_KEY_Hibernate` (0x1008FFA8)  
`Qt::Key_Hibernate` (0x01000108)

`"Standby"` \[1\]

The Standby key. (Also known as Suspend or Sleep.) This turns off the display and puts the computer in a low power consumption mode, without completely powering off.

`VK_SLEEP` (0x5F)

`GDK_KEY_Standby` (0x1008FF10)  
`GDK_KEY_Suspend` (0x1008FFA7)  
`GDK_KEY_Sleep` (0x1008FF2F)  
`Qt::Key_Standby` (0x01000093)  
`Qt::Key_Suspend` (0x0100010C)  
`Qt::Key_Sleep` (0x01020004)

`KEYCODE_SLEEP` (223)

`"WakeUp"` \[2\]

The WakeUp key. Used to wake the computer from the hibernation or standby modes.

`GDK_KEY_WakeUp` (0x1008FF2B)  
`Qt::Key_WakeUp` (0x010000B8)

`KEYCODE_WAKEUP` (224)

\[1\] The Standby key is not supported by Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier, so it is reported as `"Unidentified"`.

\[2\] Prior to Firefox 37, this key generated the value `"Unidentified"`.

## IME and composition keys

Keys used when using an Input Method Editor (IME) to input text which can't readily be entered by simple keypresses, such as text in languages such as those which have more graphemes than there are character entry keys on the keyboard. Common examples include Chinese, Japanese, Korean, and Hindi.

Some keys are common across multiple languages, while others exist only on keyboards targeting specific languages. In addition, not all keyboards have all of these keys.

#### Common IME keys

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"AllCandidates"`

The All Candidates key, which starts multi-candidate mode, in which multiple candidates are displayed for the ongoing input.

`GDK_KEY_MultipleCandidate` (0xFF3D  
`Qt::Key_MultipleCandidate` (0x0100113D)

`"Alphanumeric"`

The Alphanumeric key.

`VK_OEM_ATTN` (0xF0)

`GDK_KEY_Eisu_Shift` (0xFF2F)  
`GDK_KEY_Eisu_toggle` (0xFF30)  
`Qt::Key_Eisu_Shift` (0x0100112f)  
`Qt::Key_Eisu_toggle` (0x01001130)

`"CodeInput"`

The Code Input key, which enables code input mode, which lets the user enter characters by typing their code points (their Unicode character numbers, typically).

`GDK_KEY_Codeinput` (0xFF37)  
`Qt::Key_Codeinput` (0x01001137)

`"Compose"`

The Compose key.

`GDK_KEY_Multi_key` (0xFF20) \[1\]  
`Qt::Key_Multi_key` (0x01001120)

`"Convert"` \[4\]

The Convert key, which instructs the IME to convert the current input method sequence into the resulting character.

`VK_CONVERT` (0x1C)

`GDK_KEY_Henkan` (0xFF23)  
`Qt::Key_Henkan` (0x01001123)

`KEYCODE_HENKAN` (214)

`"Dead"`

A dead "combining" key; that is, a key which is used in tandem with other keys to generate accented and other modified characters. If pressed by itself, it doesn't generate a character.

If you wish to identify which specific dead key was pressed (in cases where more than one exists), you can do so by examining the [`KeyboardEvent`](../../keyboardevent)'s associated `compositionupdate` event's [`data`](../../compositionevent/data) property.

See [Dead keycodes for Linux](#dead_keycodes_for_linux) below

`"FinalMode"`

The Final (Final Mode) key is used on some Asian keyboards to enter final mode when using IMEs.

`VK_FINAL` (0x18)

`"GroupFirst"`

Switches to the first character group on an [ISO/IEC 9995 keyboard](https://en.wikipedia.org/wiki/ISO/IEC_9995). Each key may have multiple groups of characters, each in its own column. Pressing this key instructs the device to interpret keypresses as coming from the first column on subsequent keystrokes.

`GDK_KEY_ISO_First_Group` (0xFE0C)

`"GroupLast"`

Switches to the last character group on an [ISO/IEC 9995 keyboard](https://en.wikipedia.org/wiki/ISO/IEC_9995).

`GDK_KEY_ISO_Last_Group` (0xFE0E)

`"GroupNext"` \[4\]

Switches to the next character group on an [ISO/IEC 9995 keyboard](https://en.wikipedia.org/wiki/ISO/IEC_9995).

`GDK_KEY_ISO_Next_Group` (0xFE08)

`KEYCODE_LANGUAGE_SWITCH` (204)

`"GroupPrevious"`

Switches to the previous character group on an [ISO/IEC 9995 keyboard](https://en.wikipedia.org/wiki/ISO/IEC_9995).

`GDK_KEY_ISO_Prev_Group` (0xFE0A)

`"ModeChange"` \[5\]

The Mode Change key. Toggles or cycles among input modes of IMEs.

`VK_MODECHANGE` (0x1F)

`GDK_KEY_Mode_switch` (0xFF7E)  
`GDK_KEY_script_switch` (0xFF7E)  
`Qt::Key_Mode_switch` (0x0100117E)

`KEYCODE_SWITCH_CHARSET` (95)

`"NextCandidate"`

The Next Candidate function key. Selects the next possible match for the ongoing input.

`"NonConvert"` \[2\]

The NonConvert ("Don't convert") key. This accepts the current input method sequence without running conversion when using an IME.

`VK_NONCONVERT` (0x1D)

`GDK_KEY_Muhenkan` (0xFF22)  
`Qt::Key_Muhenkan` (0x01001122)

`KEYCODE_MUHENKAN` (213)

`"PreviousCandidate"`

The Previous Candidate key. Selects the previous possible match for the ongoing input.

`GDK_KEY_PreviousCandidate` (0xFF3E)  
`Qt::Key_PreviousCandidate` (0x0100113E)

`"Process"` \[3\]

The Process key. Instructs the IME to process the conversion.

`VK_PROCESSKEY` (0xE5)

`"SingleCandidate"` \[4\]

The Single Candidate key. Enables single candidate mode (as opposed to multi-candidate mode); in this mode, only one candidate is displayed at a time.

`GDK_KEY_SingleCandidate` (0xFF3C)  
`Qt::Key_SingleCandidate` (0x0100113C)

\[1\] On the _X Window System_, the Compose key is called the Multi key.

\[2\] The NonConvert key is reported as `"Nonconvert"` instead of the correct `"NonConvert"` by Internet Explorer (tested on release 9 and 11) and Firefox versions 36 and earlier.

\[3\] The Process key currently returns `"Unidentified"` in Firefox and Internet Explorer. Google Chrome returns the value of the key as if IME were not in use.

\[4\] Prior to Firefox 37, these keys were `"Unidentified"`.

\[5\] Firefox generates the key value `"AltGraph"` instead of `"ModeChange"`.

### Korean keyboards only

These keys are only available on Korean keyboards. There are other keys defined by various platforms for Korean keyboards, but these are the most common and are the ones identified by the UI Events specification.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"HangulMode"`

The Hangul (Korean character set) mode key, which toggles between Hangul and English entry modes.

`VK_HANGUL` (0x15) \[1\]

`GDK_KEY_Hangul` (0xFF31)  
`Qt::Key_Hangul` (0x01001131)

`"HanjaMode"`

Selects the Hanja mode, for converting Hangul characters to the more specific Hanja characters.

`VK_HANJA` (0x19) \[1\]

`GDK_KEY_Hangul_Hanja` (0xFF34)  
`Qt::Key_Hangul_Hanja` (0x01001134)

`"JunjaMode"`

Selects the Junja mode, in which Korean is represented using single-byte Latin characters.

`VK_JUNJA` (0x17)

`GDK_KEY_Hangul_Jeonja` (0xFF38)  
`Qt::Key_Hangul_Jeonja` (0x01001138)

\[1\] `VK_HANGUL` and `VK_KANA` share the same numeric key value on Windows, as do `VK_HANJA` and `VK_KANJI`.

### Japanese keyboards only

These keys are only available on Japanese keyboards.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Eisu"` \[1\]

The Eisu key. This key's purpose is defined by the IME, but may be used to close the IME.

`kVK_JIS_Eisu` (0x66)

`GDK_KEY_Eisu_toggle` (0xFF2F)  
`Qt::Key_Eisu_toggle` (0x01001130)

`KEYCODE_EISU` (212)

`"Hankaku"` \[3\]

The Hankaku (half-width characters) key.

`VK_OEM_AUTO` (0xF3)

`GDK_KEY_Hankaku` (0xFF29)  
`Qt::Key_Hankaku` (0x01001129)

`"Hiragana"`

The Hiragana key; selects Kana characters mode.

`VK_OEM_COPY` (0xF2)

`GDK_KEY_Hiragana` (0xFF25)  
`Qt::Key_Hiragana` (0x01001125)

`"HiraganaKatakana"` \[6\]

Toggles between the Hiragana and Katakana writing systems.

`GDK_KEY_Hiragana_Katakana` (0xFF27)  
`Qt::Key_Hiragana_Katakana` (0x01001127)

`KEYCODE_KATAKANA_HIRAGANA` (215)

`"KanaMode"`

The Kana Mode (Kana Lock) key.

`VK_KANA` (0x15) \[2\]  
`VK_ATTN` (0xF6)

`GDK_KEY_Kana_Lock` (0xFF2D)  
`GDK_KEY_Kana_Shift` (0xFF2E)  
`Qt::Key_Kana_Lock` (0x0100112D)  
`Qt::Key_Kana_Shift` (0x0100112E)

`"KanjiMode"`

The Kanji Mode key. Enables entering Japanese text using the ideographic characters of Chinese origin.

`VK_KANJI` \[2\]

`kVK_JIS_Kana` (0x68)

`GDK_KEY_Kanji` (0xFF21)  
`Qt::Key_Kanji` (0x01001121)

`KEYCODE_KANA` (218)

`"Katakana"`

The Katakana key.

`VK_OEM_FINISH` (0xF1)

`GDK_KEY_Katakana` (0xFF26)  
`Qt::Key_Katakana` (0x01001126)

`"Romaji"` \[5\]

The Romaji key; selects the Roman character set.

`VK_OEM_BACKTAB` (0xF5)

`GDK_KEY_Romaji` (0xFF24)  
`Qt::Key_Romaji` (0x01001124)

`"Zenkaku"` \[4\]

The Zenkaku (full width) characters key.

`VK_OEM_ENLW` (0xF4)

`GDK_KEY_Zenkaku` (0xFF28)  
`Qt::Key_Zenkaku` (0x01001128)

`"ZenkakuHanaku"` \[6\]

The Zenkaku/Hankaku (full width/half width) toggle key.

`GDK_KEY_Zenkaku_Hankaku` (0xFF2A)  
`Qt::Zenkaku_Hankaku` (0x0100112A)

`KEYCODE_ZENKAKU_HANKAKU` (211)

\[1\] Prior to Firefox 37, the Eisu key was mapped to `"RomanCharacters"` by mistake.

\[2\] `VK_HANGUL` and `VK_KANA` share the same numeric key value on Windows, as do `VK_HANJA` and `VK_KANJI`.

\[3\] Prior to Firefox 37, the Hankaku (half-width) key generated the key value `"HalfWidth"` on Firefox. Also, this key generates the value `"Unidentified"` on Internet Explorer (tested on release 9 and 11).

\[4\] Internet Explorer (tested on release 9 and 11) reports `"Unidentified"` for the Zenkaku key; Firefox 36 and earlier identify this key as `"FullWidth"` on Japanese keyboard layouts and `"Unidentified"` on all other keyboard layouts. Firefox 37 and later, and all versions of Google Chrome, correctly return `"Zenkaku"`.

\[5\] `"Unidentified"` in Internet Explorer (tested on release 9 and 11). Firefox 36 and earlier identify the Romaji key as `"RomanCharacters"` on Japanese keyboards and `"Unidentified"` for other keyboards; this is corrected to return `"Romaji"` in Firefox 37 and later.

\[6\] This key is reported as `"Unidentified"` prior to Firefox 37.

### Dead keycodes for Linux

Linux generates accented characters using special **dead keys**. _Dead keys_ are keys which are pressed in combination with character keys to generate accented forms of those characters. You can identify which specific dead key was used (if more than one exists) by examining the [`KeyboardEvent`](../../keyboardevent)'s associated `compositionupdate` event's [`data`](../../compositionevent/data) property.

You can find a table of the dead keys and the characters they can be used with to generate accented or otherwise special characters on Linux using GTK.

The value of [`data`](../../compositionevent/data) will be one of the following:

<table><thead><tr class="header"><th><code>CompositionEvent.data</code> value</th><th>Symbol</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><code>GDK_KEY_dead_grave</code> (0xFE50)<br />
<code>Qt::Key_Dead_Grave</code> (0x01001250)</td><td>`</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_acute</code> (0xFE51)<br />
<code>Qt::Key_Dead_Acute</code> (0x01001251)</td><td>´</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_circumflex</code> (0xFE52)<br />
<code>Qt::Key_Dead_Circumflex</code> (0x01001252)</td><td>ˆ</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_tilde</code> (0xFE53)<br />
<code>Qt::Key_Dead_Tilde</code> (0x01001253)</td><td>˜</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_perispomeni</code> (0xFE53)</td><td>͂</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_macron</code> (0xFE54)<br />
<code>Qt::Key_Dead_Macron</code> (0x01001254)</td><td>¯</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_breve</code> (0xFE55)<br />
<code>Qt::Key_Dead_Breve</code> (0x01001255)</td><td>˘</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_abovedot</code> (0xFE56)<br />
<code>Qt::Key_Dead_Abovedot</code> (0x01001256)</td><td>˙</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_diaeresis</code> (0xFE57)<br />
<code>Qt::Key_Dead_Diaeresis</code> (0x01001257)</td><td>¨</td><td>Also called an umlaut.</td></tr><tr class="even"><td><code>GDK_KEY_dead_abovering</code> (0xFE58)<br />
<code>Qt::Key_Dead_Abovering</code> (0x01001258)</td><td>˚</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_doubleacute</code> (0xFE59)<br />
<code>Qt::Key_Dead_Doubleacute</code> (0x01001259)</td><td>˝</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_caron</code> (0xFE5A)<br />
<code>Qt::Key_Dead_Caron</code> (0x0100125A)</td><td>ˇ</td><td>Also called a háček; used in Czech among other languages.</td></tr><tr class="odd"><td><code>GDK_KEY_dead_cedilla</code> (0xFE5B)<br />
<code>Qt::Key_Dead_Cedilla</code> (0x0100125B)</td><td>¸</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_ogonek</code> (0xFE5C)<br />
<code>Qt::Key_Dead_Ogonek</code> (0x0100125C)</td><td>˛</td><td>Also called a nosinė; used in Polish and Old Irish.</td></tr><tr class="odd"><td><code>GDK_KEY_dead_iota</code> (0xFE5D)<br />
<code>Qt::Key_Dead_Iota</code> (0x0100125D)</td><td>ͅ</td><td>Iota subscript.</td></tr><tr class="even"><td><code>GDK_KEY_dead_voiced_sound</code> (0xFE5E)<br />
<code>Qt::Key_Dead_Voiced_Sound</code> (0x0100125E)</td><td>゙</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_semivoiced_sound</code> (0xFE5F)<br />
<code>Qt::Key_Dead_Semivoiced_Sound</code> (0x0100125F)</td><td>゚</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_belowdot</code> (0xFE60)<br />
<code>Qt::Key_Dead_Belowdot</code> (0x01001260)</td><td>̣̣</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_hook</code> (0xFE61)<br />
<code>Qt::Key_Dead_Hook</code> (0x01001261)</td><td>̡</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_horn</code> (0xFE62)<br />
<code>Qt::Key_Dead_Horn</code> (0x01001262)</td><td>̛</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_stroke</code> (0xFE63)</td><td>̶̶</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_abovecomma</code> (0xFE64)</td><td>̓̓</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_psili</code> (0xFE64)</td><td>᾿</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_abovereversedcomma</code> (0xFE65)</td><td>ʽ</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_dasia</code> (0xFE65)</td><td>῾</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_doublegrave</code> (0xFE66)</td><td>̏</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_belowring</code> (0xFE67)</td><td>˳</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_belowmacron</code> (0xFE68)</td><td>̱</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_belowcircumflex</code> (0xFE69)</td><td>ꞈ</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_belowtilde</code> (0xFE6A)</td><td>̰</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_belowbreve</code> (0xFE6B)</td><td>̮</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_belowdiaeresis</code> (0xFE6C)</td><td>̤</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_invertedbreve</code> (0xFE6D)</td><td>̯</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_belowcomma</code> (0xFE6E)</td><td>̦</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_currency</code> (0xFE6F)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_a</code> (0xFE80)</td><td></td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_A</code> (0xFE81)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_e</code> (0xFE82)</td><td></td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_E</code> (0xFE83)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_i</code> (0xFE84)</td><td></td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_I</code> (0xFE85)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_o</code> (0xFE86)</td><td></td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_O</code> (0xFE87)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_u</code> (0xFE88)</td><td></td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_U</code> (0xFE89)</td><td></td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_small_schwa</code> (0xFE8A)</td><td>ə</td><td></td></tr><tr class="odd"><td><code>GDK_KEY_dead_capital_schwa</code> (0xFE8B)</td><td>Ə</td><td></td></tr><tr class="even"><td><code>GDK_KEY_dead_greek</code> (0xFE8C)</td><td></td><td></td></tr></tbody></table>

## Function keys

While various platforms support different numbers of the general-purpose function keys, such as F1–F12 (or F1–F10, or F1–F15, etc.), the first few are specifically defined as follows.

If more function keys are available, their names continue the pattern here by continuing to increment the numeric portion of each key's name, so that, for example, `"F24"` is a valid key value.

`KeyboardEvent.key` value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"F1"`

The first general-purpose function key, F1.

`VK_F1` (0x70)

`kVK_F1` (0x7A)

`GDK_KEY_F1` (0xFFBE)  
`GDK_KEY_KP_F1` (0xFF91)  
`Qt::Key_F1` (0x01000030)

`KEYCODE_F1` (131)

`"F2"`

The F2 key.

`VK_F2` (0x71)

`kVK_F2` (0x78)

`GDK_KEY_F2` (0xFFBF)  
`GDK_KEY_KP_F2` (0xFF92)  
`Qt::Key_F2` (0x01000031)

`KEYCODE_F2` (132)

`"F3"`

The F3 key.

`VK_F3` (0x72)

`kVK_F3` (0x63)

`GDK_KEY_F3` (0xFFC0)  
`GDK_KEY_KP_F3` (0xFF93)  
`Qt::Key_F3` (0x01000032)

`KEYCODE_F3` (133)

`"F4"`

The F4 key.

`VK_F4` (0x73)

`kVK_F4` (0x76)

`GDK_KEY_F4` (0xFFC1)  
`GDK_KEY_KP_F4` (0xFF94)  
`Qt::Key_F4` (0x01000033)

`KEYCODE_F4` (134)

`"F5"`

The F5 key.

`VK_F5` (0x74)

`kVK_F5` (0x60)

`GDK_KEY_F5` (0xFFC2)  
`Qt::Key_F5` (0x01000034)

`KEYCODE_F5` (135)

`"F6"`

The F6 key.

`VK_F6` (0x75)

`kVK_F6` (0x61)

`GDK_KEY_F6` (0xFFC3)  
`Qt::Key_F6` (0x01000035)

`KEYCODE_F6` (136)

`"F7"`

The F7 key.

`VK_F7` (0x76)

`kVK_F7` (0x62)

`GDK_KEY_F7` (0xFFC4)  
`Qt::Key_F7` (0x01000036)

`KEYCODE_F7` (137)

`"F8"`

The F8 key.

`VK_F8` (0x77)

`kVK_F8` (0x64)

`GDK_KEY_F8` (0xFFC5)  
`Qt::Key_F8` (0x01000037)

`KEYCODE_F8` (138)

`"F9"`

The F9 key.

`VK_F9` (0x78)

`kVK_F9` (0x65)

`GDK_KEY_F9` (0xFFC6)  
`Qt::Key_F9` (0x01000038)

`KEYCODE_F9` (139)

`"F10"`

The F10 key.

`VK_F10` (0x79)

`kVK_F10` (0x6D)

`GDK_KEY_F10` (0xFFC7)  
`Qt::Key_F10` (0x01000039)

`KEYCODE_F10` (140)

`"F11"`

The F11 key.

`VK_F11` (0x7A)

`kVK_F11` (0x67)

`GDK_KEY_F11` (0xFFC8)  
`Qt::Key_F11` (0x0100003A)

`KEYCODE_F11` (141)

`"F12"`

The F12 key.

`VK_F12` (0x7B)

`kVK_F12` (0x6F)

`GDK_KEY_F12` (0xFFC9)  
`Qt::Key_F12` (0x0100003B)

`KEYCODE_F12` (142)

`"F13"`

The F13 key.

`VK_F13` (0x7C)

`kVK_F13` (0x69)

`GDK_KEY_F13` (0xFFCA)  
`Qt::Key_F13` (0x0100003C)

`KEYCODE_F13`

`"F14"`

The F14 key.

`VK_F14` (0x7D)

`kVK_F14` (0x6B)

`GDK_KEY_F14` (0xFFCB)  
`Qt::Key_F1`4 (0x0100003D)

`KEYCODE_F14`

`"F15"`

The F15 key.

`VK_F15` (0x7E)

`kVK_F15` (0x71)

`GDK_KEY_F15` (0xFFCC)  
`Qt::Key_F1`5 (0x0100003E)

`KEYCODE_F15`

`"F16"`

The F16 key.

`VK_F16` (0x7F)

`kVK_F16` (0x6A)

`GDK_KEY_F16` (0xFFCD)  
`Qt::Key_F1`6 (0x0100003F)

`KEYCODE_F16`

`"F17"`

The F17 key.

`VK_F17` (0x80)

`kVK_F17` (0x40)

`GDK_KEY_F17` (0xFFCE)  
`Qt::Key_F1`7 (0x01000040)

`KEYCODE_F17`

`"F18"`

The F18 key.

`VK_F18` (0x81)

`kVK_F18` (0x4F)

`GDK_KEY_F18` (0xFFCF)  
`Qt::Key_F1`8 (0x01000041)

`KEYCODE_F18`

`"F19"`

The F19 key.

`VK_F19` (0x82)

`kVK_F19` (0x50)

`GDK_KEY_F19` (0xFFD0)  
`Qt::Key_F1`9 (0x01000042)

`KEYCODE_F19`

`"F20"`

The F20 key.

`VK_F20` (0x83)

`kVK_F20` (0x5A)

`GDK_KEY_F20` (0xFFD1)  
`Qt::Key_F20` (0x01000043)

`KEYCODE_F20`

`"Soft1"`

The first general-purpose virtual function key.

`Qt::Key_Context1` (0x01100000)

`"Soft2"`

The second general-purpose virtual function key.

`Qt::Key_Context2` (0x01100001)

`"Soft3"`

The third general-purpose virtual function key.

`Qt::Key_Context3` (0x01100002)

`"Soft4"`

The fourth general-purpose virtual function key.

`Qt::Key_Context4` (0x01100003)

## Phone keys

These keys represent buttons which commonly exist on modern smartphones.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"AppSwitch"`

Presents a list of recently-used applications which lets the user change apps quickly.

`KEYCODE_APP_SWITCH` (181)

`"Call"`

The Call key. Dials the number which has been entered.

`Qt::Key_Call` (0x01100004)

`KEYCODE_CALL` (5)

`"Camera"`

The Camera key. Activates the camera.

`Qt::Key_Camera` (0x01100020)

`KEYCODE_CAMERA` (27)

`"CameraFocus"`

The Focus key. Focuses the camera.

`Qt::Key_CameraFocus` (0x01100021)

`KEYCODE_FOCUS` (80)

`"EndCall"`

The End Call or Hang Up button.

`Qt::Key_Hangup` (0x01100005)

`KEYCODE_ENDCALL` (6)

`"GoBack"`

The Back button.

`KEYCODE_BACK` (4)

`"GoHome"` \[1\]

The Home button. Returns the user to the phone's main screen (usually an application launcher).

`KEYCODE_HOME` (3)

`"HeadsetHook"`

The Headset Hook key. This is typically actually a button on the headset which is used to hang up calls and play or pause media.

`Qt::Key_ToggleCallHangup` (0x01100007)

`KEYCODE_HEADSETHOOK` (79)

`"LastNumberRedial"`

The Redial button. Redials the last-called number.

`Qt::Key_LastNumberRedial` (0x01100009)

`"Notification"`

The Notification key.

`KEYCODE_NOTIFICATION` (83)

`"MannerMode"`

A button which cycles among the notification modes: silent, vibrate, ring, and so forth.

`KEYCODE_MANNER_MODE` (205)

`"VoiceDial"`

The Voice Dial key. Initiates voice dialing.

`Qt::Key_VoiceDial` (0x01100008)

`KEYCODE_VOICE_ASSIST` (231)

\[1\] Prior to Firefox 37, the Home button generated a key code of `"Exit"`. Starting in Firefox 37, the button generates the key code `"MozHomeScreen"`.

## Multimedia keys

The multimedia keys are extra buttons or keys for controlling media devices, found on some keyboards.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"ChannelDown"`

Switches to the previous channel.

`APPCOMMAND_MEDIA_CHANNEL_DOWN`

`Qt::Key_ChannelDown` (0x01000119)

`KEYCODE_CHANNEL_DOWN` (167)

`"ChannelUp"`

Switches to the next channel.

`APPCOMMAND_MEDIA_CHANNEL_UP`

`Qt::Key_ChannelUp` (0x01000118)

`KEYCODE_CHANNEL_UP` (166)

`"MediaFastForward"` \[2\]

Starts, continues, or increases the speed of fast forwarding the media.

`APPCOMMAND_MEDIA_FAST_FORWARD`

`GDK_KEY_AudioForward (0x1008FF97) Qt:Key_AudioForward` (0x01000102)

`KEYCODE_MEDIA_FAST_FORWARD` (90)

`"MediaPause"`

Pauses the currently playing media.

**Note:** Some older applications use `"Pause"`, but this is not correct.

`APPCOMMAND_MEDIA_PAUSE`

`GDK_KEY_AudioPause` (0x1008FF31)  
`Qt::Key_MediaPause` (0x1000085)

`KEYCODE_MEDIA_PAUSE` (127)

`"MediaPlay"`

Starts or continues playing media at normal speed, if not already doing so. Has no effect otherwise.

`APPCOMMAND_MEDIA_PLAY`

`GDK_KEY_AudioPlay` (0x1008FF14)

` KEYCODE_MEDIA_PLAY`` (126) `

`"MediaPlayPause"`

Toggles between playing and pausing the current media.

`VK_MEDIA_PLAY_PAUSE` (0xB3)  
`APPCOMMAND_MEDIA_PLAY_PAUSE`

`Qt::Key_MediaTogglePlayPause` (0x1000086)

`KEYCODE_MEDIA_PLAY_PAUSE` (85)

`"MediaRecord"`

Starts or resumes recording media.

`APPCOMMAND_MEDIA_RECORD`

`GDK_KEY_AudioRecord` (0x1008FF1C)  
`Qt::Key_MediaRecord` (0x01000084)

` KEYCODE_MEDIA_RECORD`` (130) `

`"MediaRewind"`

Starts, continues, or increases the speed of rewinding the media.

`APPCOMMAND_MEDIA_REWIND`

`GDK_KEY_AudioRewind` (0x1008FF3E)  
`Qt::Key_AudioRewind` (0x010000C5)

` KEYCODE_MEDIA_REWIND`` (89) `

`"MediaStop"`

Stops the current media activity (such as playing, recording, pausing, forwarding, or rewinding). Has no effect if the media is currently stopped already.

`VK_MEDIA_STOP` (0xB2)  
`APPCOMMAND_MEDIA_STOP`

`GDK_KEY_AudioStop` (0x1008FF15)  
`Qt::Key_MediaStop` (0x01000081)

`KEYCODE_MEDIA_STOP` (86)

`"MediaTrackNext"` \[1\]

Seeks to the next media or program track.

`VK_MEDIA_NEXT_TRACK` (0xB0)  
`APPCOMMAND_MEDIA_NEXTTRACK`

`GDK_KEY_AudioNext` (0x1008FF17)  
`Qt::Key_MediaNext` (0x01000083)

`KEYCODE_MEDIA_NEXT` (87)

`"MediaTrackPrevious"` \[1\]

Seeks to the previous media or program track.

`VK_MEDIA_PREV_TRACK` (0xB1)  
`APPCOMMAND_MEDIA_PREVIOUSTRACK`

`GDK_KEY_AudioPrev` (0x1008FF16)  
`Qt::Key_MediaPrevious` (0x01000082)

`KEYCODE_MEDIA_PREVIOUS` (88)

\[1\] Internet Explorer, Edge, and Firefox (36 and earlier) use `"MediaNextTrack"` and `"MediaPreviousTrack"` instead of `"MediaTrackNext"` and `"MediaTrackPrevious"`.

\[2\] Prior to Firefox 37, Firefox generated the key code `"FastFwd"` on some platforms and `"Unidentified"` on others instead of `"MediaFastForward"`.

## Audio control keys

These media keys are used specifically for controlling audio.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"AudioBalanceLeft"`

Adjusts audio balance toward the left.

`VK_AUDIO_BALANCE_LEFT`

`"AudioBalanceRight"`

Adjusts audio balance toward the right.

`VK_AUDIO_BALANCE_RIGHT`

`"AudioBassDown"`

Decreases the amount of bass.

`APPCOMMAND_BASS_DOWN`

`"AudioBassBoostDown"`

Reduces bass boosting or cycles downward through bass boost modes or states.

`VK_BASS_BOOST_DOWN`

`"AudioBassBoostToggle"`

Toggles bass boosting on and off.

`APPCOMMAND_BASS_BOOST`

`"AudioBassBoostUp"`

Increases the amoung of bass boosting, or cycles upward through a set of bass boost modes or states.

`VK_BASS_BOOST_UP`

`"AudioBassUp"`

Increases the amount of bass.

`APPCOMMAND_BASS_UP`

`"AudioFaderFront"`

Adjusts the audio fader toward the front.

`VK_FADER_FRONT`

`"AudioFaderRear"`

Adjusts the audio fader toward the rear.

`VK_FADER_REAR`

`"AudioSurroundModeNext"`

Selects the next available surround sound mode.

`VK_SURROUND_MODE_NEXT`

`"AudioTrebleDown"`

Decreases the amount of treble.

`APPCOMMAND_TREBLE_DOWN`

`"AudioTrebleUp"`

Increases the amount of treble.

`APPCOMMAND_TREBLE_UP`

`"AudioVolumeDown" [1]`

Decreases the audio volume.

`VK_VOLUME_DOWN` (0xAE)  
`APPCOMMAND_VOLUME_DOWN`

`kVK_VolumeDown` (0x49)

`GDK_KEY_AudioLowerVolume` (0x1008FF11)  
`Qt::Key_VolumeDown` (0x01000070)

`KEYCODE_VOLUME_DOWN` (25)

`"AudioVolumeMute" [1]`

Mutes the audio.

`VK_VOLUME_MUTE` (0xAD)  
`APPCOMMAND_VOLUME_MUTE`

`kVK_Mute` (0x4A)

`GDK_KEY_AudioMute` (0x1008FF12)  
`Qt::Key_VolumeMute` (0x01000071)

`KEYCODE_VOLUME_MUTE` (164)

`"AudioVolumeUp" [1]`

Increases the audio volume.

`VK_VOLUME_UP` (0xAF)  
`APPCOMMAND_VOLUME_UP`

`kVK_VolumeUp` (0x48)

`GDK_KEY_AudioRaiseVolume` (0x1008FF13)  
`Qt::Key_VolumeUp` (0x01000072)

`KEYCODE_VOLUME_UP` (24)

`"MicrophoneToggle"`

Toggles the microphone on and off.

`APPCOMMAND_MIC_ON_OFF_TOGGLE`

`"MicrophoneVolumeDown"`

Decreases the microphone's input volume.

`APPCOMMAND_MICROPHONE_VOLUME_DOWN`

`Qt::Key_MicVolumeDown` (0x0100011E)

`"MicrophoneVolumeMute"`

Mutes the microphone input.

`APPCOMMAND_MICROPHONE_VOLUME_MUTE`

`GDK_KEY_AudioMicMute` (0x1008FFB2)  
`Qt::Key_MicMute` (0x01000113)

`KEYCODE_MUTE` (91)

`"MicrophoneVolumeUp"`

Increases the microphone's input volume.

`APPCOMMAND_MICROPHONE_VOLUME_UP`

`Qt::Key_MicVolumeUp` (0x0100011D)

\[1\] Internet Explorer, Edge, and Firefox (48 and earlier) use `"VolumeUp"`, `"VolumeDown"`, and `"VolumeMute"` instead of `"AudioVolumeUp"`, `"AudioVolumeDown"`, and `"AudioVolumeMute"`. In Firefox 49 they were updated to match the latest specification. The old names are still used on [Boot to Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/B2G_OS).

## TV control keys

These key values represent buttons or keys present on television devices, or computers or phones which have TV support.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"TV"` \[1\]

Switches into TV viewing mode.

`KEYCODE_TV` (170)

`"TV3DMode"`

Toggles 3D TV mode on and off.

`KEYCODE_3D_MODE` (206)

`"TVAntennaCable"`

Toggles between antenna and cable inputs.

`KEYCODE_TV_ANTENNA_CABLE` (242)

`"TVAudioDescription"`

Toggles audio description mode on and off.

`KEYCODE_TV_AUDIO_DESCRIPTION` (252)

`"TVAudioDescriptionMixDown"`

Decreases trhe audio description's mixing volume; reduces the volume of the audio descriptions relative to the program sound.

`KEYCODE_TV_AUDIO_DESCRIPTION_MIX_DOWN` (254)

`"TVAudioDescriptionMixUp"`

Increases the audio description's mixing volume; increases the volume of the audio descriptions relative to the program sound.

`KEYCODE_TV_AUDIO_DESCRIPTION_MIX_UP` (253)

`"TVContentsMenu"`

Displays or hides the media contents available for playback (this may be a channel guide showing the currently airing programs, or a list of media files to play).

`KEYCODE_TV_CONTENTS_MENU` (256)

`"TVDataService"`

Displays or hides the TV's data service menu.

`KEYCODE_TV_DATA_SERVICE` (230)

`"TVInput"` \[2\]

Cycles the input mode on an external TV.

`KEYCODE_TV_INPUT` (178)

`"TVInputComponent1"`

Switches to the input "Component 1."

`KEYCODE_TV_INPUT_COMPONENT_1` (249)

`"TVInputComponent2"`

Switches to the input "Component 2."

`KEYCODE_TV_INPUT_COMPONENT_2` (250)

`"TVInputComposite1"`

Switches to the input "Composite 1."

`KEYCODE_TV_INPUT_COMPOSITE_1` (247)

`"TVInputComposite2"`

Switches to the input "Composite 2."

`KEYCODE_TV_INPUT_COMPOSITE_2` (248)

`"TVInputHDMI1"`

Switches to the input "HDMI 1."

`KEYCODE_TV_INPUT_HDMI_1` (243)

`"TVInputHDMI2"`

Switches to the input "HDMI 2."

`KEYCODE_TV_INPUT_HDMI_2` (244)

`"TVInputHDMI3"`

Switches to the input "HDMI 3."

`KEYCODE_TV_INPUT_HDMI_3` (245)

`"TVInputHDMI4"`

Switches to the input "HDMI 4."

`KEYCODE_TV_INPUT_HDMI_4` (246)

`"TVInputVGA1"`

Switches to the input "VGA 1."

`KEYCODE_TV_INPUT_VGA_1` (251)

`"TVMediaContext"`

The Media Context menu key.

`KEYCODE_TV_MEDIA_CONTEXT_MENU` (257)

`"TVNetwork"`

Toggle the TV's network connection on and off.

`KEYCODE_TV_NETWORK` (241)

`"TVNumberEntry"`

Put the TV into number entry mode.

`KEYCODE_TV_NUMBER_ENTRY` (234)

`"TVPower"` \[2\]

The device's power button.

`KEYCODE_TV_POWER` (177)

`"TVRadioService"`

Radio button.

`KEYCODE_TV_RADIO_SERVICE` (232)

`"TVSatellite"`

Satellite button.

`KEYCODE_TV_SATELLITE` (237)

`"TVSatelliteBS"`

Broadcast Satellite button.

`KEYCODE_TV_SATELLITE_BS` (238)

`"TVSatelliteCS"`

Communication Satellite button.

`KEYCODE_TV_SATELLITE_CS` (239)

`"TVSatelliteToggle"`

Toggles among available satellites.

`KEYCODE_TV_SATELLITE_SERVICE` (240)

`"TVTerrestrialAnalog"`

Selects analog terrestrial television service (analog cable or antenna reception).

`KEYCODE_TV_TERRESTRIAL_ANALOG` (235)

`"TVTerrestrialDigital"`

Selects digital terrestrial television service (digital cable or antenna receiption).

`KEYCODE_TV_TERRESTRIAL_DIGITAL` (236)

`"TVTimer"`

Timer programming button.

`KEYCODE_TV_TIMER_PROGRAMMING` (258)

\[1\] Firefox added proper support for the `"TV"` key in Firefox 37; before that, this key generated the key code `"Live"`.

\[2\] These keys were `"Unidentified"` until Firefox 37.

## Media controller keys

Because modern remote controls for media devices often include buttons beyond the basic controls covered elsewhere in this document, key values are defined for a broad array of these additional buttons.

The values below are derived in part form a number of consumer electronics technical specifications:

- [DTV Application Software Environment](http://atsc.org/standard/a100-dtv-application-software-environment-level-1-dase-1/) (part of the [ATSC](https://en.wikipedia.org/wiki/ATSC) specification)
- [Open Cable Application Platform 1.1.3](https://www.cablelabs.com/specifications/OC-SP-OCAP1.1.3-100603.pdf)
- [ANSI/CEA-2014-B](http://www.ce.org/Standards/Standard-Listings/R7-Home-Network-Committee/CEA-2014-B-(ANSI%29.aspx): Web-based Protocol and Framework for Remote User Interface on UPnP™ Networks and the Internet
- [Android KeyEvent key code values](https://developer.android.com/reference/android/view/KeyEvent.html)

**Note:** Remote controls typically include keys whose values are already defined elsewhere, such as under [Multimedia keys](#multimedia_keys) or [Audio control keys](#audio_control_keys). Those keys' values will match what's documented in those tables.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"AVRInput"` \[3\]

Changes the input mode on an external audio/video receiver (AVR) unit.

`KEYCODE_AVR_INPUT` (182)

`"AVRPower"` \[3\]

Toggles the power on an external AVR unit.

`KEYCODE_AVR_POWER` (181)

`"ColorF0Red"` \[3\]

General-purpose media function key, color-coded red. This has index `0` among the colored keys.

`VK_COLORED_KEY_0`

`KEYCODE_PROG_RED` (183)

`"ColorF1Green"` \[3\]

General-purpose media funciton key, color-coded green. This has index `1` among the colored keys.

`VK_COLORED_KEY_1`

`KEYCODE_PROG_GREEN` (184)

`"ColorF2Yellow"` \[3\]

General-purpose media funciton key, color-coded yellow. This has index `2` among the colored keys.

`VK_COLORED_KEY_2`

`KEYCODE_PROG_YELLOW` (185)

`"ColorF3Blue"` \[3\]

General-purpose media funciton key, color-coded blue. This has index `3` among the colored keys.

`VK_COLORED_KEY_3`

`KEYCODE_PROG_BLUE` (186)

`"ColorF4Grey"`

General-purpose media funciton key, color-coded grey. This has index `4` among the colored keys.

`VK_COLORED_KEY_4`

`KEYCODE_PROG_GREY`

`"ColorF5Brown"`

General-purpose media funciton key, color-coded brown. This has index `5` among the colored keys.

`VK_COLORED_KEY_5`

`KEYCODE_PROG_BROWN`

`"ClosedCaptionToggle"`

Toggles closed captioning on and off.

`VK_CC`

`KEYCODE_CAPTIONS` (175)

`"Dimmer"`

Adjusts the brightness of the device by toggling between two brightness levels _or_ by cycling among multiple brightness levels.

`VK_DIMMER`

`GDK_KEY_BrightnessAdjust` (0x1008FF3B)

`"DisplaySwap"`

Cycles among video sources.

`VK_DISPLAY_SWAP`

`"DVR"`

Switches the input source to the Digital Video Recorder (DVR).

`KEYCODE_DVR` (173)

`"Exit"`

The Exit button, which exits the curreent application or menu.

`VK_EXIT`

`Qt::Key_Exit` (0x0102000a)

`"FavoriteClear0"`

Clears the program or content stored in the first favorites list slot.

`VK_CLEAR_FAVORITE_0`

`"FavoriteClear1"`

Clears the program or content stored in the second favorites list slot.

`VK_CLEAR_FAVORITE_1`

`"FavoriteClear2"`

Clears the program or content stored in the third favorites list slot.

`VK_CLEAR_FAVORITE_2`

`"FavoriteClear3"`

Clears the program or content stored in the fourth favorites list slot.

`VK_CLEAR_FAVORITE_3`

`"FavoriteRecall0"`

Selects (recalls) the program or content stored in the first favorites list slot.

`VK_RECALL_FAVORITE_0`

`"FavoriteRecall1"`

Selects (recalls) the program or content stored in the second favorites list slot.

`VK_RECALL_FAVORITE_1`

`"FavoriteRecall2"`

Selects (recalls) the program or content stored in the third favorites list slot.

`VK_RECALL_FAVORITE_2`

`"FavoriteRecall3"`

Selects (recalls) the program or content stored in the fourth favorites list slot.

`VK_RECALL_FAVORITE_3`

`"FavoriteStore0"`

Stores the current program or content into the first favorites list slot.

`VK_STORE_FAVORITE_0`

`"FavoriteStore1"`

Stores the current program or content into the second favorites list slot.

`VK_STORE_FAVORITE_1`

`"FavoriteStore2"`

Stores the current program or content into the third favorites list slot.

`VK_STORE_FAVORITE_2`

`"FavoriteStore3"`

Stores the current program or content into the fourth favorites list slot.

`VK_STORE_FAVORITE_3`

`"Guide"`

Toggles the display of the program or content guide.

`VK_GUIDE`

`Qt::Key_Guide` (0x0100011A)

`KEYCODE_GUIDE` (172)

`"GuideNextDay"`

If the guide is currently displayed, this button tells the guide to display the next day's content.

`VK_NEXT_DAY`

`"GuidePreviousDay"`

If the guide is currently displayed, this button tells the guide to display the previous day's content.

`VK_PREV_DAY`

`"Info"`

Toggles the display of information about the currently selected content, program, or media.

`VK_INFO`

`Qt::Key_Info` (0x0100011B)

`KEYCODE_INFO` (165)

`"InstantReplay"`

Tells the device to perform an instant replay (typically some form of jumping back a short amount of time then playing it again, possibly but not usually in slow motion).

`VK_INSTANT_REPLAY`

`"Link"`

Opens content liniked to the current program, if available and possible.

`VK_LINK`

`"ListProgram"`

Lists the current program.

`VK_LIST`

`"LiveContent"`

Toggles a display listing currently available live content or programs.

`VK_LIVE`

`"Lock"`

Locks or unlocks the currently selected content or pgoram.

`VK_LOCK`

`"MediaApps"`

Presents a list of media applications, such as photo viewers, audio and video players, and games. \[1\]

`VK_APPS`

`"MediaAudioTrack"`

The Audio Track key.

GDK_KEY_AudioCycleTrack (0x1008FF9B)  
`Qt::Key_AudioCycleTrack` (0x01000106)

`KEYCODE_MEDIA_AUDIO_TRACK` (222)

`"MediaLast"`

Jumps back to the last-viewed content, program, or other media.

`VK_LAST`

`Qt::Key_MediaLast` (0x0100FFFF)

`KEYCODE_LAST_CHANNEL` (229)

`"MediaSkipBackward"`

Skips backward to the previous content or program.

`KEYCODE_MEDIA_SKIP_BACKWARD`

`"MediaSkipForward"`

Skips forward to the next content or program.

`VK_SKIP`

`KEYCODE_MEDIA_SKIP_FORWARD`

`"MediaStepBackward"`

Steps backward to the previous content or program.

`KEYCODE_MEDIA_STEP_BACKWARD`

`"MediaStepForward"`

Steps forward to the next content or program.

`KEYCODE_MEDIA_SKIP_FORWARD`

`"MediaTopMenu"`

Top Menu button. Opens the media's main menu (e.g., for a DVD or Blu-Ray disc).

`Qt::Key_TopMenu` (0x0100010A)

`KEYCODE_MEDIA_TOP_MENU`

`"NavigateIn"`

Navigates into a submenu or option.

`KEYCODE_NAVIGATE_IN`

`"NavigateNext"`

Navigates to the next item.

`KEYCODE_NAVIGATE_NEXT`

`"NavigateOut"`

Navigates out of the current screen or menu.

`KEYCODE_NAVIGATE_OUT`

`"NavigatePrevious"`

Navigates to the previous item.

`KEYCODE_NAVIGATE_PREVIOUS`

`"NextFavoriteChannel"`

Cycles to the next channel in the favorites list.

`VK_NEXT_FAVORITE_CHANNEL`

`"NextUserProfile"`

Cycles to the next saved user profile, if this feature is supported and multiple profiles exist.

`VK_USER`

`"OnDemand"`

Opens the user interface for selecting on demand content or programs to watch.

`VK_ON_DEMAND`

`"Pairing"`

Starts the process of pairing the remote with a device to be controlled.

`KEYCODE_PAIRING` (225)

`"PinPDown"`

A button to move the picture-in-picture view downward.

`VK_PINP_DOWN`

`"PinPMove"`

A button to control moving the picture-in-picture view.

`VK_PINP_MOVE`

`"PinPToggle"`

Toggles display of th epicture-in-picture view on and off.

`VK_PINP_TOGGLE`

`"PinPUp"`

A button to move the picture-in-picture view upward.

`VK_PINP_UP`

`"PlaySpeedDown"`

Decreases the media playback rate.

`VK_PLAY_SPEED_DOWN`

`"PlaySpeedReset"`

Returns the media playback rate to normal.

`VK_PLAY_SPEED_RESET`

`"PlaySpeedUp"`

Increases the media playback rate.

`VK_PLAY_SPEED_UP`

`"RandomToggle"`

Toggles random media (also known as "shuffle mode") on and off.

`VK_RANDOM_TOGGLE`

`GDK_KEY_AudioRandomPlay` (0x1008FF99)

`"RcLowBattery"`

A code sent when the remote control's battery is low. This doesn't actually correspond to a physical key at all.

`VK_RC_LOW_BATTERY`

`"RecordSpeedNext"`

Cycles among the available media recording speeds.

`VK_RECORD_SPEED_NEXT`

`"RfBypass"`

Toggles radio frequency (RF) input bypass mode on and off. RF bypass mode passes RF input directly to the RF output without any processing or filtering.

`VK_RF_BYPASS`

`"ScanChannelsToggle"`

Toggles the channel scan mode on and off. This is a mode which flips through channels automatically until the user stops the scan.

`VK_SCAN_CHANNELS_TOGGLE`

`"ScreenModeNext"`

Cycles through the available screen display modes.

`VK_SCREEN_MODE_NEXT`

`"Settings"`

Toggles display of the device's settings screen on and off.

`VK_SETTINGS`

`Qt::Key_Settings` (0x0100011C)

`KEYCODE_SETTINGS`

`"SplitScreenToggle"`

Toggles split screen display mode on and off.

`VK_SPLIT_SCREEN_TOGGLE`

`GDK_KEY_SplitScreen (`0x1008FF7D)  
`Qt::Key_SplitScreen` (0x010000ED)

`"STBInput"` \[3\]

Cycles among input modes on an external set-top box (STB).

`KEYCODE_STB_INPUT` (180)

`"STBPower"` \[3\]

Toggles on and off an external STB.

`KEYCODE_STB_POWER` (179)

`"Subtitle"`

Toggles the display of subtitles on and off if they're available.

`VK_SUBTITLE`

`GDK_KEY_Subtitle` (0x1008FF9A)

`KEYCODE_CAPTIONS` (175)

`"Teletext"`

Toggles display of [teletext](https://en.wikipedia.org/wiki/Teletext), if available.

`VK_TELETEXT`

`KEYCODE_TV_TELETEXT` (233)

`"VideoModeNext"` \[3\]

Cycles through the available video modes.

`VK_VIDEO_MODE_NEXT`

`GDK_KEY_Next_VMode` (0x1008FE22)

`"Wink"`

Causes the device to identify itself in some fashion, such as by flashing a light, briefly changing the brightness of indicator lights, or emitting a tone.

`VK_WINK`

`"ZoomToggle"` \[2\]

Toggles between full-screen and scaled content display, or otherwise change the magnification level.

`VK_ZOOM` (0xFB)

`Qt::Key_Zoom` (0x01020006)

`KEYCODE_TV_ZOOM_MODE` (255)

\[1\] Don't confuse the media controller `VK_APPS` key with the Windows `VK_APPS` key, which is also known as `VK_CONTEXT_MENU`. That key is encoded as `"ContextMenu"`.

\[2\] Internet Explorer (tested on release 9 and 11) and Firefox 36 and earlier identify the zoom toggle button as `"Zoom"`. Firefox 37 corrects this to `"ZoomToggle"`.

\[3\] These keys were `"Unidentified"` until Firefox 37.

## Speech recognition keys

These special multimedia keys are used to control speech recognition features.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"SpeechCorrectionList"` \[1\]

Presents a list of possible corrections for a word which was incorrectly identified.

`APPCOMMAND_CORRECTION_LIST`

`"SpeechInputToggle"` \[2\]

Toggles between dictation mode and command/control mode. This lets the speech engine know whether to interpret spoken words as input text or as commands.

`APPCOMMAND_DICTATE_OR_COMMAND_CONTROL_TOGGLE`

\[1\] The `APPCOMMAND_CORRECTION_LIST` command on Windows generates `"Unidentified"` on Firefox.

\[2\] The `APPCOMMAND_DICTATE_OR_COMMAND_CONTROL_TOGGLE` command on Windows generates `"Unidentified"` on Firefox.

## Document keys

These keys control documents. In the specification, they're included in other sets of keys (such as the media keys), but they are more sensibly considered to be their own category.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Close"` \[1\]

Closes the current document or message. Must not exit the application.

`APPCOMMAND_CLOSE`

`GDK_KEY_Close` (0x1008FF56)  
`Qt::Key_Close` (0x010000CE)

`KEYCODE_MEDIA_CLOSE` (128)

`"New"` \[1\]

Creates a new document or message.

`APPCOMMAND_NEW`

`GDK_KEY_New` (0x1008FF68)  
`Qt::Key_New` (0x01000120)

`"Open"` \[1\]

Opens an existing document or message.

`APPCOMMAND_OPEN`

`GDK_KEY_Open` (0x1008FF6B)  
`Qt::Key_Open` (0x01000121)

`"Print"`

Prints the current document or message.

`APPCOMMAND_PRINT`

`GDK_KEY_Print` (0xFF61)  
`Qt::Print` (0x01000009)

`"Save"` \[1\]

Saves the current document or message.

`APPCOMMAND_SAVE`

`GDK_KEY_Save` (0x1008FF77)  
`Qt::Key_Save` (0x010000EA)

`"SpellCheck"` \[1\]

Starts spell checking the current document.

`APPCOMMAND_SPELL_CHECK`

`GDK_KEY_Spell` (0x1008FF7C)  
`Qt::Key_Spell` (0x010000EC)

`"MailForward"` \[1\]

Opens the user interface to forward a message.

`APPCOMMAND_FORWARD_MAIL`

`GDK_KEY_MailForward` (0x1008FF90)  
`Qt::Key_MailForward` (0x010000FB)

`"MailReply"` \[1\]

Opens the user interface to reply to a message.

`APPCOMMAND_REPLY_TO_MAIL`

`GDK_KEY_Reply` (0x1008FF72)  
`Qt::Key_Reply` (0x010000E5)

`"MailSend"` \[1\]

Sends the current message.

`APPCOMMAND_SEND_MAIL`

`GDK_KEY_Send` (0x1008FF7B)  
`Qt::Key_Send` (0x010000EB)

\[1\] Prior to Firefox 37, this key generated the key value `"Unidentified"`.

## Application selector keys

Some keyboards offer special keys for launching or switching to certain common applications. Key values for those are listed here.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"LaunchCalculator"` \[5\]

The Calculator key, often labeled with an icon. This is often used as a generic application launcher key (`APPCOMMAND_LAUNCH_APP2`).

`APPCOMMAND_LAUNCH_APP2`

`GDK_KEY_Calculator` (0x1008FF1D)  
`Qt::Key_Calculator` (0x010000CB)

`KEYCODE_CALCULATOR` (210)

`"LaunchCalendar"` \[5\]

The Calendar key. Often labeled with an icon.

`GDK_KEY_Calendar` (0x1008FF20)  
`Qt::Key_Calendar` (0x010000E4)

`KEYCODE_CALENDAR` (208)

`"LaunchContacts"`

The Contacts key.

`KEYCODE_CONTACTS` (207)

`"LaunchMail"`

The Mail key. Often labeled with an icon.

`VK_LAUNCH_MAIL` (0xB4)  
`APPCOMMAND_LAUNCH_MAIL`

`GDK_KEY_Mail` (0x1008FF19)  
`Qt::Key_LaunchMail` (0x010000A0)

`KEYCODE_ENVELOPE` (65)

`"LaunchMediaPlayer"` \[1\]

The Media Player key.

`VK_LAUNCH_MEDIA_SELECT` (0xB5)  
`APPCOMMAND_LAUNCH_MEDIA_SELECT`

`GDK_KEY_CD` (0x1008FF53)  
`GDK_KEY_Video` (0x1008FF87)  
`GDK_KEY_AudioMedia` (0x1008FF32)  
`Qt::Key_LaunchMedia` (0x010000A1)

`"LaunchMusicPlayer"` \[5\]

The Music Player key. Often labeled with an icon.

`GDK_KEY_Music` (0x1008FF92)  
`Qt::Key_Music` (0x010000FD)

`KEYCODE_MUSIC` (209)

`"LaunchMyComputer"` \[5\]

The My Computer key on Windows keyboards. This is often used as a generic application launcher key (`APPCOMMAND_LAUNCH_APP1`).

`APPCOMMAND_LAUNCH_APP1`

`GDK_KEY_MyComputer` (0x1008FF33)  
`GDK_KEY_Explorer` (0x1008FF5D)

`"LaunchPhone"`

The Phone key. Opens the phone dialer application (if one is present).

`GDK_KEY_Phone` (0x1008FF6E)  
`Qt::Key_Phone` (0x010000E3)

`"LaunchScreenSaver"` \[5\]

The Screen Saver key.

`GDK_KEY_ScreenSaver` (0x1008FF2D)  
`Qt::Key_ScreenSaver` (0x010000BA)

`"LaunchSpreadsheet"` \[4\]

The Spreadsheet key. This key may be labeled with an icon.

`GDK_KEY_Excel` (0x1008FF5C)  
`Qt::Key_Excel` (0x010000D4)

`"LaunchWebBrowser"` \[4\]

The Web Browser key. This key is frequently labeled with an icon.

`GDK_KEY_WWW` (0x1008FF2E)  
`Qt::Key_WWW` (0x010000BB)

`KEYCODE_EXPLORER` (64)

`"LaunchWebCam"` \[5\]

The WebCam key. Opens the webcam application.

`GDK_KEY_WebCam` (0x1008FF8F)  
`Qt::Key_WebCam` (0x010000FA)

`"LaunchWordProcessor"` \[5\]

The Word Processor key. This may be an icon of a specific word processor application, or a generic document icon.

`GDK_KEY_Word` (0x1008FF89)  
`Qt::Key_Word` (0x010000F4)

`"LaunchApplication1"` \[2\]

The first generic application launcher button.

`VK_LAUNCH_APP1` (0xB6)  
`APPCOMMAND_LAUNCH_APP1`

`GDK_KEY_Launch0` (0x1008FF40)  
`Qt::Key_Launch0` (0x010000A2)

`"LaunchApplication2"` \[3\]

The second generic application launcher button.

`VK_LAUNCH_APP2` (0xB7)  
`APPCOMMAND_LAUNCH_APP2`

`GDK_KEY_Launch1` (0x1008FF41)  
`Qt::Key_Launch1` (0x010000A3)

`"LaunchApplication3"`

The third generic application launcher button.

`GDK_KEY_Launch2` (0x1008FF42)  
`Qt::Key_Launch2` (0x010000A4)

`"LaunchApplication4"`

The fourth generic application launcher button.

`GDK_KEY_Launch3` (0x1008FF43)  
`Qt::Key_Launch3` (0x010000A5)

`"LaunchApplication5"`

The fifth generic application launcher button.

`GDK_KEY_Launch4` (0x1008FF44)  
`Qt::Key_Launch4` (0x010000A6)

`"LaunchApplication6"`

The sixth generic application launcher button.

`GDK_KEY_Launch5` (0x1008FF45)  
`Qt::Key_Launch5` (0x010000A7)

`"LaunchApplication7"`

The seventh generic application launcher button.

`GDK_KEY_Launch6` (0x1008FF46)  
`Qt::Key_Launch6` (0x010000A8)

`"LaunchApplication8"`

The eighth generic application launcher button.

`GDK_KEY_Launch7` (0x1008FF47)  
`Qt::Key_Launch7` (0x010000A9)

`"LaunchApplication9"`

The ninth generic application launcher button.

`GDK_KEY_Launch8` (0x1008FF48)  
`Qt::Key_Launch8` (0x010000AA)

`"LaunchApplication10"`

The 10th generic application launcher button.

`GDK_KEY_Launch9` (0x1008FF49)  
`Qt::Key_Launch9` (0x010000AB)

`"LaunchApplication11"`

The 11th generic application launcher button.

`GDK_KEY_LaunchA` (0x1008FF4A)  
`Qt::Key_LaunchA` (0x010000AC)

`"LaunchApplication12"`

The 12th generic application launcher button.

`GDK_KEY_LaunchB` (0x1008FF4B)  
`Qt::Key_LaunchB` (0x010000AD)

`"LaunchApplication13"`

The 13th generic application launcher button.

`GDK_KEY_LaunchC` (0x1008FF4C)  
`Qt::Key_LaunchC` (0x010000AE)

`"LaunchApplication14"`

The 14th generic application launcher button.

`GDK_KEY_LaunchD` (0x1008FF4D)  
`Qt::Key_LaunchD` (0x010000AF)

`"LaunchApplication15"`

The 15th generic application launcher button.

`GDK_KEY_LaunchE` (0x1008FF4E)  
`Qt::Key_LaunchE` (0x010000B0)

`"LaunchApplication16"`

The 16th generic application launcher button.

`GDK_KEY_LaunchF` (0x1008FF4F)  
`Qt::Key_LaunchF` (0x010000B1)

\[1\] Internet Explorer, Edge, and Firefox (36 and earlier) use `"SelectMedia"` instead of `"LaunchMediaPlayer"`. Firefox 37 through Firefox 48 use `"MediaSelect"`. Firefox 49 has been updated to match the latest specification, and to return `"LaunchMediaPlayer"`.

\[2\] Google Chrome 57 and earlier returned `"LaunchMyComputer"` instead of `"LaunchApplication1"`. See [Chrome Bug 612743](https://bugs.chromium.org/p/chromium/issues/detail?id=612743) for more information.

\[3\] Google Chrome 57 and earlier returned `"LaunchCalculator"` instead of `"LaunchApplication2"`. See [Chrome Bug 612743](https://bugs.chromium.org/p/chromium/issues/detail?id=612743) for more information.

\[4\] Prior to Firefox 37, Firefox returned the key code `"LaunchApplication1"` instead of "`LaunchWebBrowser"` for the Web browser key.

\[5\] Firefox introduced support for this key in Firefox 37. Prior to that, this key was reported as `"Unidentified"`.

## Browser control keys

Some keyboards include special keys for controlling Web browsers. Those keys follow.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"BrowserBack"`

Navigates to the previous content or page in the current Web view's history.

`VK_BROWSER_BACK` (0xA6)  
`APPCOMMAND_BROWSER_BACKWARD`

`GDK_KEY_Back` (0x1008FF26)  
`Qt::Key_Back` (0x01000061)

`KEYCODE_BACK` (4)

`"BrowserFavorites"` \[1\]

Opens the user's list of bookmarks/favorites.

`VK_BROWSER_FAVORITES` (0xAB)  
`APPCOMMAND_BROWSER_FAVORITES`

`GDK_KEY_Favorites` (0x1008FF30)  
`GDK_KEY_MySites` (0x1008FF67)  
`Qt::Favorites` (0x01000091)

`KEYCODE_BOOKMARK` (174)

`"BrowserForward"`

Navigates to the next content or page in the current Web view's history.

`VK_BROWSER_FORWARD` (0xA7)  
`APPCOMMAND_BROWSER_FORWARD`

`GDK_KEY_Forward` (0x1008FF27)  
`Qt::Key_Forward` (0x01000062)

`KEYCODE_FORWARD` (125)

`"BrowserHome"`

Navigates to the user's preferred home page.

`VK_BROWSER_HOME` (0xAC)  
`APPCOMMAND_BROWSER_HOME`

`GDK_KEY_HomePage` (0x1008FF18)  
`Qt::Key_HomePage` (0x01000090)

`KEYCODE_HOME` (3)

`"BrowserRefresh"`

Refreshes the current page or content.

`VK_BROWSER_REFRESH` (0xA8)  
`APPCOMMAND_BROWSER_REFRESH`

`GDK_KEY_Refresh` (0x1008FF29)  
`GDK_KEY_Reload` (0x1008FF73)

`"BrowserSearch"`

Activates the user's preferred search engine or the search interface within their browser.

`VK_BROWSER_SEARCH` (0xAA)  
`APPCOMMAND_BROWSER_SEARCH`

`GDK_KEY_Search` (0x1008FF1B)  
`Qt::Key_Search` (0x01000092)

`KEYCODE_SEARCH` (84)

`"BrowserStop"`

Stops loading the currently displayed Web view or content.

`VK_BROWSER_STOP` (0xA9)  
`APPCOMMAND_BROWSER_STOP`

`GDK_KEY_Stop` (0x1008FF28)  
`Qt::Key_Search` (0x01000063)

\[1\] Prior to Firefox 37, this key's value was reported as `"Unidentified"`.

## Numeric keypad keys

These keys are found on the keyboard's numeric keypad. However, not all are present on every keyboard. Although typical numeric keypads have numeric keys from 0 to 9 (encoded as `"0"` through `"9"`), some multimedia keyboards include additional number keys for higher numbers.

The 10 key, if present, generates events with the `key` value of `"0"`.

`KeyboardEvent.key` Value

Description

Virtual Keycode

Windows

Mac

Linux

Android

`"Decimal"` \[1\] <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The decimal point key (typically . or , depending on the region).

In newer browsers, this value to be the character generated by the decimal key (one of those two characters). \[1\]

`VK_DECIMAL` (0x6E)

`kVK_ANSI_KeypadDecimal` (0x41)

`GDK_KEY_KP_Decimal` (0xFFAE)

`KEYCODE_NUMPAD_DOT` (158)

`"Key11"`

The 11 key found on certain media numeric keypads.

`"Key12"`

The 12 key found on certain media numeric keypads.

`"Multiply"` \[1\] <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The numeric keypad's multiplication key, \*.

`VK_MULTIPLY` (0x6A)

`kVK_ANSI_KeypadMultiply` (0x43)

`GDK_KEY_KP_Multiply` (0xFFAA)  
`Qt::Key_Multiply` (0x0D7)

`KEYCODE_NUMPAD_MULTIPLY` (155)

`"Add"` \[1\] <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The numeric keypad's addition key, +.

`VK_ADD` (0x6B)

`kVK_ANSI_KeypadPlus` (0x45)

`GDK_KEY_KP_Add` (0xFFAB)

`KEYCODE_NUMPAD_ADD` (157)

`"Clear"`

The numeric keypad's Clear key.

`kVK_ANSI_KeypadClear` (0x47)

`GDK_KEY_Clear` (0xFF0B)  
`Qt::Key_Clear` (0x0100000B)

`KEYCODE_CLEAR` (28)

`"Divide"` \[1\] <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The numeric keypad's division key, /.

`VK_DIVIDE` (0x6F)

`kVK_ANSI_KeypadDivide` (0x4B)

`GDK_KEY_KP_Divide` (0xFFAF)  
`Qt::Key_Slash` (0x2F)

`KEYCODE_NUMPAD_DIVIDE` (154)

`"Subtract"` \[1\] <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The numeric keypad's subtraction key, -.

`VK_SUBTRACT` (0x6D)

`kVK_ANSI_KeypadMinus` (0x4E)

`GDK_KEY_KP_Subtract` (0xFFAD)

`KEYCODE_NUMPAD_SUBTRACT` (156)

`"Separator"` \[1\]

The numeric keypad's places separator character.

(In the United States this is a comma, but elsewhere it is frequently a period.)

`VK_SEPARATOR` (0x6C)

`kVK_JIS_KeypadComma` (0x5F)

`GDK_KEY_KP_Separator` (0xFFAC)

`KEYCODE_NUMPAD_COMMA` (159)

`"0"` through `"9"`

The actual digit keys on the numeric keypad.

`VK_NUMPAD0` (0x60) - `VK_NUMPAD9` (0x69)

`kVK_Keypad0` (0x52) - `kVK_Keypad9` (0x5C)

`GDK_KEY_KP_0` (0xFFB0) - `GDK_KEY_KP_9` (0xFFB9)

`KEYCODE_NUMPAD_0` (144) - `KEYCODE_NUMPAD_9` (153)

\[1\] While older browsers used words like `"Add"`, `"Decimal"`, `"Multiply"`, and so forth modern browsers identify these using the actual character (`"+"`, `"."`, `"*"`, and so forth).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key/Key_Values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key/Key_Values</a>
