UIEvent.isChar
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `UIEvent.isChar` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event produced a key character or not.

Syntax
------

    var isChar = UIEvent.isChar;

### Value

A Boolean which is `true` if the event produces a character; otherwise `false`. Some keystroke combinations may raise events but not produce any character (example: ctrl-alt-?). When this is the case, `isChar` returns `false`. It is used when event handlers need to do something like echo the input on the screen.

Example
-------

In this snippet, which is part of an event handler, the event is checked to see if it generates a character; if it does, the value of <span class="page-not-created">`UIEvent.which`</span> is appended to a string which buffers the typed characters.

    if (event.isChar) {
      characterBuffer += e.which;
    }

Specifications
--------------

*This property is not part of any specification.*

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

`isChar`

No

No

Yes-55

The `isChar` property has never been supported by any browser but Firefox, and even on Firefox it's never worked except on Mac OSX. For that reason, it's been removed in Firefox 55 to align with other browsers.

No

No

No

No

No

Yes-55

The `isChar` property has never been supported by any browser but Firefox, and even on Firefox it's never worked except on Mac OSX. For that reason, it's been removed in Firefox 55 to align with other browsers.

No

No

No

See also
--------

-   [`UIEvent`](../uievent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/isChar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/isChar</a>
