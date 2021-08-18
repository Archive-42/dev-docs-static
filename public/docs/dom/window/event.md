Window.event
============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only [`Window`](../window) property `event` returns the [`Event`](../event) which is currently being handled by the site's code. Outside the context of an event handler, the value is always `undefined`.

You *should* avoid using this property in new code, and should instead use the [`Event`](../event) passed into the event handler function. This property is not universally supported and even when supported introduces potential fragility to your code.

**Note:** This property can be fragile, in that there may be situations in which the returned `Event` is not the expected value. In addition, `Window.event` is not accurate for events dispatched within [shadow trees](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-window-event">DOM<br />
<span class="small">The definition of 'Window.event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`event`

1

12

66

4

7

1.1

1

18

66

10.1

1

1.0

See also
--------

-   [`Event.srcElement`](../event/srcelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/event</a>
