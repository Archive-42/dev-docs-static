# Element: webkitmouseforcewillbegin event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Safari for macOS fires the non-standard `webkitmouseforcewillbegin` event at an [`Element`](../element) before firing the initial `mousedown` event. This offers the opportunity to tell the system not to trigger any default Force Touch actions if and when the click turns into a [Force Touch event](../force_touch_events).

To instruct macOS not to engage any default Force Touch actions if the user apply enough pressure to activate a Force Touch event, call [`preventDefault()`](../event/preventdefault) on the `webkitmouseforcewillbegin` event object.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Unknown</td></tr><tr class="even"><td>Cancelable</td><td>Unknown</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr></tbody></table>

`webkitmouseforcewillbegin` is a proprietary, WebKit-specific event. It is part of the [Force Touch events](../force_touch_events) feature.

## Specifications

_Not part of any specification._ Apple has [a description at the Mac Developer Library](https://developer.apple.com/library/prerelease/mac/documentation/AppleApplications/Conceptual/SafariJSProgTopics/RespondingtoForceTouchEventsfromJavaScript.html).

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

`webkitmouseforcewillbegin_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [Force Touch events](../force_touch_events)
- `webkitmouseforcedown`
- `webkitmouseforceup`
- `webkitmouseforcechanged`
- [`Force_Touch_events`](../force_touch_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcewillbegin_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcewillbegin_event</a>
