KeyboardEvent.location
======================

The `KeyboardEvent.location` read-only property returns an `unsigned long` representing the location of the key on the keyboard or other input device.

Possible values are:

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_KEY_LOCATION_STANDARD</code></td><td>0</td><td>The key has only one version, or can't be distinguished between the left and right versions of the key, and was not pressed on the numeric keypad or a key that is considered to be part of the keypad.</td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_LEFT</code></td><td>1</td><td>The key was the left-hand version of the key; for example, the left-hand Control key was pressed on a standard 101 key US keyboard. This value is only used for keys that have more than one possible location on the keyboard.</td></tr><tr class="odd"><td><code>DOM_KEY_LOCATION_RIGHT</code></td><td>2</td><td>The key was the right-hand version of the key; for example, the right-hand Control key is pressed on a standard 101 key US keyboard. This value is only used for keys that have more than one possible location on the keyboard.</td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_NUMPAD</code></td><td>3</td><td><p>The key was on the numeric keypad, or has a virtual key code that corresponds to the numeric keypad.</p><div class="note notecard"><strong>Note:</strong> When NumLock is locked, Gecko always returns <code>DOM_KEY_LOCATION_NUMPAD</code> for the keys on the numeric pad. Otherwise, when NumLock is unlocked and the keyboard actually has a numeric keypad, Gecko always returns <code>DOM_KEY_LOCATION_NUMPAD</code> too. On the other hand, if the keyboard doesn't have a keypad, such as on a notebook computer, some keys become Numpad only when NumLock is locked. When such keys fires key events, the location attribute value depends on the key. That is, it must not be <code>DOM_KEY_LOCATION_NUMPAD</code>.</div><div class="note notecard"><strong>Note:</strong> NumLock key's key events indicate <code>DOM_KEY_LOCATION_STANDARD</code> both on Gecko and Internet Explorer.</div></td></tr><tr class="odd"><td><code>DOM_KEY_LOCATION_MOBILE</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span><span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>4</td><td><p>The key was on a mobile device; this can be on either a physical keypad or a virtual keyboard.</p><div class="note notecard"><strong>Note:</strong> Gecko always returns <code>DOM_KEY_LOCATION_MOBILE</code> on Android (Prior to 18), Maemo, and <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Boot_to_Gecko">Boot to Gecko</a>. However, at <span>Gecko 38</span>, this is dropped.</div></td></tr><tr class="even"><td><code>DOM_KEY_LOCATION_JOYSTICK</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>5</td><td><p>The key was a button on a game controller or a joystick on a mobile device.</p><div class="note notecard"><strong>Note:</strong> Gecko never fires trusted key events with <code>DOM_KEY_LOCATION_JOYSTICK</code> except on Android. Starting 18, native key events on Android may have this value. However, at <span>Gecko 38</span>, this is dropped.</div></td></tr></tbody></table>

Syntax
------

    var location = event.location;

Example
-------

    function keyEvent(event) {
      console.log("Location of key pressed: " + event.location);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-location">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.location' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`KeyboardEvent`](../keyboardevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/location</a>
