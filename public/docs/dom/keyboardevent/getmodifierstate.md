KeyboardEvent.getModifierState()
================================

The `KeyboardEvent.getModifierState()` method returns the current state of the specified modifier key: `true` if the modifier is active (that is the modifier key is pressed or locked), otherwise, `false`.

Syntax
------

    var active = event.getModifierState(keyArg);

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

### Parameters

*`keyArg`*  
A modifier key value. The value must be one of the [`KeyboardEvent.key`](key) values which represent modifier keys, or the string `"Accel"` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>. This is case-sensitive.

Modifier keys on Internet Explorer
----------------------------------

IE9 uses `"Scroll"` for `"ScrollLock"` and `"Win"` for `"OS"`.

Modifier keys on Gecko
----------------------

When getModifierState() returns true on Gecko?

Windows

Linux (GTK)

Mac

Android 2.3

Android 3.0 or latter

`"Alt"`

Either Alt key or AltGr key pressed

Alt key pressed

⌥ Option key pressed

Alt key or option key pressed

`"AltGraph"`

Both Alt and Ctrl keys are pressed, or AltGr key is pressed

Level 3 Shift key (or Level 5 Shift key) pressed

⌥ Option key pressed

*Not supported*

`"CapsLock"`

During LED for ⇪ Caps Lock turned on

*Not supported*

While CapsLock is locked

`"Control"`

Either Ctrl key or AltGr key pressed

Ctrl key pressed

control key pressed

menu key pressed.

Ctrl key, control key or menu key pressed.

`"Fn"`

*Not supported*

Function key is pressed, but we're not sure what key makes the modifier state active. Fn key on Mac keyboard doesn't cause this active.

`"FnLock"`

*Not supported*

`"Hyper"`

*Not supported*

`"Meta"`

*Not supported*

Meta key pressed

⌘ Command key pressed

*Not supported*

⊞ Windows Logo key or command key pressed

`"NumLock"`

During LED for Num Lock turned on

A key on numpad pressed

*Not supported*

While NumLock is locked

`"OS"`

⊞ Windows Logo key pressed

Super key or Hyper key pressed (typically, mapped to ⊞ Windows Logo key)

*Not supported*

`"ScrollLock"`

During LED for Scroll Lock turned on

During LED for Scroll Lock turned on, but typically this isn't supported by platform

*Not supported*

While ScrollLock is locked

`"Shift"`

⇧ Shift key pressed

`"Super"`

*Not supported*

`"Symbol"`

*Not supported*

`"SymbolLock"`

*Not supported*

-   On the other platforms, "Alt", "Control" and "Shift" may be supported.
-   All modifiers (except `"FnLock"`, `"Hyper"`, `"Super"` and `"Symbol"` which are defined after Gecko implements this) are always supported for untrusted events on Gecko. This doesn't depend on the platform.

`"Accel"` virtual modifier
--------------------------

**Note:** The `"Accel"` virtual modifier has been effectively **deprecated** in current drafts of the DOM3 Events specification.

`getModifierState()` also accepts a deprecated virtual modifier named `"Accel"`. `event.getModifierState("Accel")` returns `true` when at least one of [`KeyboardEvent.ctrlKey`](ctrlkey) or [`KeyboardEvent.metaKey`](metakey) is `true`.

In old implementations and outdated specifications, it returned `true` when a modifier which is the typical modifier key for the shortcut key is pressed. For example, on Windows, pressing Ctrl key may make it return `true`. However, on Mac, pressing ⌘ Command key may make it return `true`. Note that which modifier key makes it return true depends on platforms, browsers, and user settings. For example, Firefox users can customize this with a pref, `"ui.key.accelKey"`.

Example
-------

    // Ignore if following modifier is active.
    if (event.getModifierState("Fn") ||
        event.getModifierState("Hyper") ||
        event.getModifierState("OS") ||
        event.getModifierState("Super") ||
        event.getModifierState("Win") /* hack for IE */) {
      return;
    }

    // Also ignore if two or more modifiers except Shift are active.
    if (event.getModifierState("Control") +
        event.getModifierState("Alt") +
        event.getModifierState("Meta") > 1) {
      return;
    }

    // Handle shortcut key with standard modifier
    if (event.getModifierState("Accel")) {
      switch (event.key.toLowerCase()) {
        case "c":
          if (event.getModifierState("Shift")) {
            // Handle Accel + Shift + C
            event.preventDefault(); // consume the key event
          }
          break;
        case "k":
          if (!event.getModifierState("Shift")) {
            // Handle Accel + K
            event.preventDefault(); // consume the key event
          }
          break;
      }
      return;
    }

    // Do something different for arrow keys if ScrollLock is locked.
    if ((event.getModifierState("ScrollLock") ||
           event.getModifierState("Scroll") /* hack for IE */) &&
        !event.getModifierState("Control") &&
        !event.getModifierState("Alt") &&
        !event.getModifierState("Meta")) {
      switch (event.key) {
        case "ArrowDown":
        case "Down": // hack for IE and old Gecko
          event.preventDefault(); // consume the key event
          break;
        case "ArrowLeft":
        case "Left": // hack for IE and old Gecko
          // Do something different if ScrollLock is locked.
          event.preventDefault(); // consume the key event
          break;
        case "ArrowRight":
        case "Right": // hack for IE and old Gecko
          // Do something different if ScrollLock is locked.
          event.preventDefault(); // consume the key event
          break;
        case "ArrowUp":
        case "Up": // hack for IE and old Gecko
          // Do something different if ScrollLock is locked.
          event.preventDefault(); // consume the key event
          break;
      }
    }

Although this example uses `.getModifierState()` with `"Alt"`, `"Control"`, `"Meta"` and `"Shift"`, using `event.altKey`, `event.ctrlKey`, `event.metaKey` and `event.shiftKey` may be more preferable.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-getModifierState">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'getModifierState()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition (<a href="https://dvcs.w3.org/hg/dom3events/raw-file/tip/html/DOM3Events-key.html#keys-modifier">Modifier Keys spec</a>)</td></tr></tbody></table>

Browser compatibility
---------------------

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

`getModifierState`

31

12

15

9

17

10.1

4.4.3

31

15

18

10.3

2.0

`accel_parameter`

48

≤79

32

No

35

No

48

48

32

35

No

5.0

`alt_parameter`

Yes

≤79

Yes

?

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`altgraph_parameter`

48

≤79

Yes

?

35

10.1

48

48

Yes

35

10.3

5.0

`capslock_parameter`

48

≤79

Yes

?

35

?

48

48

Yes

35

?

5.0

`control_parameter`

Yes

≤79

Yes

?

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`fn_parameter`

48

≤79

Yes

?

35

?

48

48

Yes

35

?

5.0

`fnlock_parameter`

Yes

≤79

No

?

Yes

?

Yes

Yes

No

Yes

?

Yes

`hyper_parameter`

Yes

≤79

No

?

Yes

?

Yes

Yes

No

Yes

?

Yes

`meta_parameter`

Yes

≤79

Yes

?

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`numlock_parameter`

48

≤79

Yes

?

35

?

48

48

Yes

35

?

5.0

`os_parameter`

48

12

Yes

Yes

35

?

48

48

Yes

35

?

5.0

`scrolllock_parameter`

48

12

Yes

Yes

35

?

48

48

Yes

35

?

5.0

`shift_parameter`

Yes

≤79

Yes

?

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`super_parameter`

Yes

≤79

No

?

Yes

?

Yes

Yes

No

Yes

?

Yes

`symbol_parameter`

48

≤79

No

?

35

?

48

48

No

35

?

5.0

`symbollock_parameter`

Yes

≤79

No

?

Yes

?

Yes

Yes

No

Yes

?

Yes

See also
--------

-   The [`KeyboardEvent`](../keyboardevent) this method belongs to.
-   [`MouseEvent.getModifierState`](../mouseevent/getmodifierstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/getModifierState</a>
