KeyboardEvent
=============

`KeyboardEvent` objects describe a user interaction with the keyboard; each event describes a single interaction between the user and a key (or combination of a key with modifier keys) on the keyboard. The event type (`keydown`, `keypress`, or `keyup`) identifies what kind of keyboard activity occurred.

**Note:** `KeyboardEvent` events just indicate what interaction the user had with a key on the keyboard at a low level, providing no contextual meaning to that interaction. When you need to handle text input, use the `input` event instead. Keyboard events may not be fired if the user is using an alternate means of entering text, such as a handwriting system on a tablet or graphics tablet.

Constructor
-----------

[`KeyboardEvent()`](keyboardevent/keyboardevent)  
Creates a new `KeyboardEvent` object.

Constants
---------

The `KeyboardEvent` interface defines the following constants.

### Keyboard locations

The following constants identify which part of the keyboard the key event originates from. They are accessed as `KeyboardEvent.DOM_KEY_LOCATION_STANDARD` and so forth.

<table><caption>Keyboard location identifiers</caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_KEY_LOCATION_STANDARD</code></td><td>0x00</td><td><p>The key described by the event is not identified as being located in a particular area of the keyboard; it is not located on the numeric keypad (unless it's the NumLock key), and for keys that are duplicated on the left and right sides of the keyboard, the key is, for whatever reason, not to be associated with that location.</p><p>Examples include alphanumeric keys on the standard PC 101 US keyboard, the NumLock key, and the space bar.</p></td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_LEFT</code></td><td>0x01</td><td><p>The key is one which may exist in multiple locations on the keyboard and, in this instance, is on the left side of the keyboard.</p><p>Examples include the left Control key, the left Command key on a Macintosh keyboard, or the left Shift key.</p></td></tr><tr class="odd"><td><code>DOM_KEY_LOCATION_RIGHT</code></td><td>0x02</td><td><p>The key is one which may exist in multiple positions on the keyboard and, in this case, is located on the right side of the keyboard.</p><p>Examples include the right Shift key and the right Alt key (Option on a Mac keyboard).</p></td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_NUMPAD</code></td><td>0x03</td><td><p>The key is located on the numeric keypad, or is a virtual key associated with the numeric keypad if there's more than one place the key could originate from. The NumLock key does not fall into this group and is always encoded with the location <code>DOM_KEY_LOCATION_STANDARD</code>.</p><p>Examples include the digits on the numeric keypad, the keypad's Enter key, and the decimal point on the keypad.</p></td></tr></tbody></table>

Properties
----------

*This interface also inherits properties of its parents, [`UIEvent`](uievent) and [`Event`](event).*

 [`KeyboardEvent.altKey`](keyboardevent/altkey) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Alt ( Option or ⌥ on OS X) key was active when the key event was generated.

 [`KeyboardEvent.code`](keyboardevent/code) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) with the code value of the physical key represented by the event.

**Warning:** This ignores the user's keyboard layout, so that if the user presses the key at the "Y" position in a QWERTY keyboard layout (near the middle of the row above the home row), this will always return "KeyY", even if the user has a QWERTZ keyboard (which would mean the user expects a "Z" and all the other properties would indicate a "Z") or a Dvorak keyboard layout (where the user would expect an "F").

 [`KeyboardEvent.ctrlKey`](keyboardevent/ctrlkey) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Ctrl key was active when the key event was generated.

 [`KeyboardEvent.isComposing`](keyboardevent/iscomposing) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the event is fired between after `compositionstart` and before `compositionend`.

 [`KeyboardEvent.key`](keyboardevent/key) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the key value of the key represented by the event.

 <span class="page-not-created">`KeyboardEvent.locale`</span> <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing a locale string indicating the locale the keyboard is configured for. This may be the empty string if the browser or device doesn't know the keyboard's locale.

**Note:** This does not describe the locale of the data being entered. A user may be using one keyboard layout while typing text in a different language.

 [`KeyboardEvent.location`](keyboardevent/location) <span class="badge inline readonly">Read only </span>   
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the location of the key on the keyboard or other input device. A list of the constants identifying the locations is shown above in [Keyboard locations](#keyboard_locations).

 [`KeyboardEvent.metaKey`](keyboardevent/metakey) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Meta key (on Mac keyboards, the ⌘ Command key; on Windows keyboards, the Windows key (⊞)) was active when the key event was generated.

 [`KeyboardEvent.repeat`](keyboardevent/repeat) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the key is being held down such that it is automatically repeating.

 [`KeyboardEvent.shiftKey`](keyboardevent/shiftkey) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the Shift key was active when the key event was generated.

Methods
-------

*This interface also inherits methods of its parents, [`UIEvent`](uievent) and [`Event`](event).*

[`KeyboardEvent.getModifierState()`](keyboardevent/getmodifierstate)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if a modifier key such as Alt, Shift, Ctrl, or Meta, was pressed when the event was created.

Obsolete methods
----------------

 [`KeyboardEvent.initKeyEvent()`](keyboardevent/initkeyevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Initializes a `KeyboardEvent` object. This was implemented only by Firefox, and is no longer supported even there; instead, you should use the [`KeyboardEvent()`](keyboardevent/keyboardevent) constructor.

 [`KeyboardEvent.initKeyboardEvent()`](keyboardevent/initkeyboardevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Initializes a `KeyboardEvent` object. This is now deprecated. You should instead use the [`KeyboardEvent()`](keyboardevent/keyboardevent) constructor.

Obsolete properties
-------------------

 <span class="page-not-created">`KeyboardEvent.char`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the character value of the key. If the key corresponds to a printable character, this value is a non-empty Unicode string containing that character. If the key doesn't have a printable representation, this is an empty string.

**Note:** If the key is used as a macro that inserts multiple characters, this attribute's value is the entire string, not just the first character.

 [`KeyboardEvent.charCode`](keyboardevent/charcode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the Unicode reference number of the key; this attribute is used only by the `keypress` event. For keys whose `char` attribute contains multiple characters, this is the Unicode value of the first character in that attribute. In Firefox 26 this returns codes for printable characters.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](keyboardevent/key) instead, if available.

 [`KeyboardEvent.keyCode`](keyboardevent/keycode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing a system and implementation dependent numerical code identifying the unmodified value of the pressed key.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](keyboardevent/key) instead, if available.

 [`KeyboardEvent.keyIdentifier`](keyboardevent/keyidentifier) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
This property is non-standard and has been deprecated in favor of [`KeyboardEvent.key`](keyboardevent/key). It was part of an old version of DOM Level 3 Events.

 <span class="page-not-created">`KeyboardEvent.keyLocation`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
This is a non-standard deprecated alias for [`KeyboardEvent.location`](keyboardevent/location). It was part of an old version of DOM Level 3 Events.

 [`KeyboardEvent.which`](keyboardevent/which) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing a system and implementation dependent numeric code identifying the unmodified value of the pressed key; this is usually the same as `keyCode`.

**Warning:** This attribute is deprecated; you should use [`KeyboardEvent.key`](keyboardevent/key) instead, if available.

Events
------

The following events are based on the `KeyboardEvent` type. They can be delivered to any object which implements [`GlobalEventHandlers`](globaleventhandlers), including [`Element`](element), [`Document`](document), and [`Window`](window). In the list below, each event links to the documentation for the `Document` handler for the event, which applies generally to all of the recipients.

[`keydown`](document/keydown_event)  
A key has been pressed.

[`keyup`](document/keyup_event)  
A key has been released.

### Obsolete events

 [`keypress`](document/keypress_event) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A key that normally produces a character value has been pressed. This event was highly device-dependent and is obsolete. You should not use it.

Usage notes
-----------

There are three types of keyboard events: `keydown`, `keypress`, and `keyup`. For most keys, Gecko dispatches a sequence of key events like this:

1.  When the key is first pressed, the `keydown` event is sent.
2.  If the key is not a modifier key, the `keypress` event is sent.
3.  When the user releases the key, the `keyup` event is sent.

### Special cases

Some keys toggle the state of an indicator light; these include keys such as Caps Lock, Num Lock, and Scroll Lock. On Windows and Linux, these keys dispatch only the `keydown` and `keyup` events.

On Linux, Firefox 12 and earlier also dispatched the `keypress` event for these keys.

However, a limitation of the macOS event model causes Caps Lock to dispatch only the `keydown` event. Num Lock was supported on some older laptop models (2007 models and older), but since then, macOS hasn't supported Num Lock even on external keyboards. On older MacBooks with a Num Lock key, that key doesn't generate any key events. Gecko does support the Scroll Lock key if an external keyboard which has an F14 key is connected. In certain older versions of Firefox, this key generated a `keypress` event; this inconsistent behavior was [bug 602812](https://bugzilla.mozilla.org/show_bug.cgi?id=602812).

### Auto-repeat handling

When a key is pressed and held down, it begins to auto-repeat. This results in a sequence of events similar to the following being dispatched:

1.  `keydown`
2.  `keypress`
3.  `keydown`
4.  `keypress`
5.  &lt;&lt;repeating until the user releases the key&gt;&gt;
6.  `keyup`

This is what the DOM Level 3 specification says should happen. There are some caveats, however, as described below.

#### Auto-repeat on some GTK environments such as Ubuntu 9.4

In some GTK-based environments, auto-repeat dispatches a native key-up event automatically during auto-repeat, and there's no way for Gecko to know the difference between a repeated series of keypresses and an auto-repeat. On those platforms, then, an auto-repeat key will generate the following sequence of events:

1.  `keydown`
2.  `keypress`
3.  `keyup`
4.  `keydown`
5.  `keypress`
6.  `keyup`
7.  &lt;&lt;repeating until the user releases the key&gt;&gt;
8.  `keyup`

In these environments, unfortunately, there's no way for web content to tell the difference between auto-repeating keys and keys that are just being pressed repeatedly.

#### Auto-repeat handling prior to Gecko 5.0

Before Gecko 5.0 (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2), keyboard handling was less consistent across platforms.

Windows  
Auto-repeat behavior is the same as in Gecko 4.0 and later.

Mac  
After the initial keydown event, only keypress events are sent until the keyup event occurs; the inter-spaced keydown events are not sent.

Linux  
The event behavior depends on the specific platform. It will either behave like Windows or Mac depending on what the native event model does.

**Note:** Manually firing an event does *not* generate the default action associated with that event. For example, manually firing a key event does not cause that letter to appear in a focused text input. In the case of UI events, this is important for security reasons, as it prevents scripts from simulating user actions that interact with the browser itself.

Example
-------

    <!DOCTYPE html>
    <html>
    <head>
    <script>
    'use strict';

    document.addEventListener('keydown', (event) => {
      const keyName = event.key;

      if (keyName === 'Control') {
        // do not alert when only Control key is pressed.
        return;
      }

      if (event.ctrlKey) {
        // Even though event.key is not 'Control' (e.g., 'a' is pressed),
        // event.ctrlKey may be true if Ctrl key is pressed at the same time.
        alert(`Combination of ctrlKey + ${keyName}`);
      } else {
        alert(`Key pressed ${keyName}`);
      }
    }, false);

    document.addEventListener('keyup', (event) => {
      const keyName = event.key;

      // As the user releases the Ctrl key, the key is no longer active,
      // so event.ctrlKey is false.
      if (keyName === 'Control') {
        alert('Control key was released');
      }
    }, false);

    </script>
    </head>

    <body>
    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#interface-keyboardevent">UI Events<br />
<span class="small">The definition of 'KeyboardEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

The `KeyboardEvent` interface specification went through numerous draft versions, first under DOM Events Level 2 where it was dropped as no consensus arose, then under DOM Events Level 3. This led to the implementation of non-standard initialization methods, the early DOM Events Level 2 version, [`KeyboardEvent.initKeyEvent()`](keyboardevent/initkeyevent) by Gecko browsers and the early DOM Events Level 3 version, [`KeyboardEvent.initKeyboardEvent()`](keyboardevent/initkeyboardevent) by others. Both have been superseded by the modern usage of a constructor: [`KeyboardEvent()`](keyboardevent/keyboardevent).

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

`KeyboardEvent`

1

12

1.5

9

12.1

3.1

1

18

4

12.1

2

1.0

`KeyboardEvent`

Yes

≤79

31

No

Yes

Yes

Yes

Yes

31

Yes

Yes

Yes

`altKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`charCode`

26

12

3

9

12.1

5.1

≤37

Yes

Yes

Yes

5.1

Yes

`code`

48

79

38

No

35

10

48

48

38

35

10

5.0

`ctrlKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

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

`isComposing`

56

≤79

31

No

43

10.1

56

56

31

43

10.3

6.0

`key`

51

12

23

9

IE's implementation does not completely match the current spec because it is based on an older version of the spec.

38

10

51

51

23

41

10

5.0

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

`keyIdentifier`

26-54

?

No

No

15-41

5.1

≤37-54

26-54

No

Yes-41

5.1

1.5-6.0

`location`

Yes

12

15

9

Yes

6.1

Yes

Yes

15

Yes

8

Yes

`metaKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`repeat`

Yes

79

28

No

Yes

10.1

Yes

Yes

28

Yes

10.3

Yes

`shiftKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`which`

4

12

2

Firefox also implements this property on the `UIEvent` interface.

9

12.1

5.1

≤37

Yes

Yes

Firefox also implements this property on the `UIEvent` interface.

12.1

5.1

Yes

### Compatibility notes

-   As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](keyboardevent/keycode#non-printable_keys_(function_keys)) ([bug 968056](https://bugzilla.mozilla.org/show_bug.cgi?id=968056)), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

See also
--------

-   [`KeyboardEvent.code`](keyboardevent/code).
-   [`KeyboardEvent.key`](keyboardevent/key).
-   [`KeyboardEvent.getModifierState()`](keyboardevent/getmodifierstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent</a>
